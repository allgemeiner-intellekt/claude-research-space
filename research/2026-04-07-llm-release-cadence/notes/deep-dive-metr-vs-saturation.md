# Deep Dive: METR Time Horizons vs. Benchmark Saturation — What Is Actually Exponential?

## Question

Are METR's task-horizon doublings (still on an exponential, ~7-month doubling) and the benchmark-saturation story (top-5 model gap on MATH-500 = 0.4pp, benchmarks at ceiling) measuring the same underlying capability from different angles, or different things? Specifically: when we decompose METR time-horizon gains, how much comes from (a) better base model weights, (b) reasoning RL post-training, (c) improved scaffolding/harness? If scaffolding dominates, the exponential lives in agent engineering, not in the model; if base model dominates, benchmark saturation is cosmetic. This is the single most important unresolved tension in the corpus.

---

## What I Searched

1. METR paper (arXiv 2503.14499, NeurIPS 2025) and its blog post (metr.org, Mar 2025)
2. METR follow-up notes: "Clarifying limitations of time horizon" (Kwa, Jan 2026); "Time Horizon 1.1" (METR, Jan 2026); "Measuring Time Horizon using Claude Code and Codex" (Jurkovic, Feb 2026); "Impact of modelling assumptions on time horizon results" (Barry, Mar 2026)
3. METR's live time-horizon dashboard (metr.org/time-horizons)
4. LessWrong critique: "METR's data can't distinguish between trajectories" (Moss, Feb 2026)
5. Epoch AI: "AI capabilities progress has sped up" (Dec 2025) with ECI breakpoint analysis
6. Epoch AI: "How far can reasoning models scale?" (Josh You, date implicit ~May 2025)
7. DeepSeek-R1 paper (arXiv 2501.12948, published Nature June 2025)
8. Densing Law paper (Xiao et al., Nature Machine Intelligence 2024)
9. GPT-4.5 reception evidence (multiple sources, Feb-Mar 2025)
10. Particula Tech blog on SWE-bench scaffolding: "Agent Scaffolding Beats Model Upgrades" (Mar 2026)
11. Epoch AI's year-end analysis of capability acceleration timing (Dec 2025)

---

## METR Methodology Summary

The METR paper (Kwa et al., 2025, NeurIPS) proposes the "50%-task-completion time horizon" as the key metric: the duration of tasks (measured by how long skilled human experts take) at which an AI agent succeeds 50% of the time. Concretely: if a human expert typically takes 30 minutes on a task, and the model gets it right half the time, then 30 minutes is "within" its horizon. METR fits a logistic function: P(success) = σ(β_agent(log h_agent - log t_task)), where h_agent is the 50% time horizon and β_agent is a slope parameter. They use bootstrapped confidence intervals. Task suites: RE-Bench, HCAST subsets, and 66 novel shorter tasks (total ~170 tasks in TH1.0, expanded to ~228 in TH1.1).

**The key empirical finding**: From 2019 through late 2025, frontier AI time horizons doubled approximately every 7 months (TH1.0) to 4-5 months (revised upward in TH1.1, post-2023 data). TH1.1 (Jan 2026) gives a post-2023 doubling time of 131 days (~4.4 months) with tight CIs of 107-161 days. The full-period estimate remains 196 days (~6.5 months), anchored by pre-2023 models.

**What METR says drives the gains**: The abstract and body of the paper state that "the increase in AI models' time horizons seems to be primarily driven by greater reliability and ability to adapt to mistakes, combined with better logical reasoning and tool use capabilities." This is descriptive, not a decomposition into pretraining vs. RL vs. scaffolding. The paper provides no causal attribution experiment (e.g., ablating the scaffold while holding model fixed, or comparing base model to RL-trained model on the same task suite). This is the core gap in the evidence.

**Scaffold used**: METR uses two primary scaffolds: ReAct (a simple action-observe loop) and Triframe (a more complex multi-agent architecture where an advisor, parallel actor agents, and rater agents evaluate options before each action). These are METR-internal scaffolds, not the commercial product scaffolds (Claude Code, OpenAI Codex).

