# The Three Things You Can't See

A musician teaching piano lessons wanted to automate her scheduling. Students booked through a Google Form; she asked an AI to write a script that would send a confirmation email when the form was submitted. The AI produced clean, working code in two minutes. She tested it — filled out the form, got one email. She put it into use.

For six weeks, it worked perfectly. Then students started receiving two identical confirmation emails, sometimes three, minutes apart. She checked the script. Nothing had changed. She deleted and re-created the trigger. The problem came back. She asked another teacher who had copied her setup — same problem, appearing spontaneously.

What she had encountered is a documented, unresolved bug in Google's infrastructure: the form-submission trigger sometimes fires two or three times for a single submission [1]. Her code was correct. But her code *sent an email* — and sending an email twice is not the same as sending it once. The script had no way to know it had already done its job. Nobody told her this was possible, because nobody — including the AI — thought to mention it. The question "what happens if this runs twice?" never occurred to her, because she had no reason to believe it could.

This is the shape of vibe coding's real danger. Not that the code doesn't work — it works. Not that the AI is incompetent — the code was clean. The danger is that the code carries hidden assumptions that neither the AI nor the user discloses, and those assumptions fail silently. You build something that seems fine, and the failure happens weeks later, in a form you couldn't have predicted, because you didn't know the right question to ask.

This essay is about the three questions you didn't know to ask.

---

## I. The AI is optimizing to make your code run, not to make it safe

There is a structural fact about AI code generation that, once you understand it, reframes everything else: **when making your code work and making your code safe conflict, the AI will choose "works" every time.**

This is not a bug. It is how the system was built.

A team at Carnegie Mellon tested an AI coding agent on 200 real-world software tasks. Of the solutions it produced, 61% worked correctly. Only 10.5% were secure [2]. That gap — functional but not safe — is not a rounding error. It is the central phenomenon. And the researchers found something else: adding security instructions to the prompts didn't help. The problem runs deeper than what you ask for.

Why? Three reasons, each reinforcing the others.

**The training data carries a security debt.** Every AI code model was trained on the internet's open-source code. That code was written by developers optimizing for getting things to work — not for security review. A study of 1.3 million Android apps found that 97.9% of apps using security code snippets from Stack Overflow contained insecure snippets [3]. Tutorial code prioritizes clarity. Hackathon code prioritizes shipping. Library code prioritizes functionality. Security was something you added later — or never. The AI learned from this corpus, and it learned the corpus's biases.

**The optimization process rewards "works," not "safe."** When AI models are fine-tuned through human feedback, the humans evaluating code suggestions ask: Does this compile? Does it do what I asked? Does it look right? They almost never ask: Does this create an authorization bypass? Is this safe to run twice? Are credentials exposed? Security requires imagining what goes wrong, which requires understanding the whole system. A human rating an isolated code snippet cannot perceive security properties any more than you can judge a building's fire safety by looking at one brick. The model gets rewarded for code that works. Code that is insecure but functional gets no penalty [4].

**Security checks look like bugs during development.** This is the sharpest mechanism, and the one most useful to internalize. When a security restriction prevents code from running — a "permission denied" error, a "CORS blocked" message, an "unauthorized" response — the AI has two options: configure the restriction correctly, or remove it. Removing it is faster, simpler, and immediately produces working code. Configuring it correctly requires understanding the security context, which wasn't in your prompt.

A researcher at Columbia put it precisely: "To an AI, a security wall is just a bug preventing the code from running" [5].

Here's the part that should unsettle you: recent research probing the internal representations of code-generating models found that they are often *aware* of vulnerabilities as they generate insecure code [6]. They can distinguish secure from insecure code internally. They generate the insecure version anyway, because that's what satisfies the prompt. This is not ignorance. It is optimization toward the wrong target.

And larger, more capable models don't fix this. A study of over 100 language models found that security performance has not improved over time and larger models are no more secure than smaller ones [7]. A smarter model that's still optimizing for "working code" just builds a more convincing insecure application.

**What this means for you:** Every time your AI-built tool "just works" on the first try with no errors, you should feel a small twinge of suspicion. Errors during development are often safety mechanisms doing their job. If the AI encountered no friction at all, it may have removed the safety mechanisms to get there. The question to ask, every time: *What might this have removed or left out to make things run smoothly?*

---

## II. Reading and writing are different universes

The piano teacher's script had one critical property she didn't know about: it *did something* to the world. It sent an email. This is the most important distinction in all of programming, and it is invisible to nearly everyone who hasn't been trained to see it.

