# Survey: What engineering concepts have the highest "danger-to-invisibility ratio" for non-technical AI users?

## Summary

This is a surprisingly well-documented problem — but documentation is scattered across security research, developer experience writing, and a growing body of vibe-coding-specific post-mortems. The core finding is strong and consistent: AI coding tools are trained to produce functional code, not secure or reliable code. They optimize for "does this run?" not "does this survive contact with real users, bad inputs, or retries?" The gap between those two things is exactly what kills vibe-coded apps in production.

The highest-danger-to-invisibility concepts cluster into three zones: (1) secrets and credentials, where the failure is immediate and often automated-attacker-triggered; (2) authorization logic, where the failure is structural and only surfaces under adversarial conditions; and (3) state/transaction management, where the failure looks like normal behavior until data corruption accumulates. There is strong empirical backing for these rankings from Veracode (100+ LLMs analyzed), Tenzai (5 tools, 15 apps), Escape.tech (5,600 live apps), and the MITRE CWE Top 25 list.

What I did not expect: the research confirms that larger, more capable LLMs are not meaningfully more secure. Veracode found no correlation between model size and security output. This means vibe coders using frontier models are not protected by model quality — the problem is structural, not a matter of which AI they're using.

---

## What I Searched

1. "vibe coding security vulnerabilities AI-generated code dangers non-technical users"
2. "what every developer should know fundamentals beginners often miss"
3. Academic papers on AI-generated code security (Semantic Scholar, 2022–2025)
4. "vibe coding risks mistakes non-programmers building apps AI 2024 2025"
5. "secrets management API keys hardcoded environment variables security mistakes beginners"
6. "SQL injection input validation AI code generation OWASP top 10 web app security"
7. Academic papers on novice programmer misconceptions (Semantic Scholar, 2018–2025)
8. "race conditions concurrency bugs web applications beginners don't understand"
9. "idempotency database transactions atomicity explained developers importance"
10. "CWE common weakness enumeration most dangerous software mistakes top list 2025"
11. "mentoring non-technical people who code what concepts they miss"
12. "git version control data loss beginners mistakes irreversible actions"
13. "authorization vs authentication confused beginners IDOR broken access control"
14. "database schema migration production irreversible data loss app developer mistakes"
15. Veracode 2025 GenAI Code Security Report
16. OWASP LLM Top 10 for 2025

---

## Key Sources

### The 70% Problem: Hard Truths About AI-Assisted Coding (Addy Osmani, Substack, Dec 2024)
- **Link**: https://addyo.substack.com/p/the-70-problem-hard-truths-about
- **Key content**: Senior Google engineer identifies a "knowledge paradox" — AI tools help experienced developers more than beginners because experienced developers apply "years of hard-won engineering wisdom to shape and constrain the AI's output." Non-engineers hit the 70% wall: prototype works, but the final 30% (edge cases, error handling, security) requires real engineering knowledge. The "two steps back" pattern: fix one bug with AI, it breaks something else, repeat. Non-engineers lack the mental models to understand what's actually going wrong.
- **Assessment**: High-quality practitioner experience from a credible source. Not peer-reviewed but extensively cited in the discourse. Identifies what concepts are missing without naming them precisely — useful for triangulation.

### Why AI Writes Insecure Code: The Vibe Coding Security Problem (DataHogo, April 2026)
- **Link**: https://www.datahogo.com/en/blog/vibe-coding-security-problem
- **Key content**: Explains the structural roots of AI security failures: (1) training data was full of insecure code because open-source historically prioritized functionality; (2) RLHF optimizes for "code developers approve" not "code that's secure" — developers catch syntax errors but not authorization flaws; (3) the context window problem: AI sees a few files, not your full auth stack, middleware, and threat model; (4) "happy path bias" — AI generates code for the world as described, not for adversarial inputs. Most important line: "Security is a system-level property. A route is secure or insecure not just based on its own code, but based on how it interacts with auth middleware, database policies, and every other part of the system."
- **Assessment**: Vendor content (they sell a scanner) but the structural analysis is rigorous and well-sourced. Cites Veracode 2025 data (45% of AI code has vulnerabilities).