---

## The Scaffolding Decomposition: The Critical Evidence

### METR's Own Scaffold Ablation (Jurkovic, Feb 2026)

This is the most direct evidence available and the primary source for the decomposition question. METR ran a controlled comparison of their default scaffolds (ReAct, Triframe) against Claude Code (for Opus 4.5) and OpenAI Codex (for GPT-5). These are the commercial, heavily-optimized, production-grade scaffolds from the model vendors themselves.

**Results**:
- For Opus 4.5: Claude Code beats ReAct in only 50.7% of bootstrap samples — statistically indistinguishable from 50%
- For GPT-5: Codex beats Triframe in only 14.5% of bootstrap samples — Codex is actually WORSE than METR's general scaffold

**Conclusion from METR**: "It seems that neither Claude Code nor Codex outperform the default scaffolds METR uses, at least when measuring the time horizon of Opus 4.5 and GPT-5." They note that Claude Code and Codex are "mostly used in an interactive setting, where a human user often checks in on the agent's work," which differs from METR's fully automated evaluation context.

**What this means for the decomposition question**: The gains observed in METR's time horizon are NOT primarily driven by better scaffolding. METR's two generic, unoptimized, non-model-specific scaffolds perform equivalently to (or better than) the commercially optimized, vendor-tuned scaffolds. The exponential increase in time horizon across 2019-2025 cannot therefore be attributed primarily to scaffold engineering improvements, at least not within the context of how METR measures things. The scaffold contribution appears small — well within measurement noise.

**Important caveat**: This comparison holds for contemporary models but doesn't resolve what happened historically (2019-2024). The scaffold comparison is only run on 2025-era models. We cannot directly rule out that early gains (GPT-2 to GPT-3 era) were partly driven by scaffold improvements at the time. However, since METR uses essentially the same scaffold types throughout their historical trend, scaffold changes are not a confound in their time-series.

### The SWE-Bench Contrasting Evidence

An industry analysis (Particula Tech, Mar 2026) argues that on SWE-bench, "scaffolding changes alone produce 22+ point swings on SWE-bench Pro with the same model," while "swapping between the six best frontier models moves your score by less than a single percentage point." Six frontier models now score within 0.8 points of each other on SWE-bench Verified.

This appears to directly contradict METR's scaffold finding. The reconciliation:
1. SWE-bench is a specific code-repo benchmark where the evaluation harness, tool formats, and task structure are all tightly coupled to scaffold design. The scaffolding IS the product on SWE-bench, since all benchmarks inherently incentivize scaffold optimization.
2. METR's task suite is designed to be "scaffold-agnostic" with clear success criteria evaluated independently of how the agent gets there. The tasks are more general and isolated.
3. The SWE-bench finding describes benchmark-specific engineering optimization; the METR finding describes capability measurement controlled for scaffold.
4. Crucially: the convergence of top frontier models on SWE-bench Verified (within 0.8pp) is consistent with benchmark saturation, not scaffold dominance per se. If the model differences are negligible, scaffolding becomes the only lever — but that's a ceiling effect, not a sign that scaffolding drives model-level progress.

The SWE-bench evidence thus supports the benchmark saturation story (models converged) without undermining METR's attribution (scaffold not driving time horizon trend).

---

## The Pretraining vs. RL Decomposition

### DeepSeek-R1 as Primary Evidence

The DeepSeek-R1 paper (arXiv 2501.12948, Nature June 2025) is the most explicit decomposition available. The key ablation: DeepSeek-R1-Zero is trained from the base model (DeepSeek-V3) using pure reinforcement learning with no supervised fine-tuning on reasoning trajectories. This directly tests the RL contribution to reasoning capability.