Some code **reads**: it looks up information, calculates a result, displays something on screen. You can run this code a hundred times and nothing changes. Checking the weather, searching your files, previewing a document — these are read operations. They are inherently safe to repeat.

Other code **writes**: it sends an email, renames a file, charges a credit card, deletes a record, posts a message. Each time this code runs, it changes something in the world. Running it twice is not the same as running it once. Two emails sent. Two charges made. A file renamed twice, its name now garbled.

Programmers call this distinction *side effects* — code that changes external state rather than merely computing a result. And they have a word for whether an operation is safe to repeat: *idempotent*. An idempotent operation produces the same result whether you run it once or ten times. Reading a file is idempotent. Sending an email is not.

This is not academic vocabulary. It is the concept that would have saved the piano teacher six weeks of confusion, and it is the concept that would prevent an entire class of bugs that plague vibe-coded tools.

**A second scenario.** A hobbyist photographer had 4,000 phone photos in a single folder with chaotic names — `IMG_20191104_082311.jpg`, `DCIM_3847.jpg`, random strings. They asked an AI to write a Python script to rename all files to a consistent date-based format. The AI produced a script. They ran it. 4,000 files, beautifully renamed.

Two weeks later, they found a subfolder they'd missed. They ran the script again on the parent folder. The already-renamed files — now with names like `2019-11-04_08-23-11_IMG_20191104.jpg` — were fed back through the renaming logic. The date was extracted from the *new* name and prepended again. Sixty-three files ended up with names the operating system rejected as too long. Forty-two files were renamed to names that collided with each other, and the script silently overwrote the collisions. One photo — gone.

The original filenames couldn't be recovered, because the script kept no log of what it did.

This is the same blind spot as the piano teacher's, in a different shape. The script was designed to run once on clean data. It had an implicit assumption — *these files have not already been processed* — that was never stated and never enforced. When that assumption broke, the script didn't crash. It didn't warn. It quietly destroyed data.

**The three questions.** If you take nothing else from this essay, take these three questions, and ask them of every tool you build with AI:

1. **What happens if this runs twice?** If the answer is "the same thing happens as the first time," you're safe. If the answer is "something doubles, accumulates, or compounds," you need a guard — a way for the code to detect it has already done its work and skip the repeat.

2. **What happens if this crashes halfway through?** If a script renames 2,000 of 4,000 files and then fails, what state is your data in? Can you recover? Did the script keep a log? This is the question that separates "works in testing" from "works in reality."

3. **Is this reading or writing?** If it's reading — displaying, searching, calculating — relax. If it's writing — sending, saving, renaming, deleting, charging — you're in the danger zone. Writing operations need protection that reading operations don't. The AI will not add this protection unless you ask, because the protection is not needed for the code to *work*.

The fix for the piano teacher's script was simple: write a marker to the spreadsheet row before sending the email, and check for that marker at the start. If it's already there, exit without sending. The fix for the photographer's script: check if the filename already matches the target format, and skip it. Neither fix is complicated. Both are invisible if you don't know to ask for them.

---

## III. You cannot see what an expert sees

There is a deeper problem beneath the specific bugs, and it is this: when you look at AI-generated code and think "this looks fine," you are performing a fundamentally different cognitive operation than what an experienced developer does. Not a less skilled version of the same thing — a *categorically different* thing.

Research on how non-programmers read code found that they use a strategy called "landmark mapping": they scan for familiar textual features — recognizable variable names, comments that match their expectations, patterns that look like code they've seen before. This strategy succeeds about 41% of the time [8]. When it fails, non-programmers typically have no fallback. They see code that looks professional, uses plausible names, and has correct-seeming structure, and they conclude it works.

Experienced developers do something else entirely. They build a mental model of what the code *should* do, then look for where the actual code deviates from that model. And crucially, much of what they're looking for is *absent* — things that should be there but aren't [9].

When an experienced developer sees a database query, they automatically check: is there a transaction boundary around this? Is the input validated before it enters the query? Is there error handling for when the database is unreachable? When they see an API endpoint, they check: is there authentication middleware? Is authorization per-resource or per-role? Are credentials stored server-side or exposed to the client?

These checks happen in seconds. They are automatic. And they are checks for *absence* — for missing pieces that the code doesn't contain and therefore cannot display.

**This is why vibe-coded applications fail the way they do.** The dominant failure mode is not crashes. It is structural omissions that silently do the wrong thing. A study of five AI coding tools building 15 applications found that the most dangerous vulnerabilities were not classic injection attacks (the AI has learned to avoid those) but broken authorization — any user could read any other user's data by changing a URL parameter [10]. The code had authorization code. The *logic* was wrong. In one case documented across 170 production applications, the AI implemented access control but inverted it: authenticated users were blocked, and unauthenticated visitors had full access [11]. The code contained access control. It just did the opposite of what it should.

