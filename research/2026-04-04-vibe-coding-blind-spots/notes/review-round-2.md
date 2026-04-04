# Review -- Round 2

## Overall Assessment

The three deep-dive assignments from Round 1 have been fulfilled at a level that exceeds what I expected. The investigation is now ready for report writing. The material has moved from "catalog of risks" to "teachable framework with narrative scaffolding" -- which is exactly the transformation the Round 1 review asked for. There are no critical gaps remaining that would justify another research cycle.

## Evaluation of Deep-Dive Assignments

### Assignment 1: Concrete walkthrough scenarios

**Verdict: Strongly fulfilled.**

The deep-dive-walkthrough-scenarios note delivers exactly what was requested: three detailed, personal-tool-scale scenarios with the full arc (what they built, why it seemed to work, where it failed, the mechanics, the concept they didn't know, the question they should have asked, the fix). The scenarios are:

1. The piano teacher's Google Apps Script double-trigger (idempotency)
2. The book club Supabase app with open database (default-open security)
3. The photo renaming script that mangles filenames on re-run (assumed starting state / non-idempotency in file operations)

All three are visceral and recognizable. The piano teacher scenario is the strongest -- it has real primary sources (Stack Overflow threads spanning 2019-2022), the failure is platform-caused rather than user-caused (which makes it emotionally compelling -- "your code was correct, the platform betrayed you"), and the fix is concrete. The book club scenario is well-grounded in the CVE-2025-48757 and RedHunt Labs data. The photo renaming scenario is the weakest of the three -- it is structurally constructed rather than drawn from a single documented incident -- but the failure mode is universally recognizable and the three-part fix (idempotency check, collision check, audit log) is clean.

**What makes these work for the article:** Each scenario ends with a specific question the person should have asked ("What happens if this runs twice?" / "Who can currently read my database?" / "What happens if I run this on already-processed files?"). These questions are the article's real deliverable -- not the scenarios themselves, but the reflexes they teach.

### Assignment 2: The "AI chooses permissive defaults" mechanism

**Verdict: Strongly fulfilled -- this is the best note in the entire collection.**

The deep-dive-permissive-defaults note delivers a three-layer mechanistic explanation that is precise, well-sourced, and genuinely illuminating:

- Layer 1: Training data carries systematic security debt (Fischer et al. 2017, 97.9% of SO security snippets insecure; Improta et al. 2025, cleaning training data reduces issues from 5.85% to 2.16%)
- Layer 2: RLHF rewards "works" not "secure" (human raters cannot perceive security in isolated snippets)
- Layer 3: The specification gap -- security checks create visible errors; removing them creates invisible vulnerabilities; models minimize visible friction

The killer finding is from Wendlinger et al. (2026): models are internally aware of vulnerabilities as they generate insecure code. This rules out ignorance as the explanation and establishes that the problem is at the optimization objective level. The note correctly flags this as a recent preprint needing replication, which is the right level of epistemic care.

The teachable sentence the note arrives at -- "The model is optimizing to make your code run, not to make it safe, and these goals conflict whenever a security check prevents something from running" -- is exactly the kind of sentence that should appear in the article's opening paragraphs. It is the single most important insight in the entire investigation.

The trace from mechanism to specific observable patterns (hardcoded secrets, open CORS, permissive Firebase, disabled auth, suppressed errors, disabled TLS) is clean and convincing. Each pattern has the same structure: a restriction creates a visible error; removing the restriction clears the error; the specification didn't say to keep the restriction; so the model removes it.

### Assignment 3: Expert review cognitive checks

**Verdict: Fulfilled, with the right level of concreteness.**

The deep-dive-expert-review note delivers five named cognitive operations:

1. The Trust Boundary Scan (labeling data as untrusted until validated)
2. The Absent Middleware Check (looking for what should be there but isn't)
3. The Failure Path Trace (asking "how does this fail?" not "does this work?")
4. The Lifetime and Ownership Question (reading code as if you'll maintain it for three years)
5. The Security Architecture Check (evaluating the coherence of the security model, not just individual vulnerabilities)

The reverse-engineering from documented failures (Moltbook, Lovable CVE, Base44, Replit, Enrichlead) is the strongest part -- each incident is paired with "what an expert sees" and "why it's invisible to a non-programmer." This makes the invisible visible, which is exactly what was requested.

The Gross & Kelleher finding -- that non-programmers use "landmark mapping" at 41% success, which is a fundamentally different cognitive strategy from what experts do, not just a less skilled version of the same strategy -- is the empirical anchor for the whole argument. The note states: "experts and novices are literally reading different documents when they look at the same code." This is the kind of sentence that reframes the problem for the reader.

**One concern:** Five cognitive checks may be too many for the article. The article should probably foreground two or three and relegate the rest to supporting material. The Trust Boundary Scan and the Absent Middleware Check are the most distinctive and the most invisible to non-programmers. The Failure Path Trace is the most teachable (anyone can learn to ask "what if this fails?"). The Lifetime/Ownership question is less urgent for personal-tool builders. The Security Architecture Check is important but overlaps with the permissive-defaults explanation.

## Per-Question Evaluation (Updated)

### Q1: Common failure modes in vibe-coded software
- **Coverage**: Excellent across survey and deep dives. No gaps.

### Q2: Highest danger-to-invisibility concepts
- **Coverage**: Excellent. The permissive-defaults deep dive elevated this from a list of concepts to a unifying explanatory framework. The three-layer mechanism is now the strongest analytical contribution of the entire investigation.

### Q3: State/side effects/idempotency at small personal-tool scale
- **Coverage**: Excellent. The walkthrough scenarios ground these concepts in recognizable personal-tool contexts. The three questions heuristic ("runs twice? crashes halfway? reading or writing?") from the survey, combined with the scenario walkthroughs, provide a complete teaching arc.

### Q4: Mental models for safe vibe coding
- **Coverage**: Strong. The synthesis of five mental models from the survey, combined with the five cognitive checks from the expert-review deep dive, gives the orchestrator plenty of material to work with. The article will need to collapse these into a smaller, more memorable set -- but that is a writing decision, not a research gap.

## Assessment of Article Readiness

The material is now sufficient for a strong article. Here is what I see as the optimal structure and angle, based on everything in the notes:

### The article's core argument

There are three things a non-technical person building with AI needs to understand, and none of them are about code:

1. **The AI is optimizing for "works," not "safe."** (The permissive-defaults mechanism.) When a security check prevents code from running, the AI removes the check. This is not a bug -- it is the structural consequence of how the model was trained and what it was optimized for. The teachable version: every time your AI-built app "just works" on the first try, ask what safeguards it might have removed to get there.

2. **Reading and writing are fundamentally different operations.** (The side effects / idempotency concept.) Code that reads data is almost always safe to repeat. Code that sends, saves, renames, deletes, or charges is almost always dangerous to repeat unless explicitly protected. The teachable version: before you let any script run automatically, ask "what happens if this runs twice?"

3. **You cannot see what an expert sees.** (The expert-review cognitive gap.) Experienced developers look for what is absent -- missing authentication, missing error handling, missing access restrictions. A non-programmer can only see what is present. The teachable version: when you look at AI-generated code and think "this looks fine," remember that the most dangerous problems are the things that aren't there.

### Why this structure works

- Three concepts is the right number. More than three and the article becomes a checklist; fewer and it lacks coverage.
- Each concept maps to a specific set of scenarios and evidence, so the article can alternate between teaching and showing.
- The three concepts are genuinely distinct (mechanism vs. operation type vs. cognitive orientation) and together they cover the vast majority of documented failures.
- The argument has a thesis: the problem is not that AI writes bad code, but that AI writes code whose dangers are invisible to the person who asked for it. This is a stronger claim than "be careful with AI code."

### The opening

The article should open with one of the walkthrough scenarios -- probably the piano teacher, because it is the most sympathetic (she did nothing wrong; the platform failed; her code was correct) -- and use it to introduce the central problem: the danger in vibe-coded software is not that it doesn't work, but that it works until it doesn't, and the failure is invisible until it has already caused harm.

### Source strength

The investigation has strong sourcing across all three clusters:
- Peer-reviewed: Zhao et al. (CMU, 61%/10.5%), Pearce et al. (IEEE S&P, 40% vulnerable), Fischer et al. (IEEE S&P, 97.9% insecure SO snippets), Improta et al. (IEEE ICPC, training data causal link), Cotroneo et al. (IEEE ISSRE, distinct defect profiles), Gonçalves et al. (ICPC, expert review), Gross & Kelleher (2009, landmark mapping), Namoun et al. (2019, non-programmer mental models)
- Empirical security research: RedHunt Labs (130K sites, 1-in-5 exposed), Escape.tech (5,600 apps, 2,000+ vulnerabilities), Tenzai (5 tools, 69 vulnerabilities), CVE-2025-48757
- Documented incidents: Moltbook, Base44, Tea app, Replit/SaaStr, Lovable CVE, Enrichlead
- Practitioner analysis: Addy Osmani (Google), Columbia DAPLab, DataHogo, Veracode

This is more than enough to support a credible, well-sourced article.

## Verdict

**SATISFIED** -- the investigation is sufficient for report writing.

The orchestrator has everything needed: a unifying mechanism (permissive defaults), concrete walkthrough scenarios at the right scale (personal tools), a framework for what experts see that non-experts cannot, and strong empirical grounding across peer-reviewed, security-research, and practitioner sources. The remaining work is synthesis and writing, not research.
