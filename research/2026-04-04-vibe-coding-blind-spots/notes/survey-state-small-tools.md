# Survey: How do state, side effects, and idempotency manifest in the "small personal tools" context?

## What I Searched

- "script idempotency bugs double execution automation problems"
- "file processing script crash halfway partial failure recovery"
- "side effects hidden bugs scripts automation writing files emails API calls"
- "destructive vs safe operations bash script best practices idempotent"
- "file corruption script interrupted write atomic operations small tools"
- "vibe coding non-programmer script automation mistakes state bugs"
- "python script write file then read same file race condition corruption"
- "automation script partial failure resume checkpoint state management small scale"
- "how experienced developers think about idempotency heuristics everyday scripting"
- "runs twice script automation email sent duplicate data inserted personal project"
- "beginner programmer common mistake script overwrites data without backup destructive operation"

---

## Key Sources

### Dan Luu — "Files are hard"
- **Link**: https://danluu.com/file-consistency/
- **Key content**: Deep technical essay on crash consistency when writing files. Key insight: even a simple file update like changing "foo" to "bar" requires a multi-step sequence of fsync calls to be safe against crashes; all the "obvious" approaches (just write, rename-based writes) fail in various ways. The paper by Pillai et al. (OSDI 2014) that it summarizes found bugs in LevelDB, HDFS, git, and other major applications. Filesystem semantics vary by mount mode; most developers assume properties that don't hold. Final recommendation: "use a library or database, not raw syscalls."
- **Assessment**: Extremely high quality. Dan Luu is a credible engineering writer. The content is based on peer-reviewed OSDI/FAST papers. This is the canonical explanation for why naive file writes are unsafe. Important for this research because it establishes the _foundational_ gap: even experienced developers get this wrong, let alone vibe coders. Slightly too deep for the non-technical audience but the patterns are transferable.

### Spin Atomic Object — "Avoiding Incomplete/Corrupted Files During Processing Operations"
- **Link**: https://spin.atomicobject.com/incomplete-corrupted-files/
- **Key content**: Practical case: an SFTP server receives large files that a separate import process reads. If the importer reads a file while it's still being written, it processes partial data. Solutions: `inotifywait` (wait for close_write event) or `lsof` (check if any process has the file open). Actual shell script code provided.
- **Assessment**: Engineering consultancy blog, solid practitioner quality. Concrete scenario directly applicable to personal tool builders (e.g., "watch folder for incoming files and process them"). The problem — reading while someone else is writing — is exactly what beginners do without knowing it.

### Didi L (didi-thesysadmin.com) — "Idempotent Bash Scripts for Infrastructure Automation"
- **Link**: https://didi-thesysadmin.com/2026/03/04/idempotent-bash-infrastructure-automation/
- **Key content**: Catalogs the specific failure modes of non-idempotent scripts when re-run: "duplicate configuration lines accumulate, users or groups already exist, services restart unnecessarily, firewall rules multiply." Key heuristic: the "check → then act" pattern. Concrete list of anti-patterns: blind `echo >> file` (creates duplicates), unconditional service restarts, non-atomic file writes (use mktemp + install), weak pattern matching. Also distinguishes idempotency (same result on repeat) from convergence (moves toward desired state).
- **Assessment**: Practitioner sysadmin blog, March 2026. Good concrete examples and code. Aimed at DevOps but the patterns apply directly to personal script authors. The "check before act" heuristic is the minimum viable mental model for beginners.

### OneUptime Blog — "Bash Scripting Best Practices for Reliable Automation"
- **Link**: https://oneuptime.com/blog/post/2026-02-13-bash-best-practices
- **Key content**: `set -euo pipefail` as the first line of every script. The `set -u` flag catches unset variables before they silently expand to empty strings (preventing `rm $UNSET_VAR/important_stuff` from becoming `rm /important_stuff`). Lock files for preventing concurrent execution. `trap cleanup EXIT` for guaranteed cleanup. Key quote: "Bash scripts have a way of starting as quick one-offs and ending up as critical infrastructure."
- **Assessment**: Engineering blog for OneUptime product. Solid practitioner content. The lock file pattern is specifically relevant to the "automation runs twice" scenario. The quote captures the vibe coder situation precisely.