### Vibe Coding Is Leaking Vulnerabilities Into Your Codebase (LindleyLabs, April 2026)
- **Link**: https://lindleylabs.com/blog/vibe-coding-is-leaking-vulnerabilities-into-your-codebase
- **Key content**: Reports Moltbook incident (AI-only social network, Wiz found 1.5M API tokens and 35K email addresses exposed — founder had written zero lines of code himself). Tenzai study: 5 AI coding tools, 15 apps — 69 vulnerabilities found; every tool introduced SSRF; no app built CSRF protection; no app set security headers. Escape.tech: 5,600 live vibe-coded apps — 2,000+ vulnerabilities, 400+ exposed secrets, 175 instances of PII (medical records, IBANs) accessible via public endpoints. Carnegie Mellon stat: 61% of AI-generated code is functionally correct, only 10.5% is secure. Lovable CVE-2025-48757: 170/1,645 scanned apps had Supabase service keys in frontend bundles (distinguishing anon key from service key requires security knowledge invisible in vibe coding workflow). Key code example of IDOR pattern — user ID taken from request parameter rather than session.
- **Assessment**: Well-sourced practitioner article with real incident data and specific CVE. The Tenzai and Escape.tech figures are striking and specific enough to be investigable. Published April 2026, most current source found.

### Vibe Coding Problems: Why Your App Breaks in Production (Modall/Jake Randall, March 2026)
- **Link**: https://modall.ca/blog/vibe-coded-app-breaks-production
- **Key content**: Comprehensive catalog of 8 production failure modes in vibe-coded apps: (1) missing error handling; (2) no auth hardening; (3) hardcoded secrets; (4) silent failures (app appears to work, database write fails silently); (5) zero test coverage; (6) environment mismatches (works locally, fails in production); (7) no database indexing (works with 100 rows, breaks with 10,000); (8) missing rate limiting. CodeRabbit analysis of 470 OSS PRs: AI-generated code had 1.7x more issues overall, security vulnerabilities 2.74x higher, performance inefficiencies 8x more frequent. Columbia University DAPLab: error handling identified as most serious and most common failure mode because failures are often silent.
- **Assessment**: Consulting firm with commercial interest, but the taxonomy is well-supported and matches other sources. CodeRabbit citation is verifiable (December 2025 study).

### Veracode 2025 GenAI Code Security Report (Business Wire press release, July 2025)
- **Link**: https://www.businesswire.com/news/home/20250730694951/en/AI-Generated-Code-Poses-Major-Security-Risks-in-Nearly-Half-of-All-Development-Tasks-Veracode-Research-Reveals
- **Key content**: Analyzed 80 coding tasks across 100+ LLMs. Key findings: AI introduced OWASP Top 10 vulnerabilities in 45% of all test cases. Java: failure rate over 70%; Python/C#/JavaScript: 38-45%. LLMs failed to defend against XSS (CWE-80) in 86% of cases and log injection (CWE-117) in 88% of cases. Critical finding: "Security performance has not kept up [with functional quality], remaining unchanged over time." Larger models do not perform significantly better than smaller ones — suggesting a "systemic issue rather than an LLM scaling problem."
- **Assessment**: Most rigorous empirical study found. Veracode is a reputable security company, methodology is documented (80 CWE-specific coding tasks, Veracode Static Analysis for evaluation). The finding that larger models are no more secure is important and counterintuitive.