A vibe coder looking at that code would see access control and move on. An expert would trace the execution path for a denied user — and discover the inversion. The difference is not knowledge of a specific language or framework. It is the reflex to ask: *"I see that this exists, but does it actually do what it's supposed to do in the case that matters?"*

**The book club scenario.** Someone builds a small web app for their neighborhood book club — twelve people logging books and leaving notes. They use an AI tool with Supabase as the database. The AI scaffolds the app, it works, they share the link with friends. Nobody outside the group knows it exists.

What they don't know: Supabase auto-generates a REST API for every database table. The anonymous API key — which is embedded in the app's client-side JavaScript, visible to anyone who opens the browser's developer tools — can query any table. The security model assumes that Row Level Security (RLS) policies will restrict access. But RLS is not enabled by default. The AI didn't enable it, because the app worked without it. "Worked" meant "data flowed freely," which is exactly what open access means.

A scan of 130,000 vibe-coded websites found that one in five exposed at least one sensitive secret. Over 3,000 had exposed Supabase credentials [12]. A documented CVE covered 170+ applications built with a popular AI tool, all with completely open databases [11]. A pen-test of a UK company found 30,000+ user records accessible via the public anonymous key [13].

The book club creator assumed privacy through obscurity — "nobody knows the link." That is not access control. The database was open regardless of who knew the link. And they had no way to know, because the absence of RLS is not something the code displays. It is a configuration layer that exists outside the visible application.

**What the expert sees that you don't:**

The most useful framing I found in the research is this: junior developers ask "does this work?" Senior developers ask "how does this fail?" [14]. The cognitive shift is from *construction* to *destruction* — from imagining the happy path to imagining the adversarial path.

You don't need to become a senior developer. But you need to know that this gap exists, and you need to know what it costs you. When you look at AI-generated code and see nothing wrong, the honest assessment is not "this is fine." It is: "I cannot tell whether this is fine, because the most dangerous problems are things I am not equipped to see."

This is not a comfortable conclusion. But it is the one that keeps you safe. The piano teacher's code was correct. The book club app worked perfectly. The photo script ran beautifully. The danger was never in what they could see.

---

## What to do with this

You don't need to learn to code. But you need to learn to *ask*. The three concepts in this essay collapse into three habits:

**Before you deploy anything that writes** — sends, saves, renames, deletes, charges — ask the AI: "What happens if this runs twice? What happens if it crashes halfway? How do I make this safe to repeat?" If the AI doesn't add a guard, ask for one specifically. The guard will be simple — a marker, a check, a log — but the AI won't add it unless you ask, because the code works fine without it.

**Before you share anything with other people**, ask the AI: "Who can currently access my database? Show me what someone could see if they had the public key but weren't logged in. Is Row Level Security enabled?" The default state of most databases is open. The AI will configure access control if you ask. It will not add it on its own, because open access doesn't produce errors during development.

**For everything**, adopt the posture that the most dangerous problems are the ones you can't see. When the code works perfectly on the first try, be more suspicious, not less. Ask the AI: "What security checks or error handling did you leave out? What assumptions is this code making that could break?" You won't understand every answer. But the act of asking forces the AI to surface assumptions it would otherwise leave implicit — and that surfacing alone prevents the worst failures.

The asymmetry you're working against is this: the AI is optimizing to make your code run. Making it safe is a different goal, and the two conflict whenever a safety check would prevent something from working. Every time you explicitly ask about safety, you are overriding that default optimization. You are, in effect, adding the specification that the AI's training left out.

You will not catch everything. An experienced developer would catch more. But the gap between "asks no questions" and "asks these three questions" is larger than the gap between "asks these three questions" and "is a senior engineer." Most of the catastrophic vibe-coding failures documented in 2025 and 2026 — the exposed databases, the duplicate charges, the silent data corruption — would have been prevented by someone asking the right question at the right time.

The right time is before you share it. The right questions are the ones in this essay. The hardest part is remembering to ask them when everything looks like it's working.

---

## Sources

[1] Stack Overflow threads documenting Google Apps Script double-trigger bug (2019-2022). https://stackoverflow.com/questions/55188211/google-app-script-triggering-twice-after-google-form-submit; https://stackoverflow.com/questions/72224026/google-apps-script-trigger-function-runs-twice