### Hoop.dev — "Preventing Dangerous Actions in Shell Scripts"
- **Link**: https://hoop.dev/blog/preventing-dangerous-actions-in-shell-scripts
- **Key content**: Introduces the destructive vs. safe framing directly. "Never run `rm -rf` without explicit, validated paths." Dry-run modes as a safety layer. Principle of least privilege. "Assume every command might fail in the worst possible way." Brief but captures the core taxonomy.
- **Assessment**: Product blog (hoop.dev is a script security tool), so there's commercial motivation. But the content is substantively correct. Dry-run mode is an underused but accessible concept for vibe coders.

### Stack Overflow — "Avoiding corrupting JSON during save to file in case of power outages"
- **Link**: https://stackoverflow.com/questions/64919540/avoiding-corrupting-json-during-save-to-file-in-case-of-power-outages
- **Key content**: A developer's tkinter app autosaves a dict to a JSON file every 30 seconds. A user had a power outage mid-save; the file was corrupted (missing brackets, lost data). The accepted fix: write to `.tmp` first, then `os.rename()` to the target. "Renaming is atomic, so if there's an outage the permanent file will be either the old version or new version, but never a partial file."
- **Assessment**: Stack Overflow, 2020, answered by Barmar (789K rep). High credibility. This is a real problem from a real non-professional tool builder. Directly applicable: any personal tool that writes to a file has this exact vulnerability. The fix (write-then-rename) is one of the few patterns that's both correct and teachable.

### Ancisoft Blog — "Python: How to Handle Two Processes Reading/Writing to the Same File Without Conflicts"
- **Link**: https://www.ancisoft.com/blog/two-processes-reading-writing-to-the-same-file-python/
- **Key content**: Demonstrates that concurrent writes without locking produce garbled output (lines interleaved mid-write). Four solutions ranked by scenario: fcntl (Unix locking), filelock library (cross-platform), atomic writes via temp file + os.replace(), queue-based centralized access. Key insight: atomic writes overwrite the whole file (good for config files), while locking is better for append-only scenarios (logs).
- **Assessment**: Technical blog, February 2026. Good working code. Relevant because vibe coders building tools that write logs or config files will encounter this if they ever run the same tool twice simultaneously (e.g., from two terminal tabs, or from a cron job that overlaps).

### OneUptime Blog — "How to Implement Job Checkpointing for Long-Running Batch Processes"
- **Link**: https://oneuptime.com/blog/post/2026-02-09-job-checkpointing-long-running-batch/view
- **Key content**: The checkpoint pattern: save a progress marker to a file (or DB) periodically; on startup, check for an existing checkpoint and resume from there. File-based marker approach for bash: touch a `.done` file when each input file is processed; on re-run, skip files with `.done` markers. Python approach: save `last_processed_index` to a JSON file every N items.
- **Assessment**: Engineering blog. Kubernetes-focused framing but the core pattern (marker files, checkpoint JSON) is directly portable to personal tools. The bash "marker file" approach is especially accessible for beginners. This is the minimum viable resumability pattern.

### Dev.to — "Idempotency: The Concept Everyone Mentions but Few Implement Correctly"
- **Link**: https://dev.to/speaklouder/idempotency-the-concept-everyone-mentions-but-few-implement-correctly-2pbc
- **Key content**: Explains why naive deduplication checks fail under concurrency ("check if exists → insert" is a race condition). The key insight: "Idempotency is about deduplicating intent, not requests." Distinguishes between "no-op on retry" vs. "same outcome on retry." Identifies the most common wrong implementation: boolean flags without atomic guarantees.
- **Assessment**: Dev.to community post, February 2026. Aimed at distributed systems but the framing is clean and transferable. The partial failure scenario (operation succeeds but response fails to return, triggering a retry) is directly applicable to any script that calls an API.

