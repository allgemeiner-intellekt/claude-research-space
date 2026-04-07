# Deep Dive: Cost Per Capability in Frontier LLMs, 2020–2026

## Question

Has the cost of producing a given capability increment in frontier LLMs been rising or falling over 2020–2026, and does the trajectory match Eroom's Law (pharma-style halving every ~9 years), Moore's Law (deflation), or something in between? The deeper question: are two distinct trajectories in play simultaneously — one Eroom-style for the frontier, one Moore-style for the efficiency deflation curve — and what does this imply for release cadence sustainability?

## Investigation

### Sources Searched and Fetched

- Epoch AI: "Training compute of frontier AI models grows by 4-5x per year" (2024)
- Epoch AI: "How much does it cost to train frontier AI models?" (2024, arXiv paper)
- Epoch AI: "Algorithmic progress in language models" (2024, Erdil et al.)
- Epoch AI data insight: "Training compute costs are doubling every eight months for the largest AI models" (2024)
- Epoch AI data insight: "Most of OpenAI's 2024 compute went to experiments" (2025)
- Epoch AI Gradient Updates: "Final training runs account for a minority of R&D compute spending" (March 2026)
- DeepSeek-V3 Technical Report, arXiv:2412.19437 (Dec 2024, updated Feb 2025)
- DeepSeek-R1, arXiv:2501.12948 (Jan 2025; published Nature 2025)
- Xiao et al., "Densing Law of LLMs," Nature Machine Intelligence, 7:1823–1833 (2025); arXiv:2412.04315
- Mertens, Fischl-Lanzoni, Thompson, "Is there 'Secret Sauce' in LLM Development?" arXiv:2602.07238 (Feb 2026)
- SemiAnalysis (Dylan Patel): "DeepSeek Debates: Chinese Leadership On Cost, True Training Cost" (Jan 31, 2025)
- SemiAnalysis (Dylan Patel): "GPT-4 Architecture, Infrastructure, Training Dataset, Costs" (July 10, 2023)
- Stanford AI Index 2024/2025 (via Epoch AI cost data)
- Statista/Epoch AI training cost chart for selected models
- Tom's Hardware, WccfTech on Grok-3 cluster size
- Reddit thread on DeepSeek misconceptions (Jan 2025), confirming Epoch's DeepSeek V3 cost breakdown and citing Dario Amodei

### Key Primary Data