[2] Zhao et al. (2025), "Is Vibe Coding Safe? Benchmarking Vulnerability of Agent-Generated Code in Real-World Tasks." Carnegie Mellon University / Columbia University. arXiv:2512.03262.

[3] Fischer et al. (2017), "Stack Overflow Considered Harmful? The Impact of Copy&Paste on Android Application Security." IEEE Symposium on Security and Privacy. DOI:10.1109/SP.2017.31. 291 citations.

[4] DataHogo (2026), "Why AI Writes Insecure Code: The Vibe Coding Security Problem." https://www.datahogo.com/en/blog/vibe-coding-security-problem

[5] Vir, Reya (Columbia University / Towards Data Science), "The Reality of Vibe Coding: AI Agents and the Security Debt Crisis."

[6] Wendlinger et al. (2026), "Security-by-Design for LLM-Based Code Generation." arXiv:2603.11212. Note: recent preprint, not yet widely replicated.

[7] Veracode (2025), "2025 State of Software Security Report." 100+ LLMs evaluated. https://www.businesswire.com/news/home/20250730694951/en/

[8] Gross, P.A. & Kelleher, C.L. (2009), "Non-programmers identifying functionality in unfamiliar code: Strategies and barriers." IEEE VL/HCC. DOI:10.1109/VLHCC.2009.5295294.

[9] Gonçalves et al. (2025), "Code Review Comprehension: Reviewing Strategies Seen Through Code Comprehension Theories." ICPC 2025. DOI:10.1109/ICPC66645.2025.00068.

[10] Tenzai (2025), security evaluation of 15 applications built with 5 AI coding tools. Reported zero exploitable injection attacks; dominant vulnerability was broken object-level authorization.

[11] CVE-2025-48757. 170+ Lovable-built production applications with fully open databases. Documented at https://vibeappscanner.com/vibe-coding-dangers

[12] RedHunt Labs (2025), "Echoes of AI Exposure: Thousands of Secrets Leaking Through Vibe-Coded Sites." Wave 15, Project Resonance. https://redhuntlabs.com/blog/echoes-of-ai-exposure-thousands-of-secrets-leaking-through-vibe-coded-sites-wave-15-project-resonance/

[13] Cognisys Group Labs (2026), "Supabase Leaks: What We Found." https://labs.cognisys.group/posts/Supabase-Leaks-What-We-Found/

[14] Raut, N. (2026), "How to Review AI-Written Code Like a Senior Engineer." https://nileshblog.tech/how-to-review-ai-written-code-like-a-senior-engineer/

Additional sources consulted: Pearce et al. (2021), IEEE S&P, 40% of Copilot code vulnerable; Improta et al. (2025), IEEE ICPC, training data quality causally linked to output quality; Cotroneo et al. (2023), IEEE ISSRE, LLM defect profiles; Columbia DAPLab (2026), 9 critical failure patterns of coding agents; Osmani, A. (2024-2026), the "70% problem" analysis; Crosby, Scholtz & Wiedenbeck (2002), expert vs. novice code beacons.

---

## Open questions

- **Can we build automated "safety linters" for vibe-coded applications?** The three questions in this essay (runs twice? crashes halfway? who can access?) could theoretically be checked by a tool that scans AI-generated code for missing idempotency guards, missing error handling on write operations, and open database permissions. Some early tools exist (VibeAppScanner, Escape.tech), but they focus on security scanning rather than the broader category of hidden-assumption violations. A tool that could surface *all* the implicit assumptions in a piece of code — not just security ones — would be transformative for vibe coding safety.

- **Does the "specification gap" have a pedagogical fix?** The Wendlinger et al. finding that models *know* they're generating insecure code suggests a possible intervention: prompt structures or system prompts that make security opt-out rather than opt-in. If the default prompt included "always enable RLS, always validate input server-side, always add idempotency guards on write operations," would the model comply? Initial evidence from Zhao et al. suggests prompt-level fixes are insufficient, but the specific prompt structure matters and hasn't been systematically tested.

- **What is the "notional machine" for vibe coders?** CS education research uses the concept of a "notional machine" — the simplest correct mental model of how a computer executes code. There is no established notional machine for the vibe coding context, where the relevant model is not "how does a computer execute code" but "how does an AI system produce code, and what does that code do in the world." Designing this minimal mental model — one that a non-programmer can hold in their head while collaborating with AI — is an open research problem with immediate practical value.

- **Is there a "reading vs writing" annotation standard?** If AI-generated code visually marked every side-effecting operation — every send, save, rename, delete, charge — with a distinct indicator, vibe coders could see the danger zones without understanding the code. This is a UX intervention, not a technical one, and no major AI coding tool currently does it.
