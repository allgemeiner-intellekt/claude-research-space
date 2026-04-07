# Research log — LLM release cadence: sustainable, or about to inflect?

## 2026-04-07 — Scoping

The user's literal question: is the relentless ~3-month cadence of frontier
LLM releases from leading labs sustainable for another decade or two, or are
we headed for an inflection point where some new (or borrowed-from-other-
industries) pattern replaces it?

### Why the literal question is the wrong frame

"Sustainable yes/no" is a binary that hides what's actually interesting. The
sharper observation is that the cadence has *already* changed character
multiple times in the 2023-2026 window:

- 2023 was dominated by base-model scale-ups (GPT-4 class)
- 2024 introduced reasoning models / inference-time compute as a new axis
- 2025 saw frontier convergence and the rise of "minor revisions" (3.5 → 3.6
  → 3.7) as the dominant release format
- 2026 has the "agent" framing competing with the "model" framing

So the cadence persists, but what *counts as a release* has been mutating
under the surface. That observation reframes the whole question: maybe the
inflection point is not in the future. Maybe it has already happened twice,
and the public-facing cadence has been smoothing over a much rougher
underlying technical reality.

There is also a second, separate question hiding in the user's prompt:
even if technical progress slows, will the cadence persist for institutional
reasons (Red Queen competition, investor pressure, branding)? Moore's Law
in its later years was sustained by multi-core hacks and node renamings well
past the point where transistor density really mattered for performance.
Could LLM releases enter a similar zombie phase?

### The four questions

1. **What is actually being released in 2023-2026?** Trace the substantive
   content of "frontier releases" over this window. When did the underlying
   nature shift? Was there a hidden inflection already? Distinguish: base
   scale-ups, reasoning paradigm shifts, post-training improvements,
   distillation/efficiency gains, agent infrastructure, multimodal
   integration. The question is whether the cadence is one phenomenon or
   several phenomena overlapping.

2. **What are the binding constraints on continued scaling, in 2026
   numbers?** Compute (chip supply, fab capacity, power), data (text
   exhaustion, synthetic data limits), capital (training run cost
   trajectories: $10M → $100M → $1B → $10B), talent. Where are the actual
   walls? Which arrives first? Which would force a paradigm break?

3. **What does the history of analogous technology cadences predict?**
   Moore's Law (timing and character of inflection — what looked like
   slowdown vs. what actually happened). Eroom's law (pharma R&D
   productivity collapse). Aviation (rapid 1900-1970, plateau after).
   Internet bandwidth. Battery density. Which historical pattern is the
   best fit for what's happening with LLMs, and what does the analogy
   actually predict?

4. **Could the cadence persist on pure institutional momentum?** Game
   theory of frontier labs racing each other; investor expectations;
   branding requirements; the precedent of mature industries shipping
   cosmetic revisions to maintain mindshare. Would the "release every 3
   months" pattern have a life of its own even if the underlying technical
   substance stalled?

### Anti-questions (deliberately not pursuing)

- "When will we hit AGI" — too far from the structural question
- General LLM capability surveys — already covered elsewhere
- Model-by-model benchmark comparisons — not what the user asked
- Safety/alignment trajectories — orthogonal to release cadence

### Plan

Survey one agent per question in parallel. Review. Deep-dive on whichever
threads turn out to be load-bearing for the synthesis. Iterate until the
reviewer is satisfied. User is asleep, so multiple cycles are appropriate.
