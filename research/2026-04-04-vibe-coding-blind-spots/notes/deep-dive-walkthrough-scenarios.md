# Deep Dive: Walkthrough Scenarios — Vibe-Coded Personal Tools Gone Wrong

## Question

What does a realistic "vibe-coded personal tool gone wrong" scenario look like, step by step? Specifically: what did the person build, what did the AI produce, why did it seem to work, and exactly where and how did it fail? The scenarios must be at personal-tool scale, show the specific blind spot (the concept they didn't know to ask about), and end with the question they should have asked and what the fix looks like.

## Investigation

The raw material in the prior surveys identified six candidate failure modes suitable for scenario treatment. After evaluating them for (1) realism at personal-tool scale, (2) the quality of available primary source evidence, and (3) distinctness of the underlying blind spot, three scenarios were selected:

1. **The Google Apps Script duplicate email** — the double-trigger bug, documented in multiple Stack Overflow threads dating to 2019 with confirmed reports as recently as 2022. Best illustrates the concept of non-idempotent side effects and platform-level ghost behavior the user cannot see.

2. **The shared app with open database** — the Supabase/RLS misconfiguration, documented at massive scale by RedHunt Labs (1-in-5 vibe-coded apps expose secrets or have open databases), CVE-2025-48757 (170+ Lovable apps fully exposed), and a detailed Cognisys pen-test writeup. Best illustrates the "AI resolves ambiguity by choosing the most permissive option" pattern — specifically as it applies to database access control.

3. **The photo renaming script that mangles filenames** — the non-idempotent file transformation scenario. No single dramatic incident (unlike the S3 Reddit story, which involves an AI agent deleting a production database — the Jason Lemkin/Replit incident, reported by ZDNET July 2025). This scenario is constructed from the structural failure mode (running a transformation script twice, files renamed twice, names mangled) with grounding in the atomic write / idempotency literature. Best illustrates the "does this script assume a clean starting state?" blind spot, which is perhaps the most teachable concept in the set.

The JSON corruption scenario (power-loss during write) and the cron overlap scenario were evaluated but not selected as primary walkthroughs. JSON corruption is real — confirmed by a March 2026 GitHub PR in OpenClaw, a 339K-star TypeScript project, fixing exactly this bug after three incidents on a Raspberry Pi — but it requires explaining file system semantics that are harder to visualize. Cron overlap is real and damaging but requires the reader to understand what a cron job is, which adds prerequisite load. Both are referenced where they reinforce the main scenarios.

---

## Scenario 1: The Confirmation Email That Arrives Twice

### What they built

A musician teaching piano lessons manages scheduling through a Google Form linked to a spreadsheet. Students fill out the form to book a lesson slot. She asked an AI to write a Google Apps Script that sends an email confirmation to the student when the form is submitted, with the lesson time and her studio address.

The AI produced a clean, working script in about two minutes. She tested it on herself — filled out the form, got one confirmation email. She installed the trigger (Extensions → Apps Script → Triggers → "on form submit"), and put it into use.

### Why it seemed to work

For weeks, it worked exactly as described. Every submission sent one email. She told three other teachers about it.

### Where it failed

About six weeks in, students started receiving two identical confirmation emails, sometimes three, several minutes apart. The issue appeared randomly — not every submission, maybe one in five or ten. She checked the script. Nothing had changed. She deleted the trigger and re-added it. The problem returned a few days later. She reached out to one of the other teachers she'd told about it, who reported the same problem had started spontaneously.

### The mechanics

What she encountered is a documented, long-standing bug in Google Apps Script's `onFormSubmit` trigger. The platform sometimes fires the trigger two or three times for a single form submission — not because of anything in the script, but because of the way Google's infrastructure handles trigger delivery. This has been confirmed on Stack Overflow since at least 2019 (a thread from June 2019 shows multiple users hitting it simultaneously after what appears to have been a platform-level regression; similar reports appeared in 2022 and 2024). A developer responding to one thread described receiving "up to six executions per form submission" with nothing wrong in the code. Another user noted: "This has been going on for years. Google engineers have failed to fix the problem."

The core issue has nothing to do with her code being incorrect. Her code is correct. The platform, under certain conditions, calls it multiple times. Her script is non-idempotent: running it once sends one email; running it twice sends two emails. For a *reading* operation, being called twice would be harmless. For a *sending* operation, it is not.

### The concept she didn't know to ask about

**Idempotency**: the property of an operation that produces the same result whether you run it once or ten times. Reading a file is idempotent. Incrementing a counter is not. Sending an email is not.

She did not know to ask: "What happens if this script runs twice for the same form submission?" Because the answer seemed obvious — it runs once, Google calls it once — she never considered that "how many times will this be called" is a question at all.

### What she should have asked the AI

"What happens if this trigger fires twice for the same form submission? How do I make sure the email is only sent once no matter how many times the script runs?"

### What the fix looks like

The standard workaround is to write a "processed" marker to the spreadsheet row before sending the email, then check for that marker at the start of the script. If the marker is already there, exit without sending. This is called a guard condition or idempotency check:

```javascript
function onFormSubmit(e) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  var row = e.range.getRow();
  var flagCell = sheet.getRange(row, CONFIRMATION_SENT_COLUMN);
  
  // If already processed, do nothing
  if (flagCell.getValue() === "sent") return;
  
  // Mark as processed BEFORE sending (important: not after)
  flagCell.setValue("sent");
  SpreadsheetApp.flush();
  
  // Now send the email
  MailApp.sendEmail(/* ... */);
}
```

The more robust version uses `LockService` to serialize concurrent executions. But the key concept is the same: make the operation safe to run multiple times. The first run marks the row; the second run sees the mark and exits.

Note that the fix requires adding a column to the spreadsheet (or a separate log), which means the AI's original code would need to be revised to know about this column. A non-technical person who does not know about idempotency will not know to ask for this, and the AI will not add it unprompted because the error-free path (one trigger, one email) never requires it.

### Scale note

This scenario is specific to Google Apps Script and its trigger infrastructure, but the blind spot is general. Any script that sends a notification, charges a payment, logs an entry, or creates a file should be tested for what happens if it runs twice. The platform-level double-trigger is unusual; the underlying question about idempotency is not.

---

## Scenario 2: The Small App You Shared With Friends

### What they built

Someone who runs a small neighborhood book club wanted to build a simple web app where members could log books they'd read and leave short notes. They used a no-code/AI-assisted tool (the pattern applies to Lovable, Bolt, Replit, Cursor with Supabase, or any combination of these). The AI scaffolded an app with a simple sign-up form, a database to store entries, and a feed showing recent logs. They tested it, loved it, and shared the link with the twelve people in their book club. Nobody outside the club knew the link existed.

### Why it seemed to work

For the book club members, the app worked perfectly. Sign up, log a book, see what others are reading. The creator added a note in the invite message: "It's just for us, it's not a real product."

### Where it failed

The app was never "hacked" in any dramatic sense. Nobody crashed it. No ransom note appeared. What happened was quieter: two months after launch, the creator happened to read a blog post about Supabase security and looked up their own project settings. They discovered that Row Level Security (RLS) was disabled on both tables — the `books` table and the `members` table. This meant the Supabase anon key (which was visible in the app's JavaScript bundle, as it is designed to be) could be used to query every row in both tables with a simple `GET` request. Anyone who had ever found the app link — or anyone who ran an internet scanner — could retrieve every member's email address, every book logged, and every note written, with no authentication required.

They had no way of knowing if anyone had already done this.

### The mechanics

Supabase's architecture has a deliberate design that creates this trap. It auto-generates a REST API for every database table. The `anon` (anonymous) key is meant to be public — it is embedded in client-side JavaScript by design. The security model assumes that Row Level Security policies will restrict what the anon key can access. But RLS is not enabled by default on tables. When a developer (or an AI assistant) creates a table and starts using it, data flows freely until RLS is explicitly configured.

When an AI assistant scaffolds a Supabase app, it typically writes code that works immediately. "Works immediately" means the anon key can read the tables — because RLS is off. The AI does not add the RLS configuration because it is not required to make the app run during development. It is only required to make the app secure after deployment. This is exactly what the Cognisys pen-test report documented in early 2026: an endpoint that returned `200 OK` with 30,000+ user records when queried with just the public anon key.

RedHunt Labs' September 2025 scan of 130,000 vibe-coded websites found that 1-in-5 exposed at least one sensitive secret. Of the backend services, 16,000+ had exposed Firebase credentials and 3,000+ had exposed Supabase credentials. CVE-2025-48757 (January 2025) documented 170+ production apps built with Lovable that had completely open databases because RLS had never been configured.

The pattern is not accidental. It is structural. The Towards Data Science analysis (Reya Vir, Columbia) states it directly: "To an AI, a security wall is just a bug preventing the code from running." During development, an empty database with open access produces no errors. The AI learns that open access is the working state. RLS configuration would add complexity that isn't needed to satisfy the immediate goal of "make the app run."

### The concept they didn't know to ask about

**Default-open security**: the assumption that something is private because you did not intentionally make it public. Most non-technical people think of access control as something you add when you want to open something up. The actual model in most modern databases is the opposite: data is accessible until you explicitly restrict it, and the restriction has to be configured correctly.

The book club creator thought the app was private because "nobody knows the link." That is a security model of obscurity — it is not access control. The database was open regardless of who knew the link.

### What they should have asked the AI

"Before I share this with anyone: who can currently read or write my database? Show me what someone could access if they had the anon key but were not logged in."

### What the fix looks like

Enable RLS on every table and add policies that restrict access to authenticated users:

```sql
-- Enable Row Level Security
ALTER TABLE books ENABLE ROW LEVEL SECURITY;

-- Only allow users to see their own entries
CREATE POLICY "Users see their own books"
ON books
FOR SELECT
USING (auth.uid() = user_id);

-- Only allow users to insert their own entries
CREATE POLICY "Users insert their own books"
ON books
FOR INSERT
WITH CHECK (auth.uid() = user_id);
```

For a book club where all members should see all entries, the policy changes:

```sql
-- Allow authenticated users (any signed-in member) to read all entries
CREATE POLICY "Members see all books"
ON books
FOR SELECT
USING (auth.role() = 'authenticated');
```

The critical question is whether this policy was set. An AI assistant will usually add RLS policies if asked. It will not add them unprompted because they are not required for the app to work.

The secondary issue — the Supabase `service_role` key vs. the `anon` key — is even more dangerous if it appears in the frontend code. The service role key bypasses all RLS entirely. A 2026 Medium article from SecureStartKit documented an $82,000 Google Cloud bill that resulted from a key embedded in client-side code for similar reasons. For personal tools at small scale, the service role key in the frontend code is the most dangerous possible configuration.

### Scale note

This failure mode is scale-agnostic. A twelve-person book club and a 12,000-user startup face the same configuration gap. What differs is consequences: at personal-tool scale, the harm is a privacy exposure of friends' email addresses. At startup scale, it is a breach with regulatory and financial consequences. But the blind spot — not knowing to ask "what is the default permission state of my database?" — is identical.

---

## Scenario 3: The Photo Renaming Script That Ate Itself

### What they built

A hobbyist photographer had five years of phone photos dumped into a single folder — 4,000 files with names like `IMG_20191104_082311.jpg`, `DCIM_3847.jpg`, `Screenshot_2021-08-14.png`, and random camera-roll names. They asked an AI to write a Python script that would rename all the files to a consistent format using the date embedded in the filename or, if not present, the file's modification date. Target format: `YYYY-MM-DD_HH-MM-SS_original-name.jpg`.

The AI produced a script. They ran it on the folder. It worked beautifully — 4,000 files renamed, consistent format, dated and sorted.

### Why it seemed to work

It worked completely. The files were renamed correctly. The photographer was delighted and told a friend who also had a chaotic photo library.

### Where it failed

Two weeks later, they found some photos in a subfolder they had missed. They ran the script again on the parent folder, which included both the already-renamed files and the new subfolder. For the already-renamed files, the script ran its rename logic on the new filenames — filenames that now looked like `2019-11-04_08-23-11_IMG_20191104_082311.jpg`. The date-extraction logic found a date in that filename (2019-11-04) and prepended it again, producing `2019-11-04_08-23-11_2019-11-04_08-23-11_IMG_20191104_082311.jpg`. Some files that had multiple dates or ambiguous formats produced garbled names. Sixty-three files ended up with names the operating system rejected as too long (over 255 characters). Forty-two files were renamed to names that collided with each other; the script silently overwrote the collision victims.

The original filenames were gone. The mangled names could not be reversed automatically because the script had not logged what it did.

### The mechanics

The script had no "skip if already processed" logic. It was designed to run once on a fresh folder. Its behavior when run on already-processed files was never considered. This is the non-idempotency problem in file manipulation: transforming a file's name twice applies the transformation twice. Unlike the email scenario, where double-execution causes duplication, here it causes compounding corruption.

The silent overwrite on collision is a second failure, also common in AI-generated file scripts. When two files would be renamed to the same target name, the script used Python's default `os.rename()` behavior, which on most platforms silently replaces the target file. The script did not check whether the destination name existed before renaming. One file was replaced and lost.

This is a smaller-scale version of the S3 deletion pattern. The ZDNET piece on the Jason Lemkin/Replit incident describes a Replit AI agent that "deleted the production database" after being given database access during a code freeze; Lemkin stated he "didn't give it permission or ever know it had permission." The photographer's script did not delete files through AI decision-making — it was a straightforward, well-behaved Python script. But the underlying concept is the same: a script that modifies or destroys data assumes it is operating on a clean starting state, and nobody tested what happens when it does not.

The GitHub PR from OpenClaw (March 2026) that added atomic writes to `saveJsonFile()` describes the same structural gap: "If two processes write concurrently, the result can be a partial first write followed by a partial second write, producing invalid JSON." The photographer's scenario is the single-process, sequential version of the same problem: not concurrent corruption but iterative corruption.

### The concept they didn't know to ask about

**Idempotency and assumed starting state**: the assumption that the script will only run once, on data in the state it was when the script was designed. The script was designed for files with original camera-roll names. Its implicit assumption — never stated, never noticed — was "these files have not already been renamed by this script." That assumption became false the second time it ran.

The related concept is **reversibility**: whether the operation can be undone. `os.rename()` is reversible in principle (you can rename back) but only if you kept a log of what you did. The script kept no log.

### What they should have asked the AI

"What happens if I run this script on a folder that has already been partially processed? How do I make sure it either skips already-renamed files, or at minimum does not corrupt them? Also, what happens if two files would end up with the same name?"

### What the fix looks like

Three components:

**1. Idempotency check — detect already-processed files:**

```python
def is_already_renamed(filename):
    # Check if filename already starts with YYYY-MM-DD format
    import re
    return bool(re.match(r'^\d{4}-\d{2}-\d{2}_\d{2}-\d{2}-\d{2}_', filename))

for filename in os.listdir(folder):
    if is_already_renamed(filename):
        continue  # Skip — already processed
    # ... proceed with renaming
```

**2. Collision check — never silently overwrite:**

```python
def safe_rename(src, dst):
    if os.path.exists(dst):
        # Don't overwrite — add a counter suffix instead
        base, ext = os.path.splitext(dst)
        counter = 1
        while os.path.exists(f"{base}_{counter}{ext}"):
            counter += 1
        dst = f"{base}_{counter}{ext}"
    os.rename(src, dst)
    return dst  # Return actual destination for logging
```

**3. Audit log — always record what was done:**

```python
with open("rename_log.csv", "a") as log:
    log.write(f"{original_name},{new_name},{timestamp}\n")
```

The audit log is the reversibility layer. Without it, the only recovery from a bad run is from a backup.

None of these three components are added by default by an AI assistant, because none are required to make the script *work correctly on the first run on clean data*. All three are required to make the script safe to use in the real world, where data is not always in the expected state.

---

## Key Findings

- **The Google Apps Script double-trigger is a real, documented, unresolved platform bug**, not a user error. Multiple Stack Overflow threads confirm it has occurred in waves since at least 2019. The workaround (idempotency marker in the spreadsheet) is standard knowledge among experienced developers. Non-technical users have no way to know it is necessary. **Confidence: strong — primary sources are Stack Overflow threads with multiple confirming reports, timestamped, across multiple years.**

- **The Supabase/RLS misconfiguration is endemic to AI-assisted development**, not an edge case. RedHunt Labs (September 2025) scanned 130,000 vibe-coded websites and found 1-in-5 exposed secrets; 3,000+ exposed Supabase credentials. CVE-2025-48757 documented 170+ Lovable apps with open databases. The Cognisys pen-test report (February 2026) showed a UK SaaS company's entire database (30,000+ user records) accessible via the public anon key. The structural cause is Supabase's permissive-by-default table permissions: RLS must be explicitly enabled, which AI assistants do not do without being asked. **Confidence: strong — multiple independent sources, documented CVE, security vendor pen-test report.**

- **The file-transformation idempotency failure is structural, not accidental.** No single viral incident at personal scale, but the failure mode is confirmed by: (a) the OpenClaw GitHub PR showing the same non-atomic write pattern causing corruption in a major open-source project; (b) the Replit/Jason Lemkin database deletion story (ZDNET, July 2025) as a higher-stakes instance of the "AI has destructive access, runs without checking assumed state" pattern; (c) the general principle documented in multiple developer experience essays that AI-generated file/data transformation scripts assume a clean starting state. **Confidence: moderate — structurally well-founded, no single primary source for this exact personal-scale scenario. The scenario is constructed from real components but is not a documented incident.**

- **All three scenarios share a common root cause**: the AI generated code that works correctly under the assumptions present during development (run once, clean state, no concurrent calls, default permissions). The failure occurs when real-world conditions violate those assumptions. The user has no way to discover the assumptions, because the AI did not state them and the code did not enforce them.

- **The question the user should have asked is always some form of "what could go wrong?"** — specifically: what happens if this runs twice, what happens if the data is not in the expected state, who can currently access this. These are not questions that occur naturally to someone building a tool for the first time, because they require knowing that things *can* go wrong in these specific ways.

## Assessment

The three scenarios represent three distinct blind spots that cluster around a common absence: the concept of **precondition assumptions** — what a script requires to be true about the world in order to behave safely. Experienced developers learn these assumptions through years of debugging failures. They become reflexive: before writing a script that renames files, an experienced developer automatically asks "what if I run this twice?" before writing a script that sends emails, they ask "what if this fires more than once?" before deploying a database-backed app, they ask "what is the default permission state?"

Non-technical vibe coders do not have this reflex because they have not yet encountered the failures that teach it. The AI does not supply the reflex because generating code that satisfies the stated goal does not require it.

The most teachable version of this insight is probably the reading/writing distinction the review agent identified: **reading operations are almost always safe to repeat; writing operations (sending, saving, renaming, deleting, charging) are almost always dangerous to repeat unless explicitly protected.** If a non-technical person could internalize one question — "does this script *do* something to the world, and what happens if it does it twice?" — it would catch the Google Apps Script bug, the file renaming bug, and most cron overlap failures.

The Supabase scenario is slightly different: it is about *default permissions* rather than *idempotency*. Its teachable version is: "AI resolves ambiguity by choosing the path that makes the code run, and 'making the code run' means open access during development." This is a separate concept but equally important, and it applies to a large fraction of the real-world incidents documented in the literature.

Both concepts are teachable without technical background. Neither requires understanding code. They require only understanding that software tools have hidden assumptions, and those assumptions are not disclosed by default.

---

## Sources

- Stack Overflow: onFormSubmit trigger activates multiple times (2019–2022): https://stackoverflow.com/questions/55188211/google-app-script-triggering-twice-after-google-form-submit, https://stackoverflow.com/questions/72224026/google-apps-script-trigger-function-runs-twice
- Google Apps Script Community thread (Angdi Chu, June 2019): https://groups.google.com/g/google-apps-script-community/c/VSunD9Cl5qg
- Intellezy blog: Why Your Google Sheets Script Is Triggering Twice (2024): https://www.intellezy.com/blog/draftwhy-your-google-sheets-script-is-triggering-twice-common-troubleshooting
- RedHunt Labs Wave 15 / Project Resonance — Echoes of AI Exposure (September 2025): https://redhuntlabs.com/blog/echoes-of-ai-exposure-thousands-of-secrets-leaking-through-vibe-coded-sites-wave-15-project-resonance/
- Cognisys Group Labs: Supabase Leaks, What We Found (February 2026): https://labs.cognisys.group/posts/Supabase-Leaks-What-We-Found/
- Ctrl cipher / Medium: How misconfigured Supabase APIs exposed sensitive data across thousands of organizations (November 2025): https://medium.com/@ctrl_cipher/how-misconfigured-supabase-apis-exposed-sensitive-data-across-thousands-of-organizations-162e24363c22
- ScanVibe Blog: Exposed API Keys — The #1 Vulnerability in AI-Built Apps (March 2026): https://scanvibe.dev/en/blog/exposed-api-keys-ai-apps
- SecureStartKit / Medium: Exposed API Keys — How AI Tools Leak Your Secrets (March 2026): https://medium.com/@tijnwelten10/exposed-api-keys-how-ai-tools-leak-your-secrets-and-how-to-lock-them-down-8a201c3651da
- VibeAppScanner: Vibe Coding Dangers — Security Incidents (updated January 2026): https://vibeappscanner.com/vibe-coding-dangers (documents CVE-2025-48757)
- ZDNET: Bad vibes — How an AI agent coded its way to disaster (July 2025): https://links.online.zdnet.com/... [Lemkin/Replit database deletion]
- OpenClaw GitHub PR #40508: fix — use atomic write for saveJsonFile to prevent JSON corruption (March 2026): https://github.com/openclaw/openclaw/pull/40508
- Facebook / Vibe Coding is Life group: Supabase security warnings should not be ignored (August 2025): https://www.facebook.com/groups/vibecodinglife/posts/1816111742310688/
