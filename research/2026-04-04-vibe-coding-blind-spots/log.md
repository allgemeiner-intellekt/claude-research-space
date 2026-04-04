# Research Log — Vibe Coding Blind Spots

## Scoping

**User prompt**: Non-technical person building small tools with AI. Wants to learn
engineering primitives that are essential but invisible to vibe coders — things
that, if you don't know them, you can't even tell when AI-generated code is
dangerously wrong.

**Key insight for scoping**: The user isn't asking "teach me to code." They're
asking: "What concepts do I need so that my collaboration with AI is safer and
more effective?" This means the primitives need to be:
- Learnable without learning to code from scratch
- High-leverage: ignorance creates real risk, not just suboptimal code
- Things the AI won't spontaneously teach you (because you don't know to ask)

**The angle I'm pursuing**: The most dangerous blind spot for vibe coders is
**state and side effects** — the distinction between code that computes something
and code that changes something in the world. This is where the real risk lives:
you can't tell by reading AI output whether code is safe to run twice, whether it
handles partial failure, or whether it's making irreversible changes.

But I want the survey phase to challenge this thesis. Maybe there's a more
fundamental or more practical primitive cluster. Possible alternatives:
- The execution environment (paths, dependencies, OS state)
- Security boundaries (what runs where, who can see what)
- The concept of a "contract" or interface (what code promises vs what it does)

### Questions for investigation

1. **What do experienced developers report as the most common failure modes in
   vibe-coded / AI-generated software?** — Not theoretical risks, but actual
   patterns of breakage people have observed.

2. **What engineering concepts have the highest "danger-to-invisibility ratio" for
   non-technical AI users?** — i.e., concepts where (a) ignorance causes real
   harm and (b) the concept is genuinely non-obvious / wouldn't be discovered
   through normal vibe-coding practice.

3. **How do state, side effects, and idempotency manifest in the "small personal
   tools" context?** — The user builds small tools, not distributed systems. What
   does "state management" actually look like at that scale? File corruption?
   Double-sending? Lost data?

4. **What mental models separate "dangerous vibe coding" from "safe vibe coding"?**
   — Not "learn to program" but "learn to think about programs." What's the
   minimum conceptual toolkit?

## Phase 2 — Survey

Dispatched four survey agents in parallel:
- survey-failure-modes: Covered Columbia DAPLab, Tenzai, Tambon et al., real incidents
- survey-danger-invisibility: Eight concepts ranked by danger-to-invisibility ratio
- survey-state-small-tools: Google Apps Script double-triggers, JSON corruption, cron overlap
- survey-mental-models: Notional machines, the "Infinite Intern" model, epistemic posture

Key convergence: silent failures (not crashes) are the dominant failure mode. The most
dangerous bugs are structural omissions — things that should be there but aren't.

## Phase 3 — Review Round 1

Verdict: CONTINUE. Strong evidence base but lacking the teaching layer. Three deep dives assigned:
1. Concrete walkthrough scenarios at personal-tool scale
2. The "AI chooses permissive defaults" mechanism
3. What expert review looks like concretely

## Phase 4 — Deep Dives

- walkthrough-scenarios: Three detailed scenarios (piano teacher double-email, book club
  open database, photo renaming script). All grounded in real incidents.
- permissive-defaults: Three-layer mechanism (training data debt, RLHF objective mismatch,
  specification gap). Key finding: Wendlinger et al. 2026 shows models are internally
  aware of vulnerabilities as they generate insecure code — rules out ignorance.
- expert-review: Five cognitive checks experts perform automatically. Key finding: experts
  read structural absence; novices read textual presence.

## Phase 5 — Review Round 2

Verdict: SATISFIED. Article backbone: three teachable concepts.

## Phase 6 — Report Writing

Synthesizing all notes into report.md. The article's thesis: the problem is not that
AI writes bad code, but that AI writes code whose dangers are invisible to the person
who asked for it. Three concepts to teach: (1) AI optimizes for "works" not "safe,"
(2) reading vs writing operations, (3) you cannot see what an expert sees.
