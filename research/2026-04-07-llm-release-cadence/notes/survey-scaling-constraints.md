# Survey: Binding Constraints on Continued LLM Scaling as of 2026

## What I Searched

- Epoch AI data on training compute FLOP trajectories, model counts, power projections
- HBM supply crisis 2026 (SK Hynix, Micron, Samsung)
- Stargate, xAI Colossus, Project Rainier infrastructure data
- IEA Electricity 2026 report
- Villalobos et al. / Epoch AI data exhaustion paper
- Synthetic data / model collapse literature (Semantic Scholar)
- DeepSeek-R1 training cost and efficiency disruption
- AI researcher talent market (Reuters, The Register)
- Scaling law debate: "Orion plateau," Ilya Sutskever statements, GPT-5.x releases
- Chinchilla paper (Hoffmann et al. 2022) and robustness analysis (Schaeffer et al. 2025)
- OpenAI $1.15 trillion infrastructure spend breakdown (Tomasz Tunguz analysis)
- Meta Avocado delay / The Synthesis reporting on compute-to-capability gap

---

## 1. Compute / Hardware Constraint

### FLOP Trajectory (Epoch AI data, February 2025 post)

The training compute doubling time for frontier models has held at roughly 4–5x per year through 2025:

| Model | Approximate Training Compute | Year |
|---|---|---|
| GPT-3 | ~3e23 FLOP | 2020 |
| GPT-4 | ~2e25 FLOP | 2023 |
| Grok-2 | ~3e25 FLOP | 2024 |
| Grok-3 (xAI Colossus) | ~4–5e26 FLOP | Feb 2025 |

Grok-3 was the first released model known to exceed 1e26 FLOP, trained on a cluster that expanded from 100k to 200k NVIDIA H100 GPUs over ~90 days. Epoch AI estimates ~4–5x yearly growth in frontier training compute has been the trend, and projects ~30 models above 1e26 FLOP by 2027, and ~200 by 2030 if current investment trends continue.

**Source:** Epoch AI LinkedIn post (Feb 23, 2025); Epoch AI "How many AI models will exceed compute thresholds?" report; Epoch AI AI Models database (updated March 31, 2026).

### Chip Supply: HBM Bottleneck

This is a genuine, near-term hard constraint. As of early 2026:

- SK Hynix and Micron have their entire **2026 HBM3E production sold out** years in advance.
- NVIDIA's Blackwell B200 GPU requires **192 GB of HBM3E** — a 140% increase over the H100's 80 GB. Multiplied by millions of units, this has created a demand tsunami manufacturing cannot meet.
- Samsung — the third potential supplier — has failed to qualify its 12-layer HBM3E chips to NVIDIA's standards, leaving the duopoly of SK Hynix + Micron as the sole functional suppliers.
- SK Hynix is committing $30B+ to new capacity (including a $15B advanced packaging plant in Indiana and $14.6B M15X fab in South Korea); Micron raised its 2026 capex to $20B. But: **new capacity won't materially relieve the bottleneck before 2026–2027**.

**Assessment:** HBM is a real bottleneck *today*, limiting GPU ramp speed. It's not a fundamental ceiling — supply capacity is being built — but it creates ~1–2 year lags between demand spikes and relief. It constrains the *rate* of cluster expansion, not the ultimate ceiling.

**Source:** EnkiAI "HBM Supply Crisis 2026" (Feb 28, 2026).

### Cluster Size / Power: The Megacluster Era

**Stargate (OpenAI / SoftBank / Oracle):**
- Announced January 21, 2025. Target: 10 GW of AI compute capacity across the US.
- By late 2025: 8 GW planned, $450B+ committed, ~$500B total commitment over four years.
- Abilene, Texas flagship: 1.2 GW single campus, planned for 400,000 NVIDIA GB200 Blackwell GPUs.
- Five additional US sites announced; total to ~7 GW across Texas, New Mexico, Ohio.
- Power sourcing strategy: mix of renewables, natural gas, onsite generation, grid interconnects.
- Planned SMRs (small modular reactors) for baseload.