**Finding**: DeepSeek-R1-Zero, trained via pure RL from DeepSeek-V3 base, achieves reasoning performance competitive with o1 on mathematical benchmarks. The base model (DeepSeek-V3) without RL achieves substantially worse performance on reasoning tasks. The RL stage used approximately 6e23 FLOP, which Epoch AI estimates is about 20% of the pretraining cost.

**Implication**: RL post-training provides a massive and real capability jump, not just a fine-tuning increment. The base model provides the substrate, but RL post-training with verifiable rewards is the dominant contributor to task-solving capability at the reasoning frontier. This is not scaffolding — it is a change to the model weights through RL.

**The cost relationship**: Epoch AI (Josh You, "How far can reasoning models scale?") documents that OpenAI's o3 is a 10x scale-up in reasoning training compute from o1 (per OpenAI's own graph), released just 4 months after o1. They estimate reasoning RL compute for frontier models is still multiple orders of magnitude below overall training compute. Dario Amodei observed in Jan 2025 that labs are spending "$0.1M-$1M" on RL stages, far below "hundreds of millions" — suggesting the RL paradigm is still early-scaling.

**The log-linear scaling in reasoning compute**: OpenAI's own published curves show AIME score increasing roughly log-linearly with reasoning training compute. The DeepSeek-R1 paper shows accuracy increasing with training steps in a roughly log-linear way. This suggests RL post-training currently behaves like a new scaling axis — a frontier that is still ascending its curve.

### The ECI Acceleration and When It Happened

Epoch AI's capability acceleration analysis (Dec 2025) provides a crucial timestamp. Using ECI (a composite of 37+ benchmarks via IRT scaling), they find:
- Pre-April 2024 frontier improvement: ~8 ECI points/year
- Post-April 2024 frontier improvement: ~15 ECI points/year
- Breakpoint: April 8, 2024 (R² = 0.97 for piecewise linear fit)

The acceleration "roughly coincides with the rise of reasoning models and an increasing focus on reinforcement learning among frontier labs." They note this is consistent with METR time horizon showing a ~40% acceleration in October 2024.