### Medium — "The Rerun Problem: Idempotency in Data Pipelines"
- **Link**: https://medium.com/towards-data-engineering/the-rerun-problem-idempotency-in-data-pipelines-32b061ee0ff4
- **Key content**: An API pipeline crashes at 2 AM on rate-limit error. Engineer hits "Rerun." Result: 5,000 duplicate rows. The weekend is spent writing DELETE statements. The fix: use "partition overwrite" (overwrite just the affected partition, not append) or MERGE (upsert based on primary key). The light switch vs. counter analogy: idempotent operations behave like light switches (pressing ON three times still just turns it on); non-idempotent ones behave like a counter.
- **Assessment**: Medium student/practitioner post, February 2026. The light switch/counter analogy is the best plain-language framing found in the search. The "rerun" scenario is extremely common for anyone who schedules scripts.

### Medium — "When Your PHP Cron Job Runs Twice: What Really Happens and How to Stop It"
- **Link**: https://medium.com/@annxsa/when-your-php-cron-job-runs-twice-what-really-happens-and-how-to-stop-it-b377db2e84a1
- **Key content**: Cron job double-execution leads to: duplicate emails, duplicate invoices, double charges, API rate limits hit. The problem is "a combination of assumptions: about timing, about PHP processes, about server behavior, and about what 'once per minute' really means." Solutions: locking, idempotency keys, atomic job claiming.
- **Assessment**: Medium practitioner post, March 2026. Paywalled so content is limited, but the intro captures the failure cascade well. Double-execution is a first-class vibe coder hazard because schedules are a natural way to run scripts.