**xAI Colossus (Memphis):**
- 200,000 H100/H200 GPUs; cluster estimated at $3–5B hardware cost.
- Power draw: ~100,000 GPUs at ~700W each = ~70 MW for compute alone (full 200k = ~140 MW).
- Compared to city-scale power: 100 MW powers roughly 75,000 homes.

**Project Rainier (Amazon / Anthropic):**
- $11B Indiana facility opened October 2025 on 1,200 acres.
- 500,000 Trainium2 chips (Amazon's custom non-Nvidia silicon), doubling to ~1M by end 2025.
- Final campus: 30 buildings, 2.2 GW electricity draw — enough to power 1.6 million homes.
- **This single facility represents 2.2 GW when complete.**

**Meta's Hyperion:** 2 GW planned for Louisiana.

**Power demand trend (Epoch AI / EPRI paper, August 2025):**
- Frontier training power draw has been growing at **2.2x per year**.
- Current frontier runs exceed **100 MW**.
- Projection: individual training runs could reach **4–16 GW by 2030**.
- Total AI power capacity: **>100 GW worldwide, >50 GW US by 2030**, approaching **5% of US total generation capacity**.
- US total generation capacity in 2025: roughly 1,200 GW. 5% = 60 GW. This is achievable but requires massive new construction.

**IEA Electricity 2026 report:** Confirms "growing consumption is also coming from some of the most dynamic segments of global economies, such as artificial intelligence (AI), data centres, and evolving technological innovations" — a 5-year forecast was added for the first time covering 2026–2030, reflecting acknowledged urgency. (The full quantitative figures from this report are behind a paywall and not fully accessible here.)

**Grid interconnection and power sourcing are the primary current constraint on cluster size.** 10 GW is near a national-scale commitment. The 2030 4–16 GW-per-run scenario depends on grid expansions that are not yet planned. Networking/interconnect within clusters (InfiniBand / NVLink at scale) is an engineering challenge but not yet a hard wall — clusters of 200,000 GPUs are operating.

**Source:** IntuitionLabs Stargate article (rev. Feb 21, 2026); DataCenterFrontier Stargate article; Introl.com Stargate blog (Dec 2025); CNBC Project Rainier (Oct 29, 2025); Epoch AI power projection substack (Aug 11, 2025).

---

## 2. Data Constraint

### Data Exhaustion: Villalobos et al. / Epoch AI (2024)

**Key findings from the Epoch AI paper "Will we run out of data to train large language models?"**

- Total effective stock of high-quality human-generated public text: **~300 trillion tokens** (90% CI: 100T–1000T).
- This is 5x larger than their 2022 estimate — revised upward because: (1) carefully filtered web data outperforms curated corpora (Penedo et al. 2023), and (2) models can train on several epochs without severe degradation (Muennighoff et al. 2023).
- Projection: **80% CI that this stock will be fully utilized between 2026 and 2032**.
- Under compute-optimal (Chinchilla) scaling: data sufficient for a model trained with ~5e28 FLOP, expected ~2028.
- Under overtraining (like Llama-3-70B, which was overtrained 10x): data exhaustion arrives **between 2025 and 2027**.
- Llama-3-70B overtraining factor = 10x; at 100x overtraining, stock exhausted by 2025.
- "Undertraining" (larger models, fixed dataset) can deliver equivalent of ~2 extra orders of magnitude of compute-optimal scaling before hitting a plateau. Not a long-term solution.

**Key caveat:** The paper explicitly notes that synthetic data, other modalities (image/video), and private data exist but weren't studied because: (a) synthetic data has only been shown to reliably help in narrow domains (math, code), (b) other modalities haven't demonstrated usefulness for general text reasoning at scale.

**Assessment:** Public high-quality text data is already at or approaching exhaustion for frontier overtraining regimes. This is not theoretical — it's a live constraint as of 2025–2026. The key unknown is how much synthetic data can substitute.

**Source:** Epoch AI "Will we run out of data?" blog post (2024); links to arxiv 2211.04325.

### Synthetic Data: Model Collapse Risk

Academic literature (2024–2025) confirms model collapse is a real risk:

- "Model autophagy disorder" (MAD): iterative self-consuming training degrades quality and diversity.
- Alemohammad et al. (SIMS, 2024): standard synthetic training loops go "MAD"; their SIMS approach using synthetic data for *negative guidance* mitigates this for image diffusion.
- Ferbach et al. (NeurIPS 2024): if synthetic data is *curated* by human reward signals, iterative retraining can implicitly optimize preferences — but this requires real human feedback in the loop.
- Multi-modal collapse (Hu & Rostami 2025): model collapse in multi-modal systems shows different characteristics than unimodal — sometimes improved vision-language alignment but increased variance.
- Mitigations: diverse models, frozen relabeling, real data mixing, increased decoding budget. None are silver bullets.

**Practical status as of 2026:** Synthetic data works well for **math and code** (domains with verifiable ground truth), which is why reinforcement learning with verified rewards has taken off. For general knowledge and reasoning, synthetic data risks quality collapse and still requires real data anchoring. The frontier labs are using synthetic data extensively in post-training (RLHF, RLVR) but the pretraining corpus still relies primarily on human-generated text.

**Source:** Semantic Scholar papers (Alemohammad 2024; Ferbach 2024; Hu 2025); Epoch AI data exhaustion paper.

### Reinforcement Learning / Verified-Reward Data

This is emerging as a *new* bottleneck:
- The shift to o1/o3-style inference-time compute and chain-of-thought reasoning relies on reinforcement learning from environments with **verifiable correctness signals** (math proofs, code execution, game outcomes).
- DeepSeek-R1 demonstrated this approach works cheaply and powerfully for math/code reasoning.
- The bottleneck: domains with reliable automated verification are limited. Math, code, formal logic — yes. General factual accuracy, creative tasks, strategic reasoning — much harder to verify automatically.
- "RL environments / verified-reward data" is therefore the next frontier constraint once pretraining data runs thin.

**Source:** DeepSeek-R1 technical coverage; Brenndoerfer "Scaling Frontiers" (March 15, 2026).

---

## 3. Capital Constraint

### Training Run Cost Trajectory

| Model | Estimated Training Cost | Year |
|---|---|---|
| GPT-3 | ~$5–12M | 2020 |
| GPT-4 | ~$78–100M | 2023 |
| Gemini Ultra | ~$191M | 2023 |
| DeepSeek-R1 | ~$6M (MoE, efficient) | Jan 2025 |
| GPT-5.x / next-gen | >$500M (rumored per training run) | 2025 |
| Dario Amodei prediction | "$100B training runs" by ~2026 | 2024 |

Note: DeepSeek-R1's $6M cost is for a *specific architecture* (MoE, 671B params but only 37B active per token, H800 GPUs). Western labs' rumored $500M+ training runs may reflect different architectures, longer training, and more post-training work. These are not directly comparable.

**Source:** Multiple (PadHai/onefourthlabs "Real Cost of Training AI Models," March 2026; ByteIota DeepSeek coverage; Business Insider "Orion" report Nov 2024).

### Total Committed Capital (as of early 2026)

| Lab / Entity | Committed Capital | Notes |
|---|---|---|
| OpenAI Stargate | $500B over 4 years | SoftBank/Oracle/OpenAI/MGX JV |
| OpenAI infrastructure (7-vendor) | $1.15T total 2025–2035 | Broadcom $350B, Oracle $300B, Microsoft $250B, Nvidia $100B, AMD $90B, AWS $38B, CoreWeave $22B |
| Meta 2025 capex | $60–65B | Annual capex; 2026 guidance: $115–135B |
| Amazon / Project Rainier + AWS AI | $8B in Anthropic + $11B Project Rainier | Plus broader AWS AI infrastructure |
| xAI Colossus | $3–5B hardware | 200,000 GPU cluster |
| Google DeepMind | Tens of billions (estimated) | Including $3B Anthropic investment |
| "Four hyperscalers combined" | $650B in a single year | As cited by The Synthesis (March 2026) |

**Source:** Tomasz Tunguz "OpenAI's $1 Trillion Infrastructure Spend" (Nov 2025); Introl.com Stargate Dec 2025; CNBC Project Rainier Oct 2025; The Synthesis "The Plateau" (March 14, 2026).

### The Diminishing-Returns-on-Capital Problem

**The most important data point on capital constraint:** Meta's "Avocado" model delay (reported The Synthesis, March 14, 2026):

- Meta's 2026 capex guidance: **$115–135 billion** — the most aggressive AI infrastructure spend in the industry.
- Meta hired 50+ senior researchers with nine-figure compensation packages; poached from OpenAI, DeepMind, Apple, Anthropic.
- Employed ~79,000 people total. Had more training compute, more user data (3 billion accounts), more aggressive spending than any competitor.
- Result: Avocado model still fell short of Gemini 3, OpenAI's latest, and Anthropic's frontier — by a gap large enough that Meta considered licensing Google's Gemini to power its own products.
- Meta reorganized its AI division **four times in six months**. Yann LeCun departed November 2025. Joelle Pineau (FAIR) departed mid-2025. Multiple nine-figure hires left within months.

**Interpretation:** This is the clearest evidence that capital alone does not purchase frontier model quality. "One hundred and thirty-five billion dollars buys a great deal of compute. It evidently does not buy the transformation from compute to model quality. That transformation is not linear." (The Synthesis)

**Source:** The Synthesis "The Plateau" (March 14, 2026) — not a peer-reviewed source, but detailed and plausible, citing specific organizational events and timelines.

---

## 4. Talent Constraint

### Compensation at the Frontier

- Top OpenAI researchers regularly earn **>$10M/year** (Reuters, May 2025).
- Google DeepMind has offered **$20M/year** packages; reduced vesting to 3 years.
- Mark Zuckerberg personally emailed a researcher an offer of **at least $10M/year** (The Register, June 2025).
- OpenAI countered SSI-luring researchers with $2M retention bonuses + $20M equity increases.
- Sam Altman (June 2025): Meta offered some researchers "up to $100 million" total packages.

### Size of the Frontier-Capable Pool

The consensus among industry insiders: the number of truly frontier-capable researchers is **"a few dozen to around a thousand"** people globally (Reuters, citing 8 sources). This is not hype — it reflects the reality that training frontier models requires rare combinations of:
- Systems-level understanding of how large models actually train
- Taste in architectural bets (which ideas to pursue)
- Experience managing distributed training at 10^4+ GPU scale
- Ability to debug subtle emergent failures

**Retention data (SignalFire 2024–2025 report):**
- Anthropic: 80% retention rate
- Google DeepMind: 78%
- OpenAI: 67%
- Meta: 64% (despite $10M+ packages)

**Lab poaching/flight patterns:**
- Google lost 5.4% of its AI team in 2024 to other labs.
- Meta lost 4.3% of its AI team.
- Mira Murati's Thinking Machines Lab raised $2B at $10B valuation with ~60 people and no product.
- Yann LeCun raised $1B at $3.5B pre-money valuation after departing Meta — without a launched product.

**Assessment:** Elite talent is genuinely scarce, and compensation has reached absurd levels. But this is not a *hard ceiling* — it's an expensive friction. It does constrain how quickly new labs can form and how quickly existing labs can staff their most ambitious projects. More importantly, the Meta evidence suggests that throwing money at talent (alone, without research culture) doesn't work.

**Source:** Reuters "OpenAI, Google and xAI battle for superstar AI talent" (May 21, 2025); The Register "Meta offering $10m a year-plus" (June 13, 2025); Odgers "AI Researcher Wars" (Aug 12, 2025); SmythOS talent war article (June 2025); The Synthesis "The Plateau."

---

## 5. Algorithmic / Scaling-Law Status

### Are Scaling Laws Still Holding?

**Evidence for continued holding:**
- Grok-3 (4–5e26 FLOP, Feb 2025) delivered substantial capability gains over GPT-4 class models.
- The Chinchilla robustness analysis (Schaeffer et al. 2025) found that "Chinchilla's key results withstand sizable perturbations" and that practitioners can still rely on its prescriptions.
- Epoch AI projects continued compute scaling at 4–5x/year.
- Training compute–inference pricing elasticity is β=0.432 (Tiered Super-Moore paper, March 2026) — scaling compute does still translate to improved models.
- Multiple labs are still betting billions on pretraining scaling (AI Labs Still Betting Big on Scaling, Surf AI, March 28, 2026).

**Evidence for hitting a wall or plateau:**
- **November 2024 "Orion" reports:** The Information reported OpenAI's next model (Orion/GPT-5) showed "only moderate improvement over GPT-4" and "smaller leap than between GPT-3 and GPT-4, especially in coding." This triggered the public scaling debate.
- **Ilya Sutskever (November 2024):** Told Reuters that "results from scaling up pretraining had plateaued. Scaling the right thing matters more now than ever." He later stated "The Age of Scaling Is Over" (widely reported late 2024).
- **Multiple GPT-5.x releases:** A Medium piece (March 6, 2026) noted "Gemini 3.1 Pro, Claude Opus 4.6, GPT-5.3-Codex, and GPT-5.4 — four frontier models in a single month. GPT-5.x has had four releases in four months. The cadence itself is the signal. Pretraining scaling hit a wall, models are commoditizing."
- **Meta Avocado failure:** $135B/year didn't produce a model competitive with Anthropic or OpenAI.
- **Benchmark convergence:** Multiple competing frontier models from different labs showing similar performance on standard benchmarks — suggesting the field is approaching a shared capability ceiling from current pretraining approaches.

### The Inference-Time Compute Pivot: Forced or Strategic?

OpenAI's o1 (September 2024) shifted the paradigm: instead of scaling pretraining, let the model "think longer" at inference time via chain-of-thought reasoning and reinforcement learning. This was framed as a new scaling axis.

**Was this a forced paradigm shift because pretraining hit a wall?**

The evidence suggests: **partially yes, partially strategic expansion.** Key signals:
1. o1 was released around the same time the Orion plateau reports emerged.
2. DeepSeek-R1 (January 2025) independently arrived at the same conclusion using pure RL with only 2,048 H800 GPUs at $6M total cost — matching o1 on math benchmarks. This suggests the inference-time compute approach was discovered as a genuine alternative, not just a workaround.
3. The Brenndoerfer article (March 2026) calls this a "shift from pretraining scale to inference-time scale" and notes it is now the dominant paradigm.
4. The DeepSeek-R1 effect "forced Silicon Valley giants to abandon their 'brute-force' scaling strategies in favor of a new, efficiency-first paradigm" (TokenRing, Feb 2026).

**However:** inference-time compute scaling has its own limits. DeepSeek's paper itself notes: "this approach faces fundamental limitations. Pursuing higher final answer accuracy doesn't address a key issue: correct answers don't guarantee correct reasoning. Moreover, many mathematical tasks like theorem proving require rigorous step-by-step derivation rather than numerical answers." (DeepSeekMath-V2, 2025)

### Pretraining Scaling Laws: The Current Assessment

The Chinchilla prescription (Hoffmann et al. 2022, 2,978 citations) — scaling model size and data tokens proportionally — has held as a guide. But:
- Frontier labs are now *intentionally overtrained* (more data tokens than Chinchilla-optimal) for inference efficiency — this eats data faster.
- Schaeffer et al. 2025 confirm Chinchilla prescriptions are robust, but this doesn't mean they continue forever — just that the math holds within the current regime.
- The 4–5x/year compute scaling trend has held, but the *returns* (capability per FLOP) appear to be softening as benchmarks converge.

**Key unresolved question:** Whether the "next training paradigm" — combining massive pretraining with post-training RL from verified rewards, inference-time compute, and new architectures (MoE) — represents a genuine new scaling axis or just a one-time efficiency gain. The evidence is genuinely ambiguous.

---

## Landscape Assessment

### State of Knowledge

Strong, quantitative data exists for:
- FLOP trajectory (Epoch AI) — ~4–5x/year, currently at 1–5e26 for frontier
- HBM supply bottleneck (EnkiAI, industry sources) — sold out through 2026
- Power demand trajectory (Epoch AI/EPRI) — 2.2x/year growth, 100 MW now, 4–16 GW by 2030
- Infrastructure capital commitments (multiple sources) — very large numbers, well documented
- Talent compensation and scarcity (Reuters, The Register) — $10–100M packages confirmed
- Data stock estimate (Epoch AI/Villalobos) — ~300T tokens, partially exhausted already
- Model collapse risk (academic literature) — real but mitigation strategies exist

More uncertain:
- Whether current benchmark convergence represents a fundamental wall vs. benchmarks lagging capability
- How much synthetic data + RL can substitute for exhausted human text at scale
- Whether power/grid constraints will actually bind before 2028–2030 or be built around
- Whether the inference-time compute pivot is a new sustained scaling axis or a one-time shift

### Agreements Between Sources

- Training compute has grown at 4–5x/year for years and is still growing
- Data (human-generated public text) is finite and approaching exhaustion for overtraining regimes
- HBM is a real near-term supply bottleneck (2025–2027)
- Power/grid will become a serious constraint by 2028–2030 if trends continue
- Talent is genuinely scarce at the true frontier; compensation has reached extreme levels
- The DeepSeek-R1 demonstrated dramatically better training efficiency using MoE + RL
- A paradigm shift toward inference-time compute scaling is underway

### Conflicts Between Sources

- **Is pretraining scaling dead?** Ilya Sutskever ("the age of scaling is over") vs. Sam Altman ("there is no wall") vs. Kevin Scott of Microsoft ("we're not at diminishing marginal returns"). Evidence tilts toward "softening returns, not zero returns."
- **How close is data exhaustion?** Epoch AI says 2026–2032 for the full stock; actual timing depends heavily on how much overtraining continues. With current aggressive overtraining, it's plausibly already happening.
- **Does synthetic data solve the data problem?** Labs say yes (using it extensively in post-training); academics say it works only in verifiable domains and risks model collapse elsewhere. Both are probably right.

### Which Constraint Binds First

Ordering the constraints by nearness and severity:

1. **Data (high-quality human text):** Already binding in the overtraining regime. The Epoch AI estimate says exhaustion happens 2025–2027 under aggressive overtraining. This is *the most immediate* constraint.

2. **HBM supply:** Binding now (sold out through 2026–2027). Creates lags of 1–2 years in cluster expansion speed. Will be relieved by ~2027–2028 as new capacity comes online. Not a permanent ceiling.

3. **Power / grid:** Not yet binding but approaching. Current clusters at 100 MW–2.2 GW. The trajectory toward 4–16 GW per training run by 2030 outpaces current grid expansion plans. Becomes a hard constraint sometime between 2028 and 2032.

4. **Capital returns:** Not a hard ceiling but a force for change. The Meta Avocado evidence is the clearest signal that capital-to-capability is not linear. At $135B/year, you can't buy your way to the frontier if your research culture is broken.

5. **Talent:** Real scarcity, extreme cost, but not a hard ceiling. The 10,000x researchers exist and can be found and hired — at a price.

6. **Algorithmic:** Not exhausted. New architectures (MoE), new training paradigms (RL from verified rewards), inference-time compute scaling represent genuinely new territory. The pretraining scaling law for pure transformer-on-text is probably softening; but the broader learning system has new axes to explore.

### Surprises and Contradictions

1. **The DeepSeek-R1 shock:** A $6M training run matching a $100M+ training run is genuinely shocking. It proves that the cost frontier and the capability frontier can diverge dramatically when architectural innovation outpaces brute scaling. This is the most important surprise of 2025 and has restructured the entire framing.

2. **Meta's failure despite maximal resources:** $135B/year + elite talent + 3B users of training data couldn't beat Anthropic or OpenAI. This is a strong signal that research culture and architectural judgment matter more than raw capital, and that the compute-to-capability transformation "is not linear."

3. **Inference-time compute as escape valve:** The discovery that you can trade compute at *inference* rather than *training* time effectively creates a new dimension of the scaling problem. This wasn't fully understood two years ago. It changes what "scaling" means.

4. **HBM as the unexpected near-term wall:** Most scaling discussions focus on FLOPs or data. The HBM supply chain being completely sold out through 2026–2027 is a concrete physical constraint that received less attention than it deserved before 2025.

5. **Jevons Paradox in action:** DeepSeek's efficiency gains didn't reduce AI compute demand — they *increased* it by enabling new use cases at lower cost, driving the Stargate $500B buildout. Efficiency improvements in AI may actually accelerate the power/grid constraint rather than relieving it.

### Gaps in This Survey

- No primary access to the full Epoch AI/EPRI power demand paper (behind paywall on EPRI site; only the substack summary was available).
- No access to the full IEA Electricity 2026 quantitative data (landing page only; full report paywalled).
- No SemiAnalysis or Dylan Patel primary pieces available directly (would require subscription); coverage was via secondary sources.
- No primary lab technical reports on exact training configurations for GPT-5.x, Claude Opus 4.6, or Gemini 3 (proprietary).
- The "GPT-5 wall" / Orion story is based on reporting by The Information (paywalled) and secondary coverage — not primary documentation.
- Anthropic's revenue and scaling specifics from "The Plateau" article (The Synthesis) is a newsletter, not a primary source — though the events cited are corroborated elsewhere.
- The exact nature of the inference-time compute scaling laws (how performance scales with inference FLOP budget) is still an active research area; no clean equivalent to Chinchilla exists yet for this regime.

---

## Key Sources

### Epoch AI — AI Models Database
- **Link:** https://epoch.ai/data/ai-models (updated March 31, 2026)
- **Key content:** Comprehensive database of 3,200+ models with training compute estimates. Confirms 4–5x/year FLOP growth trajectory. First model >1e26 FLOP: Grok-3 (Feb 2025).
- **Assessment:** Primary quantitative source; highly credible. Non-profit research organization, peer-reviewed methodology.

### Epoch AI — Will We Run Out of Data?
- **Link:** https://epoch.ai/blog/will-we-run-out-of-data-limits-of-llm-scaling-based-on-human-generated-data (2024)
- **Key content:** ~300T token estimate for human-generated public text stock. 80% CI exhaustion between 2026–2032. Under overtraining (10x, like Llama-3-70B), exhaustion by 2027.
- **Assessment:** Most rigorous available estimate. Authors include Pablo Villalobos, Jaime Sevilla, Tamay Besiroglu. Paper at arxiv 2211.04325.

### Epoch AI — Projecting AI Training Power Demand
- **Link:** https://epochai.substack.com/p/power-demands-of-frontier-ai-training (Aug 11, 2025)
- **Key content:** Power demand growing 2.2x/year; frontier runs now >100 MW; could reach 4–16 GW per run by 2030; total AI capacity could reach >100 GW worldwide, >50 GW US, approaching 5% of US generation.
- **Assessment:** Joint with EPRI. High credibility; grounded in documented data.

### Epoch AI — Model Counts at Compute Thresholds
- **Link:** https://epoch.ai/blog/model-counts-compute-thresholds
- **Key content:** Projects ~30 notable models above 1e26 FLOP by 2027, ~200 by 2030. Three scenarios: $30B clusters (conservative), $200B (median), $1T (aggressive) by 2030.
- **Assessment:** Credible projection; investment assumptions are the key uncertainty.

### Hoffmann et al. — Training Compute-Optimal Large Language Models (Chinchilla)
- **Link:** Advances in Neural Information Processing Systems 35, 2022 (2,978 citations)
- **Key content:** For compute-optimal training, model size and token count should scale equally (~20 tokens per parameter). Current large models are significantly undertrained.
- **Assessment:** Foundational and highly cited. Schaeffer et al. 2025 confirms robustness.

### Schaeffer et al. — Evaluating Robustness of Chinchilla
- **Link:** arXiv 2025 (3 citations so far, early)
- **Key content:** Chinchilla's key results withstand sizable perturbations in model parameter counting. Practitioners can still rely on its prescriptions.
- **Assessment:** Useful confirmation; low citation count reflects recency, not quality.

### EnkiAI — HBM Supply Crisis 2026
- **Link:** https://enkiai.com/data-center/hbm-supply-crisis-2026-the-bottleneck-redefining-ai/ (Feb 28, 2026)
- **Key content:** SK Hynix and Micron 2026 HBM production sold out; B200 needs 192 GB HBM3E (140% more than H100); Samsung failing qualification; $30B+ in new capacity announced but not arriving before 2027.
- **Assessment:** Industry analysis site; well-sourced from earnings reports and industry announcements. Not peer-reviewed, but specific and corroborated.

### Reuters — Superstar AI Talent
- **Link:** https://www.reuters.com/business/openai-google-xai-battle-superstar-ai-talent-shelling-out-millions-2025-05-21/
- **Key content:** Top OpenAI researchers earn >$10M/year; Google DeepMind has offered $20M/year packages; effective pool of frontier-capable researchers is "a few dozen to around a thousand."
- **Assessment:** Credible journalism. Reuters. Multiple named and unnamed sources.

### The Register — Meta offering $10M+
- **Link:** https://www.theregister.com/2025/06/13/meta_offers_10m_ai_researcher/ (June 13, 2025)
- **Key content:** Mark Zuckerberg personally emailed offer of at least $10M/year to a researcher; Meta's AI attrition 4.3% vs. Anthropic 20% retention.
- **Assessment:** Credible tech journalism; specific details (8-figure offer) from a named researcher source.

### The Synthesis — "The Plateau"
- **Link:** https://thesynthesis.ai/journal/the-plateau.html (March 14, 2026)
- **Key content:** Meta Avocado delayed; Meta's $135B/year capex couldn't beat frontier competitors; Meta discussed licensing Google's Gemini; four AI division reorganizations in six months; Yann LeCun departure; compute-to-capability relationship is not linear.
- **Assessment:** Newsletter/analytical publication, not journalism or peer-reviewed. Well-written with specific details. The organizational facts (LeCun departure, reorganizations) are corroborated; the Avocado model details are less widely confirmed. Use with caution — cites no primary sources. Treat as informed analysis, not fact.

### Stargate / Project Rainier Infrastructure Sources
- **Links:** IntuitionLabs (rev. Feb 21, 2026); DataCenterFrontier; Introl.com (Dec 2025); CNBC (Oct 29, 2025)
- **Key content:** Stargate = $500B, 10 GW target, 400k GB200 GPUs at Abilene; Project Rainier = $11B, 2.2 GW, 500k Trainium2 chips, operational Oct 2025.
- **Assessment:** Mix of corporate press releases, CNBC reporting (credible), and infrastructure analysis sites (generally reliable on factual specifics).

### DeepSeek-R1 Coverage
- **Links:** Multiple (ByteIota, TokenRing/Chronicle-Journal, TLDL.io)
- **Key content:** DeepSeek-R1 trained for ~$6M using 2,048 H800 GPUs; 671B params (37B active); matched o1 on AIME 2024 (79.8% vs. 79.2%); API pricing $0.55/M vs. o1's $15/M.
- **Assessment:** The training cost figure ($6M) and benchmark results are widely reported and corroborated. The sources above are secondary commentary, not technical documentation. DeepSeek's own paper is the primary source.

### Business Insider — Orion / Scaling Wall Debate
- **Link:** https://businessinsider.com/openai-orion-model-scaling-law-silicon-valley-chatgpt-2024-11 (Nov 11, 2024)
- **Key content:** Orion showed "only moderate improvement over GPT-4," smaller leap than GPT-3→GPT-4; Ilya Sutskever told Reuters pretraining scaling results "have plateaued"; Sam Altman: "there is no wall."
- **Assessment:** Business Insider citing The Information's original reporting; paywalled primary source. Credible trade journalism.

### Brenndoerfer — Scaling Frontiers
- **Link:** https://mbrenndoerfer.com/writing/scaling-frontiers-limits-power-laws-data-wall-architecture (March 15, 2026)
- **Key content:** Comprehensive 40-minute read on physical, statistical, and economic limits of LLM scaling; data wall; MoE; inference-time compute; written for a technical handbook.
- **Assessment:** Individual technical writer / educator. Useful synthesis but not original research; sources own arguments well. Not peer-reviewed.