**Important note**: The ECI breakpoint is April 2024, which corresponds to early reasoning model experiments (o1-preview wasn't released until September 2024). The o1 release coincides approximately with the METR acceleration, not the ECI acceleration. This suggests the acceleration in broad capability (ECI) may have started before the widespread RL release — possibly driven by improved pretraining quality or architecture, before the reasoning model wave hit publicly. This is the least-explained piece of the puzzle.

### GPT-4.5 as Negative Evidence for Pure Pretraining

GPT-4.5 (released Feb 2025) is the strongest negative evidence against pretraining scaling. It was described internally as "a huge model" — almost certainly the largest pretraining run OpenAI had done. OpenAI's own data shows that 90% of its $5B 2024 compute budget went to experiments and research rather than production training runs, making GPT-4.5 the product of the largest focused pretraining effort. Yet:
- It barely outperformed GPT-4o on most benchmarks
- It underperformed DeepSeek-V3 on math benchmarks, a model trained at a fraction of the compute cost
- OpenAI itself pivoted to emphasize "vibes" and quality-of-interaction rather than benchmark gains
- The community consensus was disappointment; one AI forecaster publicly moved their AGI timeline estimates later

This is direct evidence that pretraining scaling, at frontier compute levels (~$5B scale), is no longer the dominant driver of benchmark capability at the top of the frontier as of early 2025.

---

## The Densing Law

The Densing Law paper (Xiao et al., Nature Machine Intelligence, 2024) documents that "capability density" — defined as capability per parameter, measuring efficiency — doubles approximately every 3.5 months in open-source LLMs. This is a distinct claim from METR's time horizon doubling and from the ECI acceleration.

**What the Densing Law measures**: Performance per parameter count, not raw performance. A model achieving the same benchmark scores as a 6-month-older model but using half the parameters would show capability density improvement without showing capability improvement.

**Relationship to METR**: The Densing Law and METR's time horizon are measuring different quantities:
- Densing Law: efficiency frontier (cost per capability)
- METR: frontier capability ceiling (raw task ability)

These can move at different rates. A model with a higher capability density might not have higher raw capability if it's smaller. The Densing Law is more relevant to cost reduction than to frontier capability.

**Relationship to ECI**: Epoch AI notes that "frontier AI performance becomes accessible on consumer hardware within about 7 months" — a closely related finding. Models that 7 months ago required datacenter-scale inference now run on RTX 4090/5090 consumer cards. This matches the Densing Law's 3.5-month efficiency doubling: after two doublings (7 months), the prior frontier capability is available at roughly consumer hardware cost.

**Does the Densing Law confound METR?**: No. METR measures frontier model performance on tasks, not efficiency. The Densing Law describes a trend in a different dimension. However, the Densing Law matters for the economic sustainability question: even if frontier capability is driven by expensive RL at the top, those capabilities become affordable exponentially faster than before.

---

## The Benchmark Saturation Story: What's Actually Saturating

The saturation picture requires disaggregation:

**What is saturating**: MMLU (~90%+ for all frontier models), GSM8K (~99%), HumanEval (~90%+), many multiple-choice academic benchmarks. These are all benchmarks where the "difficulty ceiling" was designed for graduate students, not cutting-edge LLMs, and frontier models have exceeded them. MATH-500 is approaching saturation for the top cluster of models, with negligible gaps between top-5 performers.

**What is not saturating**: METR's time-horizon tasks (the benchmark is approaching ceiling for current models — fewer than 31 tasks take more than 8 hours, and METR acknowledges the suite is saturating for frontier models, prompting TH1.1 expansion); FrontierMath (Tier 4 problems remain in single-digit percentage territory even for top models); SWE-bench Pro (still wide spread between frameworks); ARC-AGI-2 (still challenging frontier models).

**The key distinction METR makes**: The reason traditional benchmarks saturate while time horizons keep growing is structural. A benchmark that asks multiple-choice questions about graduate-level material saturates when models can always pick the right answer. METR's metric asks "how long a task can the model complete?" — which scales with ability as an open-ended function. As models get better, they solve longer tasks, and METR can keep measuring because they add longer tasks. The benchmark can only saturate when models can complete arbitrarily long tasks.

**Are METR and benchmark saturation measuring the same thing?** They are measuring real capability, but from different ends of the capability distribution. Saturated benchmarks tell you where everyone is already at ceiling — they cease to distinguish capability levels. METR's metric is designed to stay in the informative range by measuring the frontier. They're not contradicting each other; they're looking at different parts of the capability curve.

---

## Reconciling the Contradictions

The hypothesis proposed in the assignment: all of the competing claims can be true simultaneously if we distinguish four capability layers. Let me test each:

### (i) Pretraining capability: Saturating at the frontier

**Evidence**: GPT-4.5's failure to advance the capability frontier despite being described as the largest pretraining run is the primary evidence. Epoch AI notes that "the main driving force for the decline in AI training costs is not cheap hardware, but algorithm optimization and data improvement" — suggesting pretraining efficiency improves but raw frontier pretraining at fixed compute stops delivering proportional gains. The Sutskever "age of scaling is over" statement aligns with this, though it was made before full RL reasoning model results were known. The consensus among well-calibrated observers is that pure pretraining (more data, more compute, same method) is hitting diminishing returns at the frontier.

**Confidence**: Strong evidence that pure pretraining scaling is decelerating, though "plateaued" is too strong — improvement continues, just at diminishing rates relative to compute spent.

### (ii) RL post-training capability: Rising fast, but with finite runway

**Evidence**: DeepSeek-R1-Zero proves RL provides huge gains from a good base model. OpenAI's o3 is 10x the RL compute of o1 with substantial benchmark gains. The ECI acceleration in April 2024 and METR's October 2024 acceleration both coincide with the rise of reasoning models (RL post-training). Epoch AI estimates that RL reasoning compute is still multiple orders of magnitude below the scale of pretraining compute — meaning there's substantial "runway" remaining on the RL scaling axis.

**The runway question**: Epoch AI's analysis suggests that if RL reasoning compute continues scaling at 10x per few months (the o1-to-o3 pace), it will converge with overall training compute scale within 1-2 years (from mid-2025 projection). At that point, the RL scaling rate would slow to match the overall compute growth rate (~4x/year), not the current 10x/few-months pace. Additionally, RL for reasoning relies on verifiable rewards (math, code, formal proofs) — fuzzy domains remain harder to scale via the same mechanism.

**Confidence**: Strong evidence that RL post-training is the dominant current driver of METR time-horizon gains. Runway is real but finite and domain-constrained.

### (iii) Harness/scaffolding capability: Contributing but NOT dominant in METR

**Evidence**: METR's own February 2026 experiment is the primary source. Claude Code and Codex do not beat METR's generic ReAct/Triframe scaffolds on time-horizon tasks. Scaffolding is therefore not the dominant contributor to METR's measured exponential. The SWE-bench Verified convergence of top models (within 0.8pp) and scaffolding dominance on SWE-bench Pro is a different phenomenon: scaffold optimization dominates when models are equal and benchmark is scaffold-sensitive. This tells us about the state of the engineering ecosystem, not about what drives METR's trend.

**Clarification of the harness story**: The "model dissolves into product" thesis is real, but it describes something different from what METR measures. METR measures capability potential; product engineering determines how much of that potential is captured in deployment. The product engineering revolution (Claude Code, Codex, Cursor) is real and matters enormously for economic value, but it's not what causes the METR doubling. The METR exponential is in model capability; the product engineering trend is about converting that capability into useful work.

**Confidence**: Strong evidence (METR's own controlled experiment) that scaffolding is not the dominant contributor to METR time-horizon gains.

### (iv) Cost per capability: Falling fast (Densing Law, inference cost reductions)

**Evidence**: Densing Law documents 3.5-month efficiency doubling for open-source models. Epoch AI documents that frontier capability becomes consumer-accessible in ~7 months. Inference cost has dropped 10-900x depending on task type over 2023-2025. This is robustly documented and well-supported.

**Confidence**: Strong evidence. This is the cleanest and most defensible trend.

---

## Verdict: Which Hypothesis Best Explains the Contradictions

**The dominant explanation**: RL post-training is the primary driver of METR time-horizon gains since approximately Q4 2024, building on a pretraining base that is still improving but at diminishing rates. The METR exponential is not a scaffold exponential. The Densing Law efficiency exponential is real but operates in a different dimension (cost, not raw capability). The benchmark saturation story correctly describes the ceiling for benchmarks designed for academic difficulty — those benchmarks are not measuring what METR measures. There is no contradiction between "MMLU is saturated" and "METR time horizons keep growing," because they are measuring capability at different points of the distribution.

**The unresolved piece**: The ECI acceleration breakpoint (April 2024) predates the public release of reasoning models (September 2024, o1-preview). Something was already improving frontier capability faster by April 2024 — possibly improved pretraining efficiency, possibly early internal RL work at labs, possibly architectural improvements. The METR acceleration registers in October 2024, closer to the o1 release. This 6-month gap is not explained by the available evidence.

**On GPT-4.5**: GPT-4.5 was not frontier because it relied on pure pretraining scaling, which is the weakest current lever. The models that are frontier (o3, Claude 3.7/4 series with extended thinking, DeepSeek-R1) all incorporate RL post-training. GPT-4.5's failure is evidence that pretraining alone no longer defines the frontier — it's now table stakes, not the frontier-setter.

**On the METR measurement validity**: Thomas Kwa's January 2026 limitations post explicitly notes that METR cannot distinguish whether gains come from base model, RL, or other post-training. The paper says "primarily driven by greater reliability and ability to adapt to mistakes, combined with better logical reasoning and tool use capabilities" — but this is a description of the skills involved, not a causal decomposition. The clean conclusion from Jurkovic's scaffold experiment is that harness is not dominant; but between base model and RL, METR has provided no direct evidence.

**The indirect evidence for RL dominance at the frontier**: The timing correlation is strong (METR acceleration ~October 2024 = o1 era), and the DeepSeek-R1-Zero ablation shows pure RL from a good base outperforms base alone dramatically. The base model gains (GPT-4.5 failure) are weak. Therefore RL is almost certainly the dominant driver, but this inference is correlational rather than directly demonstrated for the METR time horizon series.

---

## Key Findings

1. **METR's exponential is NOT primarily scaffolding.** Direct experimental evidence: METR's generic scaffolds perform equivalently to vendor-optimized commercial scaffolds (Claude Code, Codex). The time-horizon trend is not an artifact of scaffold engineering improvements. [Strong evidence — METR's own Feb 2026 controlled experiment.]

2. **RL post-training is the most likely primary driver of METR gains since Q4 2024.** The timing correlation (METR acceleration in Oct 2024 = o1 era), DeepSeek-R1-Zero ablation (pure RL from base model dramatically outperforms base model alone), and Epoch AI's ECI acceleration analysis all point to RL post-training. [Strong evidence for the conclusion; moderate confidence on exact attribution because METR provides no direct decomposition.]

3. **Pretraining scaling is decelerating at the frontier.** GPT-4.5 (the largest ever pretraining run) failed to advance the capability frontier meaningfully, underperforming models trained with RL. [Strong evidence.]

4. **Benchmark saturation and METR are measuring different things.** Traditional academic benchmarks saturate when models exceed their difficulty ceiling. METR's metric is designed to scale with capability. Saturation on MMLU ≠ saturation of AI capability. [Strong evidence — this is by construction of the metrics.]

5. **The Densing Law (efficiency doubling every 3.5 months) is real but measures a different dimension.** It describes cost-per-capability on the efficiency frontier, not raw frontier capability. It explains why open-source models close the gap with closed frontier models within 7 months, and why inference costs are plummeting. [Strong evidence for the Densing Law trend itself; the distinction from METR is analytic.]

6. **RL post-training has a finite runway.** Epoch AI's analysis suggests RL compute will converge with overall training compute within 1-2 years (from 2025), at which point its growth rate slows to match overall compute growth (~4x/year). The domain constraint (verifiable rewards primarily available in math, code, formal logic) further limits generalization. [Moderate evidence — this is a projection based on current scaling trends.]

7. **The SWE-bench scaffolding dominance story is benchmark-specific, not a general capability finding.** Scaffolding produces 22+ point swings on SWE-bench Pro with the same model, but this is because SWE-bench Pro is scaffold-optimizable and models have converged near ceiling. On METR's more general, scaffold-agnostic tasks, model capability — not scaffold — is the differentiator. [Strong evidence.]

8. **METR's own measurement is becoming unreliable near saturation.** The March 2026 modelling analysis (Barry) documents: a recently-corrected regularization error, sensitivity to task distribution, wide confidence intervals (factor of 2 in each direction), and potential bias from noisy task-length estimates (SIMEX suggests 25-40% overestimation of recent models' 50% TH). The benchmark is approaching ceiling for current frontier models. [Strong evidence — METR's own self-critique.]

---

## Assessment

The reconciliation holds. The four-layer decomposition — pretraining (decelerating), RL post-training (rising fast, finite runway), harness (not driving METR, but driving product value), cost/efficiency (Densing Law, exponential decline) — is the correct frame. These four trends can all be simultaneously true and do not contradict each other.

**The key answer to the question**: METR's time horizons and benchmark saturation are measuring different things, not the same thing from different angles. METR is measuring the moving frontier of capability in open-ended tasks; saturated benchmarks measure a fixed ceiling that models have exceeded. They are complementary, not contradictory.

**The implications for the cadence essay**:

- The "exponential" in METR is not a software-engineering exponential. The harness hypothesis is falsified by METR's own controlled experiment. The exponential lives in model capability, primarily in RL post-training gains.

- The "model dissolves into product" phenomenon is real but separate. Product engineering (Claude Code, etc.) determines how much capability gets converted to user value. It's a conversion efficiency story, not the capability generator.

- The cadence of releases is sustained by RL post-training scaling, which is still ascending its curve. When RL compute converges with overall training compute (estimated 1-2 years from 2025), the rate of model improvement will slow toward the overall compute growth rate (~4x/year). This suggests the current cadence is sustainable for perhaps 2-3 more years before it necessarily slows.

- The benchmark saturation problem is real but misleading. It misleads people into thinking capability improvement has stopped, when in fact pretraining-targeted benchmarks have just reached their ceiling. The frontier is still rising, just in a different dimension (RL-driven reasoning and task completion) that requires new measurement approaches like METR's.

**Remaining uncertainty**:

1. No direct decomposition exists in the literature attributing METR time-horizon gains to (a) base model vs. (b) RL post-training. The scaffold question is answered; the base-vs-RL split is not. This is the key empirical gap.

2. The ECI April 2024 acceleration predates the public o1 release by 5+ months. What caused the earlier acceleration is unexplained. Internal RL experimentation at labs, improved pretraining efficiency, or measurement artifacts are all possible.

3. METR's own methodology is showing strain as the benchmark saturates. The Barry (Mar 2026) analysis documents that reasonable modelling choices can reduce frontier model 50% time horizons by 25-40%. The "exponential" claim should be held with wider uncertainty bars than METR's headline numbers suggest.

4. RL scaling on verifiable rewards generalizes poorly to fuzzy, open-ended domains. If the next phase of capability requires reasoning about ambiguous human preferences, current RL methods may not deliver continued exponential progress.

---

## Sources

- METR, "Measuring AI Ability to Complete Long Software Tasks" (Kwa et al., 2025): https://arxiv.org/abs/2503.14499 | https://metr.org/blog/2025-03-19-measuring-ai-ability-to-complete-long-tasks/
- METR, "Clarifying limitations of time horizon" (Kwa, Jan 2026): https://metr.org/notes/2026-01-22-time-horizon-limitations/
- METR, "Time Horizon 1.1" (Jan 2026): https://metr.org/blog/2026-1-29-time-horizon-1-1/
- METR, "Measuring Time Horizon using Claude Code and Codex" (Jurkovic, Feb 2026): https://metr.org/notes/2026-02-13-measuring-time-horizon-using-claude-code-and-codex/
- METR, "Impact of modelling assumptions on time horizon results" (Barry, Mar 2026): https://metr.org/notes/2026-03-20-impact-of-modelling-assumptions-on-time-horizon-results/
- METR, Time Horizons live dashboard: https://metr.org/time-horizons/
- LessWrong, "METR's data can't distinguish between trajectories" (Moss, Feb 2026): https://www.lesswrong.com/posts/sBEzomgnYJmYHki9T/updated-metr-s-data-can-t-distinguish-between-trajectories
- Epoch AI, "AI capabilities progress has sped up" (Dec 2025): https://epoch.ai/data-insights/ai-capabilities-progress-has-sped-up
- Epoch AI, "How far can reasoning models scale?" (Josh You): https://epoch.ai/gradient-updates/how-far-can-reasoning-models-scale
- Epoch AI, Epoch Capabilities Index: https://epoch.ai/eci
- DeepSeek-R1 paper (arXiv 2501.12948, Nature June 2025): https://arxiv.org/abs/2501.12948
- Densing Law (Xiao et al., Nature Machine Intelligence 2024): https://www.semanticscholar.org/paper/Densing-law-of-LLMs/593eb9e34076a78ee1914bd8253b8b02de50e0eb
- Particula Tech, "Agent Scaffolding Beats Model Upgrades: 42% to 78% on SWE-Bench" (Mar 2026): https://particula.tech/blog/agent-scaffolding-beats-model-upgrades-swe-bench