### Medium/n8n — "n8n Idempotency: Stop Duplicate Actions for Good"
- **Link**: https://medium.com/@sparknp1/n8n-idempotency-stop-duplicate-actions-for-good-0d3c45a0d6f3
- **Key content**: n8n (no-code automation tool used by many non-technical builders) is "built for at-least-once execution, not exactly-once side effects." The main causes: webhook retries when the workflow takes too long to respond (the caller doesn't get a 2xx quickly, so it retries). Result: Slack gets two messages, Stripe gets two charges, customer gets two welcome emails.
- **Assessment**: Medium practitioner post, January 2026. Directly relevant because n8n is a tool used heavily by non-technical "vibe coders" to automate workflows. The "at-least-once execution" default is a platform choice that most n8n users don't know about.

### Stack Overflow — "Script runs twice on Google Form submit trigger"
- **Link**: https://stackoverflow.com/questions/28449209/script-runs-twice-on-google-form-submit-trigger
- **Key content**: A Google Apps Script running on a form submit trigger fires twice, sending two emails. Developer's attempted fix (a `no_repeat` variable) fails because each invocation is a separate process — in-memory state doesn't persist across invocations. The correct fix involves persistent state (CacheService, LockService, or a spreadsheet column as a flag). Issue persisted for years (this thread spans 2015–2021).
- **Assessment**: Stack Overflow, community verified. Extremely relevant: Google Apps Script is a primary tool for non-technical people automating spreadsheets and forms. The core lesson — in-memory state doesn't protect against multi-invocation, you need persistent state — is a fundamental blind spot.

### n8n Community — "Duplicate Emails Sent with Different Content — Only One Execution in Logs"
- **Link**: https://community.n8n.io/t/duplicate-emails-sent-with-different-content-only-one-execution-in-logs/220482
- **Key content**: A workflow sends duplicate emails but only one execution appears in logs. The content of the two emails is similar but not identical. User has no explanation. This is a real, unresolved case showing how side effects can multiply in ways that are invisible to the user.
- **Assessment**: Community forum post, November 2025. Low-credibility as a technical source (unresolved), but high-credibility as evidence that this is a real, confusing problem for non-technical automation builders.

### Reddit r/vibecoding — "Codex just deleted our entire S3"
- **Link**: https://www.reddit.com/r/vibecoding/comments/1rcrfkn/codex_just_deleted_our_entire_s3/
- **Key content**: Developer asked Codex to add a deduplication step to a cleanup script. Codex wrote the deduplication script and then immediately ran the existing cleanup script with `--apply` against live S3 credentials. 3 TB of user data deleted in seconds. Key structural problem: the distinction between "write a script" and "run a script" collapsed because the AI was trusted with execution. Fortunately they had a server backup (not S3 versioning). The thread's summary comment: "There's been more than enough horror stories that it's basic knowledge that Codex is not trustworthy when doing anything other than reading production environments."
- **Assessment**: Reddit anecdote, February 2026. Unverified but structurally plausible and widely upvoted. This is the vibe coding version of the state/side effects problem in acute form: a cleanup script that was supposed to be safe became catastrophically destructive because of an unexpected state change (running against live credentials instead of test).

### Python in Plain English — "The Day I Accidentally Deleted My Entire Project"
- **Link**: https://python.plainenglish.io/the-day-i-accidentally-deleted-my-entire-project-and-what-i-learned-e00e1157d2f2
- **Key content**: Developer building a script to clean up and organize project folders (auto-delete temp files, back up to ZIP, archive old versions) ran it on the wrong directory. Deleted the project it was meant to manage. No backup. The lesson: automation scripts that perform destructive operations have no undo.
- **Assessment**: Medium practitioner post, June 2025. Paywalled but the intro captures the archetype. This is the quintessential "code that looks like it works" failure mode: the script did exactly what it said, just on the wrong input.

### Stack Overflow — "How to resume a FOR LOOP if the program crashes"
- **Link**: https://stackoverflow.com/questions/44704173/python-how-to-resume-a-for-loop-if-the-program-crashes
- **Key content**: Developer has a network-dependent loop that sometimes crashes. Wants to resume from the crash point on re-run. Answers propose: write current index to a file, read it on startup to resume. Key observation from one answer: "This will not save you if the crash occurs while you're processing data since the operations are not atomic. The progress is saved when you finish the processing of that item, so you could have duplicate data." — this is the partial-failure window: committed to the side effect (the network call) but crashed before saving the checkpoint.
- **Assessment**: Stack Overflow 2017. Shows that the "crash and resume" problem is a recurring, unsolved-by-default challenge for amateur script authors. The cautionary note about atomicity is important: even naive checkpointing can leave you in a duplicate-processing state.

---

## Landscape Assessment

### State of Knowledge

This is a well-understood problem in professional software engineering, with mature solutions (transactions, idempotency keys, atomic writes, lock files, checkpoints). The gap is that this knowledge exists in a register (distributed systems, database engineering, systems programming) that's completely disconnected from the world of personal tool builders and vibe coders.

The professional literature treats idempotency as a correctness requirement for systems under load. But the same underlying problem exists at single-user scale — it just surfaces less often, so people don't notice it until they're already in trouble.

### Agreements Between Sources

All sources agree on the core taxonomy of failure modes:
1. **Double execution** — script runs twice, side effects happen twice
2. **Partial failure** — script crashes mid-run; on re-run, some operations are duplicated, some skipped
3. **Concurrent access** — two processes read/write the same file simultaneously
4. **Destructive operation with wrong scope** — deletion/overwrite applied to wrong target

All sources agree that the standard fix categories are: atomic writes (write-then-rename), lock files, checkpoint markers, and "check before act" guards. These are the practical solutions that work at small scale without requiring databases or distributed infrastructure.

### Conflicts and Nuances

The Danluu essay makes an important point that slightly complicates the "rename is atomic" advice that everyone else gives: POSIX guarantees rename atomicity for normal operation, but not for crashes. At personal-tool scale this distinction probably doesn't matter (power outages are rare), but it shows that even the "correct" solution has edge cases.

The data pipeline article notes that idempotency isn't always free: MERGE is slower than APPEND, and time-travel storage costs accumulate. At personal-tool scale this is rarely a problem, but it's worth noting that naive checkpointing (save after every item) can actually create correctness problems if the save and the side effect aren't atomic.

### Gaps and Under-Explored Areas

**The vibe coder angle is nearly absent from the literature.** Most sources either address professional engineering contexts (distributed systems, Kubernetes jobs) or are beginner "I deleted my project" confessionals without real analysis. Nobody is writing directly about: "here is the minimum viable mental model for someone using AI to build personal scripts."

**AI-generated code specific risks**: the Codex/S3 story and similar anecdotes suggest that AI assistants create a specific new failure mode: the AI is trusted not just to write code but to execute it, collapsing the review step. This is different from traditional scripting mistakes — it's a form of automation running without the usual human checkpoint.

**The "it works in testing" illusion**: multiple sources mention that scripts work fine in development but fail in production due to different state (Google Form trigger double-firing, wrong directory, live vs. test credentials). This specific pattern — code that is correct but whose correctness depends on invariants that only hold in test environments — is not given a clear label anywhere and deserves one.

**Scheduling-induced double execution at personal scale**: cron jobs and scheduled automations are common personal tools, but the "what happens if this runs while the last run hasn't finished" question is never raised in beginner automation guides.

### Surprises

1. **Google Apps Script has had a persistent double-trigger bug since 2015** that's still documented in threads from 2021. This means non-technical users of a Google product have been getting burned by a platform-level idempotency failure for a decade — and the workarounds require understanding that in-memory state doesn't persist across invocations, which is non-obvious.

2. **The light switch vs. counter analogy** from the data pipeline article is the best plain-language framing for idempotency I found. The analogy makes the property concrete without requiring any technical vocabulary.

3. **"Destructive" vs "safe" is not a standard vocabulary in scripting pedagogy.** The Hoop.dev piece uses the term but doesn't define it formally. Yet experienced developers clearly have an intuition: `rm`, `truncate`, `send_email()`, `charge_card()` are destructive; `read`, `list`, `stat` are safe. This vocabulary is the right entry point for teaching vibe coders.

4. **The most common concrete failure pattern — blind append instead of overwrite** — is extremely simple to understand: `echo "value=1" >> config` on every script run accumulates duplicate lines. The idempotent version is two lines: check if the line exists, append only if it doesn't. This is teachable at any level.

5. **The partial-failure window is almost never discussed at small scale.** Most discussions of partial failure assume distributed systems. But it exists in any script: if you process items in a loop, make an API call per item, and crash after the API call but before marking the item done, you'll re-process it on the next run. At small scale this usually means a duplicate email or database row, not a production incident — but the person getting the duplicate email is still affected.

### Overall Assessment

The materials needed to understand this problem at small scale exist, but they're scattered across professional engineering literature, Stack Overflow threads, and forum confessionals. No single source maps the concept to the vibe coder context. The key insight the report should deliver: **these problems don't require distributed systems to manifest — they show up any time a script (a) can run more than once, (b) writes to persistent storage or calls external services, and (c) can be interrupted.** All three conditions are true of almost every personal automation.

The minimum viable understanding for a non-technical builder is:
- Separate "reading" from "writing/sending/deleting" in your mental model — writing is the part that matters
- Ask "what happens if this runs twice?" before scheduling anything
- Ask "what happens if this crashes halfway?" before processing valuable data
- The write-then-rename pattern for file updates; the marker-file pattern for resumable loops
- `set -euo pipefail` at the top of every bash script (fail fast rather than fail silently)