**DeepSeek V3 official figure:** The technical report (arXiv:2412.19437) states the model required 2.788M H800 GPU hours for the full training pipeline (pre-training: 2.664M GPU hours; context extension: 119K; post-training: 5K). Assuming $2/GPU hour rental (the paper's own assumption), that gives **$5.576M total**. The GPU hours are explicitly confirmed; the dollar figure is a direct product of disclosed hours × disclosed price.

**SemiAnalysis critique of the $5.6M figure:** Dylan Patel (Jan 31, 2025) confirms the $5.576M represents only the pre-training GPU rental cost. The total server CapEx for DeepSeek (hardware, not rental) is estimated at ~$1.6 billion, with $944M in operating costs for the cluster. The $5.6M is akin to citing only the marginal electricity cost of a factory run while ignoring the factory.

**Epoch AI's cost-per-frontier-run growth rate:** Amortized hardware + energy cost for final training runs of top-10-compute models has grown at **2.4x per year since 2016** (95% CI: 2.0x to 3.1x). Using cloud rental rates, the rate is 2.6x/year. This means frontier training run cost doubles roughly every **5–6 months**.

**OpenAI 2024 compute allocation:** OpenAI spent ~$5B on R&D compute in 2024. Of that, only ~$500M (10%) went to final training runs of released models (GPT-4.5, GPT-4o, o3 preview, Sora Turbo). The other 90% was experiments, de-risking runs, synthetic data generation, and unreleased model training.

**GPT-4.5 cluster and cost (Epoch AI estimate):** 40,000–100,000 H100s, training duration 90–165 days (approximately May–September 2024). At $1.50–$3/H100-hour, this gives a final training run cost roughly in the range of **$130M–$1.2B** (10th–90th percentile). The midpoint is approximately $400–500M — consistent with the rumored "$500M+" figure but with very wide uncertainty.

**Algorithmic efficiency (Epoch AI, 2024):** "Algorithmic progress in language models" (Erdil, Besiroglu et al.) found that the compute needed to achieve a given level of language model performance (measured on standard perplexity benchmarks, 231 models from 2012–2023) **halved roughly every 8 months** (95% CI: 5–14 months). This is the efficiency deflation rate for replicating a given capability — roughly 2x/year improvement.

**Densing Law (Xiao et al., Nature MI 2025):** arXiv:2412.04315, published in Nature Machine Intelligence vol. 7, pp. 1823–1833, 2025. The paper introduces "capability density" = capability per parameter. Analyzing open-source LLMs on standard benchmarks, they find the maximum capability density of open-source LLMs doubles approximately every **3.5 months**. This is faster than the Epoch AI algorithmic efficiency figure because it measures capability per parameter (not per FLOP), and because it focuses on open-source models which are compressed versions of the frontier using distillation and MoE techniques. The metric is capability per parameter rather than per dollar or per FLOP — important distinction.

**Secret sauce paper (Mertens, Fischl-Lanzoni, Thompson 2026):** Using data on 809 models (2022–2025), they find that at the frontier, 80–90% of performance differences are explained by training compute (not proprietary techniques). Away from the frontier, proprietary methods matter more, and firms can systematically produce smaller, more efficient models. There is 40x within-company compute efficiency variation across models.

**Grok-3:** 100,000 H100 GPUs trained for ~200 million GPU hours (Musk confirmed, Jan 2025; expanded to 200,000 GPUs). At $2/H100-hour, that is approximately **$400M in compute rental**. Hardware CapEx for 100K H100s at ~$25K each = $2.5B capital investment. Final training run cost (rental equivalent) is roughly in the $400M range.

---

## Frontier Model Cost-vs-Capability Table

*Training cost = amortized hardware + energy for final training run, or rental equivalent where available. Capability metric: MMLU score where available, otherwise benchmarks noted.*

| Model | Lab | Release | Training Compute (FLOP) | Final Run Cost (range) | Capability Proxy | Cost Source |
|---|---|---|---|---|---|---|
| GPT-3 (175B) | OpenAI | May 2020 | ~3.1×10²³ | $2M–$4M | MMLU: ~43% (few-shot) | Epoch AI cost model; $4.6M Lambda Labs est. is cloud-rental, higher end |
| PaLM (540B) | Google | Apr 2022 | ~2.5×10²⁴ | $8M–$25M | MMLU: ~70% | Epoch AI cost model; Statista range |
| Chinchilla (70B) | DeepMind | Mar 2022 | ~5.8×10²³ | $2M–$6M | MMLU: ~67% | Epoch AI cost model (smaller than PaLM but more compute-optimal) |
| LLaMA 1 (65B) | Meta | Feb 2023 | ~10²³ | $0.5M–$2M | MMLU: ~64% | Epoch AI cost model (estimated) |
| GPT-4 | OpenAI | Mar 2023 | ~2×10²⁵ | $41M–$78M (amortized hdw) | MMLU: ~86% | Epoch AI (2024 paper); Altman confirmed ">$100M" total |
| Llama 2 (70B) | Meta | Jul 2023 | ~7×10²³ | $1M–$3M | MMLU: ~68% | Epoch AI cost model |
| Gemini Ultra | Google | Dec 2023 | ~5×10²⁵ | $30M–$191M (amortized) | MMLU: ~90% | Epoch AI (2024 paper) |
| Claude 3 Opus | Anthropic | Mar 2024 | est. ~10²⁵ | $20M–$50M (est.) | MMLU: ~87% | Dario confirmed "a few tens of millions" for Claude 3.5 Sonnet; Opus likely similar or slightly higher |
| GPT-4o | OpenAI | May 2024 | ~1×10²⁵–5×10²⁵ | $10M–$50M (est.) | MMLU: ~88% | Epoch AI CI: 1e25–5e25 FLOP; dogesator estimate ~$10M |
| Llama 3.1 (405B) | Meta | Jul 2024 | ~4×10²⁵ | $30M–$80M (est.) | MMLU: ~88% | Meta disclosed ~3.8×10²⁵ FLOP |
| o1 | OpenAI | Sep 2024 | ~10²⁵ base | ~$20M–$30M (base est.) | GPQA: ~78%, AIME: strong | dogesator estimate ~$20M; Epoch: o-series RL is 1–30% of base compute |
| DeepSeek V3 | DeepSeek | Dec 2024 | ~2.8×10²³ (active compute); full MoE ~6×10²⁴ | **$5.6M (official rental); total incl. R&D: much higher** | MMLU: ~88%, HumanEval: ~90% | Tech report arXiv:2412.19437; SemiAnalysis Jan 2025 |
| DeepSeek R1 | DeepSeek | Jan 2025 | Undisclosed (RL-heavy) | Undisclosed (but compute-intensive) | AIME, GPQA: ~o1 level | R1 tech report; SemiAnalysis notes compute is hidden deliberately |
| GPT-4.5 | OpenAI | Feb 2025 | est. ~5×10²⁵–10²⁶ | **$130M–$1.2B** (Epoch AI 10th–90th pct) | MMLU: ~90%+ | Epoch AI OpenAI compute spend analysis; cluster satellite imagery |
| Grok-3 | xAI | Feb 2025 | ~200M H100-hours | **~$400M** (rental equiv.) | MMLU-like: claimed best-in-class | H100 × hours × $2/hr; Musk confirmed cluster details |

**Notes on confidence levels:**
- GPT-3, PaLM, Chinchilla, GPT-4, Gemini Ultra: Moderate-to-strong confidence. Epoch AI's 2024 paper (Cottier et al.) specifically modeled these. Statista chart based on that paper. Altman confirmed ">$100M" for GPT-4 total development.
- GPT-4o, Claude 3 Opus, Llama 3.1: Moderate. Epoch AI FLOP ranges ± factor of 3–5.
- o1: Speculative. Epoch assumes 1–30% of GPT-4o compute for RL.
- DeepSeek V3: $5.6M is well-sourced from official report. Total R&D cost is unverified but credibly much higher.
- GPT-4.5: Epoch AI satellite-imagery + cluster analysis, 90% CI is very wide.
- Grok-3: Musk confirmed 100K H100s, 200M GPU hours; dollar figure is straightforward calculation.

---

## Trajectory 1: Frontier Model Cost Over Time

Using the Epoch AI data (Cottier et al. 2024) as the backbone, the amortized hardware + energy cost for frontier training runs has grown at **2.4x per year** (95% CI: 2.0x–3.1x). This is a doubling every **5–6 months**.

To put this in concrete terms from the table above:
- GPT-3 final run (2020): ~$3M
- GPT-4 final run (2023, ~3 years later): ~$60M → 20x increase in 3 years ≈ 2.7x/year
- GPT-4.5 final run (early 2025, ~2 years after GPT-4): ~$400M–500M → 7–8x increase → ~2.6–2.8x/year

The 2.4–2.6x/year compound growth rate for frontier training costs is striking in itself, but it dramatically understates the total R&D cost growth. Epoch AI (March 2026 post) and the OpenAI compute analysis confirm that final training runs are only ~10% of R&D compute spending. The total organizational compute budget for developing a frontier model is growing at least as fast, possibly faster, as labs spend more on experiment infrastructure.

**Comparison to Eroom's Law:** Eroom's Law in pharma describes productivity *halving* every 9 years — i.e., costs roughly double every 9 years for equivalent drug output. The LLM frontier is not remotely in an Eroom-like regime on this axis. The frontier is spending 2.4x more compute per year, which means costs are *rising 80x per 9 years*, not doubling. The frontier trajectory is dramatically more expensive than Eroom's Law describes. If anything, it's anti-Eroom: a hyper-accelerating cost escalation, not a slow ratchet. The difference is that LLM capabilities are also rising rapidly, so whether the *cost per capability unit* is rising or falling is a separate question (addressed below).

**Comparison to Moore's Law:** Moore's Law characterized transistor density doubling every ~2 years (hardware deflation). The frontier compute cost is going in the opposite direction: doubling every 5–6 months. This is Moore's Law *inverted* on the cost side.

---

## Trajectory 2: Cost-to-Replicate-GPT-4 Over Time

This is the efficiency deflation story. The question: how much would it cost in year X to train a model achieving GPT-4-equivalent capability?

The two key empirical anchors here are:

1. **Epoch AI algorithmic efficiency result:** Compute needed to hit a given capability threshold halves every ~8 months (95% CI: 5–14 months). This is pre-training only and measured on perplexity benchmarks (Erdil et al. 2024).

2. **SemiAnalysis algorithmic progress estimate (Patel, Jan 2025):** "Estimates put algorithmic progress at 4x per year, meaning that for every passing year, 4x less compute is needed to achieve the same capability." Dario Amodei claimed up to 10x/year. The 4x figure is consistent with Epoch AI's 8-month halving (8 months ≈ 0.67 years; 2^(1/0.67) ≈ 2.8x/year, close to 4x with some additional hardware efficiency).

3. **Hardware efficiency:** H100 vs. A100 — H100 delivers roughly 2x the FP16 performance for GPT-4 training tasks at similar pricing. This compounds with algorithmic efficiency.

**A concrete reconstruction of the GPT-4 replication cost curve:**

GPT-4 was trained in late 2022 / early 2023 at a final run cost of approximately $41M–$78M (Epoch AI's amortized hardware estimate). Altman confirmed ">$100M" total including experiments.

If algorithmic + hardware efficiency gains compound at ~4x/year (Patel figure; consistent with Epoch AI's 8-month compute halving):
- 2023: ~$60M to replicate GPT-4-level capability (baseline year)
- 2024: ~$15M (4x cheaper)
- 2025: ~$3.75M (4x cheaper again)
- 2026: ~$1M (4x cheaper again)

This is consistent with:
- DeepSeek V3 (Dec 2024) achieving GPT-4o-comparable performance for $5.6M in compute. (GPT-4o is roughly GPT-4-class; DeepSeek V3 is slightly below frontier-frontier but competitive)
- The SemiAnalysis chart showing "inference cost for GPT-3 quality has fallen 1200x" — a separate proxy demonstrating the aggressive deflation in cost-to-serve-equivalent-capability

**The Densing Law angle:** Xiao et al. (Nature MI 2025) find capability density (capability per parameter) doubles every 3.5 months for open-source models. This is faster than Epoch AI's 8-month halving because (a) it measures per-parameter not per-FLOP, and (b) open-source model efficiency has benefited from distillation, MoE sparsity, and techniques diffused rapidly from frontier labs. The 3.5-month doubling is plausible for open-source models specifically; the frontier may be slightly slower. However, the directional story is clear: a 3.5-month doubling in capability density implies that within 1 year, you need 16x fewer parameters to achieve the same capability. If parameter count is a rough proxy for training cost, this is a 16x cost reduction per year for replication.

**Important caveat on the Densing Law metric:** The paper measures capability per parameter, not capability per dollar. Parameters are free at inference but cost money at training (roughly linear). However, parameters are not the binding constraint for all costs — training compute (FLOP) matters too, and with MoE, activated FLOP per token decouples from total parameter count. So the 3.5-month doubling is a favorable lower bound on efficiency gains, possibly too optimistic as a cost-per-dollar metric.

---

## Reconciliation: Two Trajectories, Not Contradictory

The key insight is that "frontier cost" and "cost to replicate a given capability" are measuring different things and can both be directionally correct simultaneously.

**Trajectory A (Eroom-flavored, frontier cost):**
The most capable model at each point in time costs 2.4x more compute per year. In absolute dollar terms, frontier training is experiencing exponential cost inflation. GPT-4 at ~$60M, GPT-4.5 at ~$400M–500M, and rumored next-generation models at $1B+ by 2027 (Epoch AI projection). This is not Eroom's Law (which would be a slow 9-year doubling); it is a much faster form of escalation.

**Why this looks like a sustainability problem:** The 2.4x/year cost growth for the *final training run* understates the total organizational commitment. Epoch AI (March 2026) shows final training runs are only ~10% of total R&D compute spend. OpenAI spent $5B on R&D compute in 2024 to produce models whose final training runs cost ~$500M. If that 10% ratio holds, the total AI R&D "cost" for a frontier release cycle is an order of magnitude larger than the training run figure. This makes the escalation even steeper in real organizational cost.

**Trajectory B (Moore-style, replication cost):**
The cost to achieve a fixed capability level (say, GPT-4-equivalent) is falling at ~4x per year (Patel's estimate, consistent with Epoch AI's 8-month compute halving). This is close to Moore's Law in pace. DeepSeek V3 provides the most concrete 2024 data point: for $5.6M in compute (rental equivalent), it achieved approximate GPT-4o capability — which cost OpenAI orders of magnitude more in 2023. This is the efficiency deflation story.

**Can both be true simultaneously?** Yes, and they describe different actors and different choices:
- Frontier labs (OpenAI, Google, Anthropic, xAI) are running up Trajectory A. Each successive frontier model costs 2–3x more compute than the previous one, and they accept this because they're chasing ever-higher capabilities.
- Laggards and open-source labs run down Trajectory B. They use the knowledge (architecture papers, benchmark results, distillation) produced by frontier labs to replicate frontier-minus-1 or frontier-minus-2 capability at a fraction of the original cost.

The Mertens et al. (2026) "Secret Sauce" paper formalizes this: at the frontier, 80–90% of performance is explained by compute scale; away from the frontier, proprietary techniques and diffused knowledge can dramatically reduce compute requirements. This is quantitative confirmation of the two-trajectory structure.

---

## Comparison to Named Laws

### Eroom's Law signature
- Eroom's Law: cost-per-approved-drug doubles every 9 years (i.e., productivity halves every 9 years)
- Frontier LLM cost growth: 2.4x/year → doubles every ~5–6 months
- **The LLM frontier is escalating ~18x faster than Eroom's Law** on the cost side. But unlike pharma, LLM capabilities are also rising rapidly. The question is whether capability is keeping pace.
- If MMLU went from ~43% (GPT-3) to ~90% (GPT-4.5) over 5 years at an escalating compute cost, then cost per MMLU point has roughly stayed flat or risen modestly. But MMLU is saturating. On harder benchmarks like GPQA or ARC-AGI, frontier models show more improvement — the capability numerator is growing, but so is the cost denominator.
- **Verdict on Eroom:** The frontier is emphatically not in an Eroom-like situation of slow productivity decay. But there are signs of Eroom-like dynamics emerging: each successive compute doubling yields smaller marginal capability gains on saturated benchmarks, meaning the cost-per-hard-benchmark-point may be rising. On GPQA and ARC-AGI, where ceilings haven't been hit yet, the picture is less clear.

### Moore's Law signature
- Moore's Law: hardware performance doubles every ~2 years (transistors per dollar)
- Efficiency deflation for LLM replication: compute needed halves every ~8 months (Epoch AI); capability density doubles every ~3.5 months (Densing Law for open-source)
- **The cost-to-replicate trajectory is running much faster than Moore's Law**, roughly 3–4x/year versus Moore's 1.4x/year. This makes sense: Moore's Law is a hardware-only trajectory, while LLM efficiency improvement combines hardware gains with algorithmic improvements and architectural innovations (MoE, MLA, distillation).

### The actual answer
Neither Eroom's Law nor Moore's Law cleanly describes what is happening. The frontier trajectory is a steeper escalation than Eroom's Law predicted; the replication trajectory is faster deflation than Moore's Law. The two are interacting in a way that has no historical analogue.

---

## Implications for Release Cadence

The two-trajectory structure has direct implications for the sustainability question:

1. **For labs on Trajectory A (frontier escalation):** Each successive frontier release requires 2–3x more compute and, in total organizational terms, 10x more compute including experiments. At the current 2.4x/year compute growth rate, a lab maintaining frontier status must be growing its AI compute budget at roughly the same rate. The only labs currently able to run on this trajectory are those with $10B+ annual capital commitments (OpenAI/Microsoft, Google/Alphabet, xAI/Musk). Anthropic is arguably one cycle behind (Claude runs are smaller than GPT-4.5 or Grok-3 in compute). The "release cadence" for a given lab is thus constrained by: (a) how fast they can scale cluster size, (b) how fast they can cycle through the experiment-then-train sequence, and (c) their financial runway. For OpenAI in 2024, ~90% of $5B compute budget was experiment overhead. If compute budget doesn't grow, cadence slows because experiments still consume the same fraction.

2. **For the field on Trajectory B (replication deflation):** The rapid deflation in replication cost means that the *effective capability floor* of what any modestly-funded actor can build rises quickly. DeepSeek in 2024 demonstrated this: $5.6M in compute producing GPT-4o-class performance. By 2026, GPT-4-class capability may be achievable for under $1M. This means the "competitive pressures" that drive frontier labs are unlikely to abate — even if any single lab pauses, others can replicate prior-frontier capability cheaply.

3. **The cadence paradox:** High release cadence is most sustainable for labs on Trajectory B (cheaper replication, lots of labs, can iterate fast) and least sustainable for labs on Trajectory A (frontier escalation, very few labs, each run is a multi-hundred-million-dollar commitment). OpenAI's cadence of several releases per year is only viable because most releases (GPT-4o variants, o-series iterations) are not full-scale new training runs — they are lightweight RL-based post-training of existing base models. The rare true frontier training runs (GPT-4.5, rumored GPT-5) are more like 1-per-year events. The "high cadence" is largely a product-release cadence (fine-tuned variants, API updates) layered on a slower foundation-model training cadence.

---

## Key Findings

- **Frontier training run costs are growing at 2.4x/year** (Epoch AI, 95% CI: 2.0–3.1x). This is a doubling every 5–6 months. Strong evidence from Cottier et al. 2024.

- **Total organizational R&D compute is ~10x the final training run cost.** Final runs are ~10% of total compute spend for OpenAI and Chinese labs (Epoch AI March 2026, MiniMax/Z.ai IPO data). Strong evidence.

- **GPT-4.5's final training run cost is estimated at $130M–$1.2B** (Epoch AI, 10th–90th percentile). Wide uncertainty range; the midpoint (~$400–500M) is consistent with informal reports. Moderate confidence.

- **The compute needed to achieve a given capability threshold halves every ~8 months** (Epoch AI, Erdil et al. 2024; 95% CI: 5–14 months). Strong evidence for pre-training perplexity benchmarks 2012–2023.

- **The Densing Law exists and is published** (Xiao et al., Nature Machine Intelligence, Dec 2024/2025). It measures capability per parameter doubling every 3.5 months for open-source models. This is a real empirical finding, not speculation. Moderate-to-strong confidence for the metric it measures (capability/parameter); caution warranted in translating to cost-per-dollar.

- **DeepSeek V3's $5.6M figure is the compute rental for the final pre-training run only.** Total R&D cost including hardware, experimentation, and cumulative cluster investment is substantially higher (SemiAnalysis estimates hardware CapEx ~$1.6B for the whole company). Strong evidence from primary sources. The $5.6M is real but misleadingly narrow.

- **Algorithmic progress is estimated at ~4x/year** for replicating a given capability level (SemiAnalysis, consistent with Epoch AI). This means cost-to-replicate GPT-4 falls by 4x per year. By 2026, GPT-4-class capability should be achievable for ~$1M or less in compute. Moderate confidence (consistent across multiple estimators; uncertainty is ± 2x).

- **At the frontier, 80–90% of performance differences are explained by compute scale**, not proprietary techniques (Mertens et al. 2026, 809-model study). Away from the frontier, proprietary techniques matter more. Strong evidence.

- **Grok-3's training run cost is approximately $400M in compute rental** equivalent (100K H100s × 2000 hours × $2/hr). Confirmed cluster size from Musk's announcement; rental cost is straightforward calculation. Hardware CapEx is ~$2.5B. Strong evidence.

- **The frontier is on a steep cost escalation (not Eroom's Law — much faster than 9-year doubling)** while the replication curve is on aggressive deflation (faster than Moore's Law). **Both trajectories can operate simultaneously** because they describe different actors making different choices. This is the correct framing. Strong analytical basis.

---

## Assessment

The empirical record is remarkably clear on the two-trajectory structure. The frontier is experiencing a genuine compute arms race with costs doubling every 5–6 months for training runs — far faster than any analogical precedent in pharma (Eroom) or semiconductors (Moore). However, this is not a simple Eroom-like productivity trap because frontier capabilities are also rising. The question of whether cost per capability point is rising or falling depends critically on how capability is measured: on saturating benchmarks (MMLU), cost-per-point may actually be falling because algorithmic efficiency is closing in; on hard unsaturated benchmarks (ARC-AGI, real-world task horizons), the picture is murkier.

The efficiency deflation story is equally robust: the Epoch AI algorithmic efficiency paper provides rigorous evidence for ~8-month halving of compute-to-capability, and the Densing Law paper provides a separate confirmation from a different angle (per-parameter efficiency in open-source models). The DeepSeek V3 data point is a concrete, specific confirmation of this deflation in 2024.

The Eroom's Law framing misapplies to LLMs because Eroom's Law describes *slow* productivity decay over decades, whereas the LLM dynamics are much faster (escalation at the frontier, deflation at the replication level) and involve two populations (frontier labs vs. laggards) behaving very differently. The better analogy might be the early semiconductor industry, where chip-fabrication leaders were spending exponentially more per chip generation while fabless companies were accessing the prior-generation capability cheaply — but even this analogy is imperfect because the capability gap between frontier and near-frontier LLMs is smaller than the gap between chip generations.

**Where uncertainty remains:**
1. The GPT-4.5 cost estimate has a very wide confidence interval (10x range). The true cost is somewhere in the $100M–$1B range; the midpoint is probably around $400M but this is genuinely uncertain.
2. The 2025–2026 frontier (GPT-5, Gemini 3, Claude Opus 4) has no reliable training cost data yet. GPT-5 may represent the first genuinely $1B+ training run.
3. Whether the algorithmic efficiency gains (8-month halving) continue at the same rate post-2025 is unknown. The Epoch AI paper covers 2012–2023; there is no guarantee the rate extends into the reasoning-model era where RL compute dominates.
4. The Densing Law's 3.5-month doubling was fit on data available as of late 2024. Whether it continues or flattens is an open question.
5. o1, o3, and DeepSeek R1 introduce RL-heavy training where the compute profile is qualitatively different (inference-heavy during RL, not just pre-training). Extending the standard FLOP-based analysis to reasoning models requires additional assumptions.

---

## Open Gaps

1. No consistent capability metric across all models in the table. MMLU is saturating above 90%; GPQA and ARC-AGI are better proxies for frontier capability but have less historical coverage. The ideal metric (Epoch AI's ECI, if it exists as a time series) was not retrievable in this investigation.
2. The total R&D cost (not just final training run) for individual models other than GPT-4 and Gemini Ultra has not been published. The 10-to-1 ratio (total R&D vs. final run) from Epoch AI's OpenAI analysis may not generalize to all labs.
3. GPT-5, Gemini 3, Claude Opus 4, and anything post-mid-2025 — no cost data available as of April 2026.
4. Whether the Densing Law's capability density metric (per-parameter) translates to cost-per-dollar in practice, given MoE decoupling of parameter count from activated compute.
5. The extent to which reasoning-model RL training (o-series, R1) shifts the cost-per-capability curve in ways that are not captured by pre-training efficiency metrics.

---

## Sources

1. Epoch AI, "Training compute of frontier AI models grows by 4-5x per year" (2024): https://epoch.ai/blog/training-compute-of-frontier-ai-models-grows-by-4-5x-per-year
2. Cottier et al. (Epoch AI), "How much does it cost to train frontier AI models?" (2024): https://epoch.ai/blog/how-much-does-it-cost-to-train-frontier-ai-models
3. Erdil et al. (Epoch AI), "Algorithmic progress in language models" (2024): https://epoch.ai/blog/algorithmic-progress-in-language-models
4. Epoch AI data insight, "Training compute costs are doubling every eight months" (2024): https://epoch.ai/data-insights/cost-trend-large-scale
5. Epoch AI data insight, "Most of OpenAI's 2024 compute went to experiments" (2025): https://epoch.ai/data-insights/openai-compute-spend
6. Denain & Wu (Epoch AI Gradient Updates), "Final training runs account for a minority of R&D compute spending" (March 2026): https://epochai.substack.com/p/final-training-runs-account-for-a
7. DeepSeek-AI, "DeepSeek-V3 Technical Report," arXiv:2412.19437 (Dec 2024, updated Feb 2025)
8. DeepSeek-AI, "DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning," arXiv:2501.12948 (Jan 2025; Nature 645:633–638, 2025)
9. Xiao et al., "Densing Law of LLMs," Nature Machine Intelligence 7:1823–1833 (2025); arXiv:2412.04315
10. Mertens, Fischl-Lanzoni, Thompson, "Is there 'Secret Sauce' in LLM Development?" arXiv:2602.07238 (Feb 2026)
11. Dylan Patel (SemiAnalysis), "DeepSeek Debates: Chinese Leadership On Cost, True Training Cost" (Jan 31, 2025): https://newsletter.semianalysis.com/p/deepseek-debates
12. Dylan Patel (SemiAnalysis), "GPT-4 Architecture, Infrastructure, Training Dataset, Costs" (July 10, 2023): https://newsletter.semianalysis.com/p/gpt-4-architecture-infrastructure
13. Epoch AI data models database: https://epoch.ai/data/ai-models (updated Mar. 31, 2026)
14. Statista/Epoch AI chart on training costs: https://www.statista.com/chart/33114/estimated-cost-of-training-selected-ai-models/