### 2025 CWE Top 25 Most Dangerous Software Weaknesses (MITRE, December 2025)
- **Link**: https://cwe.mitre.org/top25/archive/2025/2025_cwe_top25.html
- **Key content**: Official ranked list, CVE-backed. Top 5: (1) Cross-site Scripting CWE-79; (2) SQL Injection CWE-89; (3) CSRF CWE-352; (4) Missing Authorization CWE-862 (up 5 positions from 2024); (5) Out-of-bounds Write CWE-787. For web app context: also notable are Path Traversal (#6), OS Command Injection (#9), Unrestricted File Upload (#12), Deserialization of Untrusted Data (#15), Missing Authentication for Critical Function (#21, up 4 positions), SSRF (#22), Authorization Bypass Through User-Controlled Key (#24, up 6 positions). Missing Authorization rising 5 positions is notable — consistent with "AI generates routes that look correct in isolation but lack auth checks."
- **Assessment**: Authoritative. Government-backed (CISA endorses). Derived from actual CVEs in real software. The most trustworthy ranking of actual software weaknesses by real-world harm.

### Human-Written vs. AI-Generated Code: Large-Scale Study of Defects, Vulnerabilities, and Complexity (Cotroneo, Improta, Liguori, IEEE ISSRE 2025)
- **Link**: Semantic Scholar: https://www.semanticscholar.org/paper/c912b74b15dc2ea2a6dd2298e203c1e9964198b6
- **Key content**: 500K+ code samples (Python and Java), comparing human vs. AI (ChatGPT, DeepSeek-Coder, Qwen-Coder). AI-generated code: generally simpler and more repetitive, more prone to unused constructs and hardcoded debugging; AI code contains more high-risk security vulnerabilities. Human-written code: greater structural complexity, higher concentration of maintainability issues. "Distinct defect profiles" — the problems are systematically different, not just quantitatively more.
- **Assessment**: Peer-reviewed, IEEE ISSRE (respectable venue), large dataset, 12 citations. One of the most rigorous comparative studies found.

### Race Condition Vulnerability: A Complete Beginner-Friendly Guide (LocalHostVicky, Jan 2026)
- **Link**: https://localhostvicky.com/race-condition-vulnerability-a-complete-beginner-friendly-guide/
- **Key content**: Good explanation of why race conditions are hard to detect: "They depend on timing. A system may appear secure during normal testing but fail under high traffic or deliberate stress." Key attack patterns: TOCTOU (time-of-check to time-of-use), concurrent database writes (votes, coupon redemption, account balances). Affects voting/like systems, coupon redemption, e-commerce checkout, password reset — exactly the kinds of systems vibe coders build.
- **Assessment**: Blog post, no particular authority, but useful for understanding why race conditions are invisible in vibe-coding workflows. Consistent with academic and security literature.

### Stop Double-Charging Your Users: The Senior Engineer's Guide to API Idempotency (Medium, March 2026)
- **Link**: https://medium.com/@neeteshraj/stop-double-charging-your-users-the-senior-engineers-guide-to-api-idempotency-ad17300aceef
- **Key content**: Concrete illustration of why idempotency matters: user clicks checkout, backend charges Stripe, WiFi drops, frontend retries, user gets double-charged. The correct mental model: "You cannot control the chaos of the network." Non-idempotent POST operations with retry logic create real financial harm. The fix requires atomic Redis locks and server-side idempotency keys — concepts genuinely non-obvious from "make the checkout work."
- **Assessment**: Practitioner blog post. Useful for its vivid concrete example, not as an authoritative source. The pattern it describes is textbook.

### Mentoring Junior Developers in the Age of AI: The Silent Silo (NotTheCode, Dec 2025)
- **Link**: https://notthecode.com/silent-silo-mentoring-junior-developers-ai/
- **Key content**: Identifies "conceptual debt" from AI coding: "knowledge stops circulating, design weakens in places no one notices." Cargo cult coding: "copies a pattern because it 'looks right' — trusts the shape of the solution instead of the reasoning behind it." Key missing knowledge: permission models, tenancy boundaries, audit requirements, "subtle constraints baked into your domain." Models generate code "secure in a theoretical sense, not in the reality of your system." Most important observation: juniors who produce AI code at speed cannot retrace the logic when something breaks — because they never built it in the first place.
- **Assessment**: Well-written practitioner piece. Describes the problem from the mentorship angle and identifies the gap precisely: system context, tenancy, permission models.

### I Deployed Without Migrations. 400K Users Saw Blank Pages. (Medium / Code War, March 2026)
- **Link**: https://medium.com/lets-code-future/i-deployed-without-migrations-400k-users-saw-blank-pages-this-script-saved-us-c541654cbcce
- **Key content**: First-person account of deploying code that expected a database schema that hadn't been migrated yet. 400,000 users saw blank pages, revenue $0 for 21 minutes, $7,140 lost. The failure mode: code deploys and database schema changes are two separate operations that must be sequenced. Backfill migrations on large tables (2.4M rows) take 11 minutes — fine at 3am, catastrophic at 4:52pm Friday. Key lesson: "I assumed the code would work. I was overconfident." The database migration problem is especially relevant for vibe coders because AI will write schema changes and application code in the same session without flagging the deployment dependency.
- **Assessment**: Practitioner narrative. Well-told and specific. The underlying failure mode is very real and would be completely invisible to a vibe coder. Low authority but high relevance.

### Error Handling Strategies — Defensive Programming (Agent Factory / Panaversity, March 2026)
- **Link**: https://agentfactory.panaversity.org/docs/Programming-in-the-AI-Era/exception-handling/error-handling-strategies
- **Key content**: Educational resource aimed at AI-era programmers. Identifies four strategies: retry (transient errors), fallback (permanent errors), graceful degradation (non-critical features), logging (all errors). Key insight for our purposes: "Professional developers don't just catch errors and move on. They think strategically: What kind of error is this? Is it temporary? Can I recover? Should I notify the user? What should I log?" This is exactly the mental model that vibe coders don't have — they know how to wrap code in try/catch but not how to make decisions about recovery.
- **Assessment**: Educational resource, not peer-reviewed. Relevant because it explicitly frames error handling as a decision-making problem, not a syntax problem.

### Security and Quality in LLM-Generated Code: Multi-Language, Multi-Model Analysis (Kharma et al., arXiv 2025)
- **Link**: Semantic Scholar: https://www.semanticscholar.org/paper/358f564d555db51886457e1c864c939a168f2530
- **Key content**: 200 tasks across 6 CWE categories, multiple languages. Finding: "Many models fail to utilize modern security features in recent compiler/toolkit updates" and "outdated methods are still commonly used, particularly in C++." Security effectiveness varies by language. 17 citations — well-cited for a 2025 paper.
- **Assessment**: Peer-reviewed (arXiv preprint), reasonable methodology, relevant empirical data.

---

## Landscape Assessment

### State of Knowledge

The danger-to-invisibility problem is well-established empirically at the statistical level (Veracode, CMU CSET, CodeRabbit) but poorly synthesized at the conceptual level. Nobody has produced a principled taxonomy of which concepts are simultaneously dangerous AND non-obvious from normal vibe-coding practice. Most writing either: (a) lists every possible security issue (overwhelming), or (b) describes single incidents. The "danger-to-invisibility ratio" framing is novel and would be genuinely useful.

### The Clearest Findings

**Concept 1: Authorization vs. Authentication (IDOR / Missing Authorization)**
The single most dangerous invisible concept for vibe coders. Authentication (are you logged in?) is easy to add — most frameworks do it automatically. Authorization (can THIS user access THIS resource?) is structural and requires adversarial thinking. The AI-generated IDOR example from LindleyLabs is canonical: userId taken from request parameter, not from session. It works perfectly when you test it as yourself. It breaks instantly when an attacker changes the number in the URL. CWE-862 (Missing Authorization) rose 5 positions in 2025 CWE Top 25. OWASP has had "Broken Access Control" at #1 for multiple years. Veracode: AI misses XSS defenses 86% of the time.

**Concept 2: Secrets Management and Hardcoded Credentials**
The most *immediately* dangerous concept (automated scanners find and exploit exposed keys within minutes of a public push). Invisible because AI will use whatever credentials pattern gets the app working — and service keys often have broader permissions than anon keys, so using the service key is the path of least resistance. Lovable CVE-2025-48757: 170/1,645 scanned apps had Supabase service keys in frontend bundles. The .env / .gitignore pattern is a "known fix" but requires understanding *why* you can't put secrets in source code — which means understanding git history and remote repositories as distinct persistent stores.

**Concept 3: Silent Failures and Error Handling Philosophy**
The dangerous-because-invisible failure mode that's hardest to explain. Code that runs without throwing an error is not necessarily correct code. A database write can fail, be swallowed, and the user sees a confirmation they never earned. The difference between "catching an exception" and "deciding what to do when something goes wrong" is a mental model shift that vibe coders almost never make. Columbia's DAPLab identifies this as the #1 failure mode in vibe-coded apps. The AI always generates the happy path. Error handling requires imagining a different world.

**Concept 4: Race Conditions and State Consistency**
Most dangerous in applications with: checkout, payments, voting/likes, coupon redemption, account limits. The classic pattern: check-then-act with no locking. Two simultaneous requests both pass the check, both act. Balance goes negative, coupon gets used twice, limit gets exceeded. Completely invisible in solo testing because you're one user making one request. The fix requires atomic database operations or explicit locking — concepts that don't appear naturally when you're asking AI to "build a checkout flow." TOCTOU vulnerabilities appear consistently in the CWE Top 25.

**Concept 5: Idempotency and Retry Safety**
The "double charge" problem. Payment operations need to be safe to retry because networks are unreliable. Disabling the submit button on the frontend is not a fix — it's a hopeful gesture. The real fix requires server-side idempotency keys, which require understanding that the same user action can produce multiple HTTP requests through no fault of the user. Vibe coders don't think about this because in development, requests always succeed or clearly fail. Production has timeouts, drops, and retries.

**Concept 6: Database Migrations as a Separate Deployment Concern**
The Medium article's incident is archetypal: deploy code, forget to run migrations, 400K users see blank pages. The underlying concept: your application code and your database schema are two separate versioned artifacts that must evolve in sync but can be deployed independently. AI writes them in the same session and doesn't flag this dependency. The destructive version: a migration that drops a column currently in use, run on production before the old code is removed. Irreversible data loss is the extreme case.

**Concept 7: Environment Parity (Prod vs. Dev Mismatch)**
"Works on my machine" is a vibe-coding cliché, but the specific failure modes are non-obvious: hardcoded local paths, dev-only environment variables, assumptions about file system layout, database engine differences, missing environment variables in production. The invisible part: development environments are intentionally permissive and helpful; production environments are intentionally restrictive. A vibe coder testing locally is testing in the least realistic possible environment.

**Concept 8: Input Validation as Server-Side Responsibility**
The client-side validation problem: AI will often add validation on the form (maxlength, required, type="email") which is helpful for UX but provides zero security. Any attacker bypasses the browser entirely and POSTs directly to the API. SQL injection and XSS both exploit the absence of server-side validation. CWE-89 (SQL Injection) is #2 on the 2025 CWE Top 25. The invisible part: the form works, validation appears to work, there's no visible failure until someone sends a malformed request.

### Agreements Between Sources

Near-universal agreement: AI tools optimize for functional output, not secure output. Every source — academic (Veracode, CMU, IEEE), practitioner (DataHogo, LindleyLabs, Addy Osmani), and vendor (Modall) — agrees on this fundamental point. The training data/optimization target explanation is the consensus account.

Agreement: Authorization logic is the hardest thing to get right, and AI consistently fails at it. Multiple independent sources identify IDOR/broken access control as the structural vulnerability that AI code is worst at catching.

### Conflicts and Tensions

Some tension around optimism: Veracode's Wessling says security performance "hasn't kept up" and shows no improvement over time. LindleyLabs cites Databricks research finding that self-reflection prompts improve AI security output by 60-80% for Claude. These aren't necessarily contradictory (unprompted vs. prompted performance) but they pull in different directions.

The "63% of vibe coding users are non-developers" framing (from LindleyLabs) creates a tension: for non-developers, a vibe-coded app with some vulnerabilities may be better than their alternative (a spreadsheet). The audience for "danger-to-invisibility" content matters — a personal budgeting tool and a user-data-handling SaaS have very different threat profiles.

### Gaps and Under-Explored Areas

**The backup/recovery blind spot**: Data loss from destructive AI agent actions (not migrations, but the AI assistant directly running DROP TABLE or overwriting a file) is mentioned anecdotally but not empirically studied. This seems like a genuine gap — vibe coders often give AI assistants direct database/file access.

**Specific to small personal tools**: The research is almost entirely enterprise or startup-focused. A personal Notion alternative with 10 users has a different threat model from a SaaS with 10K users — the risk calculus around hardcoded secrets, for instance, is very different if the code never goes public. No source distinguishes carefully between "personal tool" and "public-facing app" risk profiles.

**Temporal/state blindness**: The idea that operations produce side effects that persist in time — that running code twice is different from running it once — seems underexplored as a distinct concept. The AI generates code that acts; it doesn't model what's been acted on.

**Dependency security (supply chain)**: LindleyLabs mentions it, Veracode's SCA work addresses it, but it's underweighted given how often AI scaffolding pulls in outdated packages with known CVEs. Vibe coders don't run `npm audit`, don't know what a CVE is, and trust the AI's package choices completely.

### Surprises

1. The claim that larger models are no more secure than smaller ones (Veracode) is genuinely surprising and important. Vibe coders intuitively believe that using the smartest available model protects them. It does not.

2. Carnegie Mellon's stat — 61% of AI code is functionally correct, only 10.5% is secure — has a striking gap. That means the vast majority of code that passes tests still has security problems.

3. The specific number from Escape.tech: 400+ exposed secrets found in 5,600 live vibe-coded apps in production. That's ~7% of apps with exposed secrets accessible in the wild. These are real apps handling real users.

4. The "happy path bias" as a *structural* property of how LLMs work (not just a tendency) is well-explained by DataHogo. It's not that AI is "bad at security" — it's that generating the described happy-path behavior is exactly what the model was trained to do. Security requires generating behaviors the user didn't describe and didn't ask for.
