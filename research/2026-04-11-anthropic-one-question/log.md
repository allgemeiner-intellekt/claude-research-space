## Log — Anthropic: one specific question

### Setup

User's instruction (2026-04-11): explore Anthropic broadly first, then identify **one** specific and meaningful question, then deep-research that question. Not a comprehensive Anthropic profile. If the user wants other angles later, those will be separate tasks.

Prior work in this repo that constrains scope (avoid overlap):
- 2026-04-10 open-weight-models — Anthropic's open-weight stance, Mythos Preview withholding, public-choice framing
- 2026-04-07 llm-release-cadence — post-training/product-shift era, Claude Code 266:2 release ratio

### Phase 1 — Exploratory survey (to find the question)

Dispatching four parallel `survey` agents on distinct angles of Anthropic that prior work has not touched. The purpose is not to produce answers but to surface where the sharpest, most falsifiable, most under-examined question lies. After reading their notes the orchestrator will commit to a single question and proceed with real depth.

Angles:
1. **LTBT & governance** — Long-Term Benefit Trust: structure, powers, whether they have been diluted since 2023, investor carve-outs.
2. **RSP track record** — Responsible Scaling Policy: has it ever actually caused a delay, non-deployment, or scope reduction? Or has every model so far comfortably cleared its thresholds?
3. **"Race to the top" thesis** — Dario Amodei's core justification. Has Anthropic's presence at the frontier measurably shifted the behavior of OpenAI, Google DeepMind, xAI, Meta on safety? Or is it a post-hoc rationalization?
4. **Amazon relationship** — $8B+ investment, Trainium commitments, compute lock-in. Is Anthropic a captured subsidiary in substance while PBC in form?

### Survey results and question selection

Three of four surveys returned successfully (race-to-top agent malfunctioned). Findings:

**Governance/LTBT**: The LTBT has exercised power (appointing Kreps, Hastings). But the board expanded from 5→6 members in Feb 2026 without disclosing whether LTBT's 3-of-5 majority scales. Trustee composition has completely turned over from EA-affiliated figures to national security/policy establishment. The trust document has never been published. Sharpest question: has the majority been diluted to 50% by the 6-person board?

**RSP track record**: Every model through Claude Sonnet 3.7 was ASL-2. Opus 4 was the first ASL-3 activation — precautionary, not triggered. RSP v3.0 (Feb 2026) explicitly dropped the pause commitment. Four self-reported compliance failures, all minor/procedural. Mythos (April 2026) is withheld from public release — but the ASL-3 Deployment Standard covers only biological weapons, not cyber. **If the RSP has no formal cyber deployment standard, Mythos was restricted by ad hoc safety judgment, not by the RSP's formal trigger architecture.** This would mean the RSP's formal mechanism has never caused a deployment restriction.

**Amazon capture**: Thesis has weakened substantially. $8B at $380B = ~2.1% equity. Google TPU deal (1 GW+), Broadcom deal (3.5 GW) dwarf AWS compute. No revenue-sharing like MSFT-OpenAI's 20%. FTC found contractual "consultation, control, and exclusivity rights" but terms are redacted. Bilateral dependency — Amazon needs Anthropic for Trainium validation as much as Anthropic needs Amazon for compute.

### The chosen question

**Has Anthropic's Responsible Scaling Policy ever formally caused a deployment restriction — and specifically, was the Mythos withholding driven by the RSP's trigger architecture, or was it an ad hoc safety judgment made outside the RSP's formal mechanism?**

Why this question:
1. **Falsifiable**: The RSP's v3.0 either has a cyber deployment standard or it doesn't. Mythos was restricted for cyber capabilities. If there's no cyber standard, the restriction is formally extra-RSP.
2. **Maximally timely**: Mythos was disclosed April 7, 2026 — 4 days ago. This is the first-ever case of a frontier lab withholding a model from public release on safety grounds.
3. **Implications beyond Anthropic**: If the most serious voluntary safety framework in AI has never formally triggered a deployment restriction, the entire premise of self-regulation is weaker than the industry claims.
4. **Under-examined**: Most commentary treats Mythos as "the RSP working" without checking whether the RSP's formal architecture actually caused it. The distinction between "Anthropic chose not to release" and "the RSP required Anthropic not to release" is crucial and mostly un-asked.
5. **Connects to the user's interests**: Institutional economics, mechanism design, the question of when self-regulatory commitments actually bind vs. when they are cheap talk.

### Phase 2-4 — Investigation cycles

**Survey round**: 4 agents dispatched (governance, RSP track record, race-to-top, Amazon capture). 3 returned successfully. Race-to-top agent malfunctioned.

**Deep dive round 1**: 4 agents dispatched:
- RSP formal mechanism — agent malfunctioned
- RSP promise-breaking — excellent findings. Drake Thomas (Anthropic) acknowledged misleading presentation. Hubinger's "big bold font" quote documented. Escape clause genealogy: v1.0 (rogue state only) → v2.0 footnote 18 (competitor-based) → v3.0 (primary organizing principle).
- Mythos motives — forensic. All four explanations (RSP, compute scarcity, commercial strategy, technical unreadiness) simultaneously true. RSP is the weakest causal factor. Compute cost ($25/$125 per M tokens) would have prevented public release regardless. System card's self-critical candor (interpretability findings, concealment features) argues against purely cynical reading.
- Self-regulation theory — outstanding. King-Lenox (2000): Responsible Care had zero effect without sanctions. INPO: only works because of joint liability + insurance pricing. Basel II: self-assessment → systematic underestimation. RSP fails all four credible commitment criteria (costly signaling: weak; external enforcement: absent; reputation: moderate; unilateral modification foreclosed: absent).

**Review round 1**: CONTINUE. Two gaps identified:
1. Does RSP v3.0's "high-stakes sabotage" category cover cyber? (Would weaken central claim.)
2. Capacity-building steelman not engaged.

**Deep dive round 2**: 2 agents dispatched:
- Cyber threshold check: **Central claim holds.** "Cyber" appears zero times in RSP v3.0's 51,386 characters. "High-stakes sabotage" = AI alignment sabotage (models manipulating their own training), NOT offensive cyber. GovAI confirms cyber references were eliminated. Mythos system card cites no RSP threshold as triggered.
- Capacity building: Defense is substantially true but insufficient. RSP provably created Frontier Red Team (11 people), Constitutional Classifiers, 8% headcount in security (~65 people), METR partnership. But capacity ≠ constraint. Even Zvi concedes the capacity was real. The dispute is whether v3.0 preserves the forcing function.

**Verdict**: Investigation sufficient. Proceeding to write report.
