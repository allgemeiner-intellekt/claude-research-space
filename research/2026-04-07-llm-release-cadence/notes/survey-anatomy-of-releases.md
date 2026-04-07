# Survey: What Is Actually Being Released — The Anatomy of Frontier LLM Releases 2023–2026

## What I Searched

- Exa semantic search: "frontier LLM releases timeline 2023–2025", "Epoch AI notable models database", "OpenAI GPT-4 o1 o3 GPT-5 release dates", "Anthropic Claude release timeline", "Google Gemini timeline", "Meta Llama releases", "DeepSeek V2 V3 R1", "benchmark saturation diminishing returns 2024 2025", "METR time horizon task completion", "Nathan Lambert Interconnects post-training", "GPT-5 underwhelming reception"
- Sources fetched: Wikipedia Claude/Gemini/Llama pages, ScriptByAI Claude/Gemini timelines, Stanford HAI 2025 AI Index, Epoch AI data insights (capabilities acceleration, reasoning model scaling), OpenAI o1 release blog, Artificial Analysis GPT-5 benchmarks, METR long-task measurement paper, Nathan Lambert Interconnects 2025 year-in-review, LayerLens Q1 2026 Frontier Model Report, TimesOfAI 2025 model roundup, Meta Llama 4 blog, DeepSeek-V3 arXiv abstract
- Authoritative: Epoch AI (quantitative AI trends research), METR (AI safety evaluation org), Stanford HAI (academic annual index), OpenAI primary documentation, Meta primary blog, arXiv technical reports
- Secondary/journalism: TimesOfAI, ScriptByAI, LayerLens — treated as reference summaries, not primary

---

## Timeline Table: Major Frontier Model Releases, 2023–April 2026

Key to "Type" column:
- **Scale-up**: new base model at meaningfully larger compute
- **Reasoning**: chain-of-thought RL, inference-time compute paradigm
- **Post-training**: improved RLHF, Constitutional AI, DPO, safety; no new base
- **Multimodal**: primary headline is adding/improving vision/audio
- **Efficiency**: same or better performance at substantially lower cost/latency
- **Agentic**: tool-use, long-horizon, computer-use framing as primary
- **Point release**: minor revision, same model family

| Date | Model | Lab | Type | Key Facts |
|------|-------|-----|------|-----------|
| Mar 2023 | **GPT-4** | OpenAI | Scale-up + Multimodal | First large-scale multimodal-capable model publicly released. Introduced as MoE (per later leaks) with ~1.8T params; OpenAI published only benchmark comparisons, not parameters. MMLU ~86%, bar exam ~90th percentile. Technical report refused to disclose training compute [arXiv 2303.08774]. |
| Mar 2023 | **Claude 1** | Anthropic | Post-training | Constitutional AI trained model. Small context (9K tokens initially, expanded to 100K in May 2023). No parameters disclosed. |
| Jul 2023 | **Claude 2** | Anthropic | Scale-up + Post-training | Improved capability, 200K context, reduced hallucination. No parameter disclosure. |
| Aug–Nov 2023 | **Claude 2.1** | Anthropic | Post-training / Point release | Enterprise features: 200K token context, tool use (beta), reduced hallucination rates. Not a new base model. |
| Dec 2023 | **Gemini 1.0** (Ultra, Pro, Nano) | Google DeepMind | Scale-up + Multimodal | Announced as natively multimodal from ground-up training (text, image, audio, video). Ultra outperformed GPT-4 on several benchmarks per Google benchmarking. Actual Ultra access delayed until Feb 2024 for Gemini Advanced. |
| Feb 2024 | **Gemini 1.5 Pro** | Google DeepMind | Architecture / Efficiency | MoE architecture. Breakthrough: 1M token context window (later 2M). "Needle in a haystack" recall across entire context. Primarily an architectural-efficiency innovation rather than headline capability jump on standard benchmarks. |
| Mar 2024 | **Claude 3** (Haiku / Sonnet / Opus) | Anthropic | Scale-up + Multimodal | First three-tier product family. Opus matched or exceeded GPT-4 on MMLU/GPQA. Sonnet balanced speed+capability. Haiku for efficiency. Clear tiering strategy introduced. |
| Apr 2024 | **Llama 3** (8B, 70B) | Meta | Scale-up | Open-weight dense transformer. Trained on ~15T tokens. Strongest open model at the time at 70B. No multimodal. |
| May 2024 | **DeepSeek-V2** | DeepSeek | Scale-up + Efficiency | 236B total parameters, 21B active (MoE). Multi-head Latent Attention (MLA) introduced. Claimed 5x cheaper inference than V1. First major shot across the bow from Chinese open-source. [arXiv 2405.04434] |
| May 2024 | **Gemini 1.5 Flash** | Google DeepMind | Efficiency / Distillation | Distilled from 1.5 Pro. Sub-300ms latency. High-volume use case focus. |
| Jun 2024 | **Claude 3.5 Sonnet** | Anthropic | Post-training + Scale-up | "First release in the Claude 3.5 family." Outperformed Claude 3 Opus on most benchmarks at Sonnet tier speed. Major capability jump within the 3.x family; redefined middle tier. |
| Jul 2024 | **Llama 3.1** (8B, 70B, **405B**) | Meta | Scale-up | 405B is largest open-weight model at the time. 128K context. Multilingual. Positioned explicitly as GPT-4-tier open challenge. |
| Sep 2024 | **o1-preview / o1** | OpenAI | **Reasoning (paradigm shift)** | First public chain-of-thought RL model. Used large-scale RL to teach "extended thinking" chain-of-thought. AIME 2024: 74% (vs GPT-4o's 12%). GPQA Diamond: 77% (first model to exceed human PhD). "Test-time compute" axis introduced. Release: Sep 12, 2024 [openai.com/index/learning-to-reason-with-llms]. Nearly 6x more expensive and 30x slower than GPT-4o [Stanford HAI 2025]. |
| Sep 2024 | **Llama 3.2** (1B, 3B, 11B, 90B) | Meta | Multimodal + Efficiency | Added vision models (11B, 90B). Smaller edge-deployment variants (1B, 3B). First multimodal Llama. |
| Oct 2024 | **Claude 3.5 Sonnet (updated)** | Anthropic | Post-training / Point release | "Across-the-board improvements" per Anthropic. Particularly coding. Computer use (beta) introduced. |
| Oct 2024 | **Claude 3.5 Haiku** | Anthropic | Efficiency | Fast/cheap tier upgraded. |
| Nov 2024 | **o1 (full)** | OpenAI | Reasoning | Full release with vision support. |
| Dec 2024 | **Gemini 2.0 Flash** | Google DeepMind | Architecture + Agentic | "Twice as fast as 1.5 Pro with stronger performance." Native tool use, multimodal outputs. Real-time streaming (Live API). Agent framing dominant. |
| Dec 2024 | **Gemini 2.0 Flash Thinking** | Google DeepMind | Reasoning | Experimental thinking mode — reasoning traces shown. Google entering the o1 space. |
| Dec 2024 | **DeepSeek-V3** | DeepSeek | Scale-up + Efficiency | 671B total parameters, 37B active per token. MLA + DeepSeekMoE. Trained on 14.8T tokens. Total training cost: ~$6M (2.788M H800 GPU-hours). Matched or exceeded GPT-4o and Claude 3.5 Sonnet on most benchmarks. Open-sourced. Genuine shock to the industry. [arXiv 2412.19437] |
| Jan 2025 | **DeepSeek-R1** | DeepSeek | Reasoning | First Chinese-origin reasoning model. Matched o1 on math/coding benchmarks. RL reasoning stage trained on ~6×10²³ FLOP (~$1M). Demonstrated that frontier reasoning didn't require Western-scale compute. Full model weights released. |
| Feb 2025 | **Claude 3.7 Sonnet** | Anthropic | Reasoning | "First hybrid reasoning model on the market." Extended thinking mode. Outperformed o1 on SWE-bench (>60% vs o1's ~50% at the time). Agent framing prominent. METR time horizon: ~1 hour (50% success). |
| Feb 2025 | **GPT-4.5 ("Orion")** | OpenAI | Scale-up (weak) | Explicitly described by OpenAI as "not a frontier model." Largest model ever trained (undisclosed parameters, estimated > GPT-4). Poor cost-performance ratio; described as "a lemon" by Ars Technica. Mixed reviews from Nathan Lambert ("Not a frontier model?"). Deprecated within months. |
| Feb 2025 | **Gemini 2.0 (enhanced)** | Google | Post-training + Agent | Updates adding more agent capabilities, improved tool use. |
| Mar 2025 | **Gemini 2.5 Pro (experimental)** | Google DeepMind | Reasoning + Scale-up | Introduced internal "thinking" (CoT reasoning). State-of-the-art on reasoning benchmarks. GPQA Diamond: approached 90%+. Became dominant coding assistant per many developers. |
| Apr 2025 | **GPT-4.1** | OpenAI | Post-training + Agentic | API-focused model. Better instruction following, tool use, long-context. Explicitly positioned as developer/API product, not ChatGPT flagship. Separated "API product" from "consumer product" — a significant framing shift. |
| Apr 2025 | **o3 / o4-mini** | OpenAI | Reasoning (10x scale-up) | o3 is 10x more reasoning compute than o1 per OpenAI's own graph. Massive improvement: AIME 2024 ~96%, SWE-bench ~70%+. ARC-AGI: ~88% (human is ~85%). o4-mini: efficient reasoning variant. Released Apr 16, 2025. |
| Apr 2025 | **Llama 4** (Scout, Maverick) | Meta | Scale-up + Multimodal + MoE | First natively multimodal MoE Llama. Scout: 17B active / 109B total, 16 experts, 10M context. Maverick: 17B active / 400B total, 128 experts. Behemoth (2T total params, not yet released at announcement) used as teacher for distillation. Trained on 30T+ tokens. [meta.com blog Apr 5, 2025] |
| Apr 2025 | **Gemini 2.5 Flash** | Google | Efficiency + Reasoning | "Thinking" model with adjustable reasoning budget. Lower cost than 2.5 Pro. |
| May 2025 | **Claude 4** (Sonnet 4, Opus 4) | Anthropic | Scale-up + Agentic | New model generation. Extended thinking + tool use simultaneously. Coding focus ("Anthropic's bet on code" — Nathan Lambert). Memory capability introduced. |
| Jun 2025 | **Gemini 2.5 Pro (updates)** | Google | Post-training | Continued iterative improvements to 2.5 Pro. |
| Jul 2025 | **Grok 4 / 4.1** | xAI | Reasoning + Scale-up | Described as leading programming benchmarks (e.g., LiveCodeBench: Grok 4 Fast best in class per LayerLens Q1 2026 data). "Frontier performance with Elon favoritism" (Nathan Lambert). |
| Aug 2025 | **GPT-5** | OpenAI | Scale-up + Reasoning | Released Aug 2025. Single endpoint, four reasoning effort levels. At "High" effort: new benchmark leader (Artificial Analysis Intelligence Index score: 68, vs o3's ~67). At "Minimal" effort: near GPT-4.1 level. Long-context reasoning (AA-LCR benchmark): #1 and #2. Increment over o3 smaller than the GPT-3→4 or GPT-4o→o1 jumps [Artificial Analysis, Aug 7, 2025]. Epoch AI: "Both GPT-4 and GPT-5 greatly exceeded their direct predecessors — disappointment better explained by more frequent cadence than slower progress." |
| Sep 2025 | **Claude Sonnet 4.5** | Anthropic | Agentic + Post-training | "Best in world for agents, coding, computer use." Incremental above Claude 4. |
| Oct 2025 | **Claude Haiku 4.5** | Anthropic | Efficiency | Sonnet 4 level coding at 1/3 cost and 2x speed. |
| Nov 2025 | **Claude Opus 4.5** | Anthropic | Post-training + Agent | Best Anthropic model: coding/agents/computer use. |
| Nov 2025 | **Gemini 3 Pro / Flash** | Google | Scale-up + Reasoning + Agentic | Gemini 3 Pro: GPQA Diamond 91.9% (per TimesOfAI). Autonomous multi-step agent planning. Gemini 3 Flash: best coding performance exceeding 3 Pro on SWE-bench (78%); 3x faster than 2.5. |
| Dec 2025 | **DeepSeek-R1 0528** | DeepSeek | Reasoning | Updated R1 variant; continued iterative improvement of RL reasoning stack. |
| Jan 2026 | **Moonshot AI Kimi K2 Thinking** | Moonshot AI | Reasoning | Large open-weight reasoning model; challenged o1-tier performance. |
| Feb 2026 | **Claude Opus 4.6 / Sonnet 4.6** | Anthropic | Agentic + Post-training | 1M token context. Better sustained agentic tasks, codebase navigation. "Plans more carefully, sustains longer." [Feb 5 / Feb 17, 2026] |
| Feb 2026 | **GPT-5.4** (note: separate from GPT-5) | OpenAI | Agentic + Reasoning | "Computer use and mid-stream reasoning." [LayerLens Q1 2026 report] |
| Feb 2026 | **Alibaba Qwen 3.5** | Alibaba | Scale-up + Efficiency | "First native multimodal open-weight model to challenge frontier proprietary AI." Phone-sized to frontier-class variants. LiveCodeBench v6: 83.6%. |
| Feb 2026 | **ByteDance Seed 2.0** | ByteDance | Scale-up + Efficiency | Three sizes. Priced for high-volume. |
| Feb 2026 | **Zhipu GLM-5** | Zhipu AI | Scale-up | Topped open-weight leaderboard at release. |
| Mar 2026 | **Gemini 3.1 Flash / Flash-Lite** | Google | Efficiency | "Most cost-efficient Gemini 3 model, built for intelligence at scale." |
| Mar 2026 | **Gemini 3.1 Pro** | Google | Post-training | Smarter model for complex tasks. |

---

## Key Patterns and Shifts Found

### Pattern 1: Scale-up ceased being the *only* headline story in mid-2024

Through GPT-4 (Mar 2023), Claude 2 (Jul 2023), and Llama 3 (Apr 2024), the dominant release narrative was: we trained on more data, with more parameters, and performance improved accordingly on benchmarks. DeepSeek-V2 (May 2024) was still fundamentally scale-up but added an efficiency twist. Gemini 1.5 Pro (Feb 2024) pivoted to *context length* as the headline rather than raw performance.

The clean scale-up narrative was already fragmenting by mid-2024, but it broke decisively with:
- **o1 (Sep 2024)**: paradigm shift, reasoning compute as a new axis entirely separate from pretraining scale
- **DeepSeek-V3 (Dec 2024)**: efficiency-at-frontier, not scale-up-for-frontier

By 2025, almost no major release is purely "trained bigger." The narrative has splintered into: (a) reasoning models, (b) agentic scaffolding, (c) efficiency at existing capability levels, (d) multimodal expansion.

### Pattern 2: The reasoning paradigm emerged sharply in September 2024

o1-preview (Sep 12, 2024) is the precise inflection point. Before it, chain-of-thought was a prompting technique applied to existing models. After it, chain-of-thought became a trained capability via reinforcement learning on reasoning traces. The key numbers from the primary source [openai.com]:
- AIME 2024: GPT-4o 12% → o1 74% (single sample), 83% (consensus@64)
- GPQA Diamond: GPT-4o 50.6% → o1 77.3%
- 6x more expensive, 30x slower than GPT-4o

The Epoch AI data confirms a capability inflection point around April 2024, with the Epoch Capabilities Index growing at 8 ECI/year before and ~15 ECI/year after (R² = 0.97, AIC-preferred two-segment model). METR's time horizon analysis independently confirms a ~40% acceleration in October 2024. Both analyses point to the same transition period: Q2–Q4 2024, coinciding with the o1 paradigm shift.

### Pattern 3: Minor revisions and point releases became normalized from late 2024

Look at the Anthropic release cadence:
- Claude 3.5 Sonnet → Claude 3.5 Sonnet (updated) [Jun→Oct 2024]: same model family, incremental
- Claude 3.7 Sonnet [Feb 2025]: called "3.7" but introduces extended thinking — arguably a bigger jump than 3→3.5 despite the smaller version bump
- Claude 4 / 4.5 / 4.6 / Opus 4.1 [May–Feb 2026]: multiple sub-releases within a generation

OpenAI's model naming became genuinely confusing:
- GPT-4 → GPT-4 Turbo → GPT-4o → GPT-4.5 → GPT-4.1 → GPT-5 → GPT-5.1 → GPT-5.2 → GPT-5.4
- o1 → o1 (full) → o3 → o4-mini (skipping o2 entirely, ostensibly for trademark reasons)
- These naming schemes do not map monotonically to capability: GPT-4.5 was explicitly *less capable* than o3 in reasoning; GPT-4.1 was positioned as API-only, not consumer flagship.

The pattern of naming that looks like progression but isn't linear capability progression became dominant by 2025.

### Pattern 4: Agent/tool-use framing became the default release narrative by mid-2025

Through 2023 and most of 2024, releases were framed primarily in terms of benchmark performance: "beats human PhD-level accuracy on GPQA," "solves 74% of AIME problems," etc. This framing remained relevant but was increasingly joined by and in some cases superseded by:
- "Best model for agents" (Claude Sonnet 4.5, Sep 2025)
- "Computer use" (Claude 3.5 Sonnet updated, Oct 2024; GPT-5.4, Mar 2026)
- "Agentic autonomy" (Gemini 3 Pro, Nov 2025)
- "Claude Code" as a first-class product alongside Claude (Feb 2025)

By Q1 2026, the LayerLens report found nine releases in six weeks, with "models shipping as bundles of settings: reasoning mode on or off, different input sizes, different tool access." The release unit is no longer "model" but increasingly "model + configuration + deployment harness."

### Pattern 5: The Chinese open-source labs created a parallel release cadence

DeepSeek-V2 (May 2024), V3 (Dec 2024), and R1 (Jan 2025) were genuine capability shocks — not just for their performance but for their training economics. V3 achieved GPT-4o-tier performance for ~$6M pretraining cost (vs. estimated >$100M for comparable US models). R1 replicated o1 reasoning at a fraction of the RL compute cost.

This produced a bifurcated cadence by 2025–2026: US labs (OpenAI, Anthropic, Google) releasing every 2–4 months; Chinese labs (DeepSeek, Alibaba Qwen, ByteDance Seed, Moonshot Kimi, Zhipu GLM) releasing on comparable or faster cycles, often with open weights.

The Epoch AI US-China gap analysis found that by early 2026, Chinese models lagged the US frontier by only ~7 months — down from 17+ percentage points in late 2023.

---

## Surprises and Contradictions

**Surprise 1: GPT-4.5 was released and failed.** OpenAI released its "largest model ever trained" in February 2025 and explicitly called it "not a frontier model" at launch. It was expensive, slow, and benchmarked below o3 on reasoning. Ars Technica called it "a lemon." Nathan Lambert's top 2025 posts included "GPT-4.5: 'Not a frontier model'?" This is the clearest example of a release that was *production of a model* not matching *capability improvement* — and suggests that pretraining scale without reasoning training may have hit diminishing returns for measurable performance.

**Surprise 2: The "disappointed by GPT-5" narrative is misleading.** Epoch AI directly addressed the discourse: "When GPT-5 released, some were disappointed that the performance improvements were only marginal compared to existing models. But this is better explained by a more frequent cadence of releases in the last two years, rather than a slowdown in capabilities." GPT-5 at "High" reasoning effort did set a new benchmark record (Intelligence Index score 68 vs. o3's 67), but the increment is smaller than the GPT-3→4 or GPT-4o→o1 jumps because the latter involved *paradigm changes*, while GPT-5 is an evolution within the reasoning-model paradigm.

**Surprise 3: Benchmark saturation is real and accelerating.** The Stanford HAI 2025 AI Index documents it clearly: "MMLU, GSM8K, and HumanEval" are now saturated — leading models score near ceiling. GPQA Diamond, introduced as a hard benchmark in 2023, is already approaching 90%+ for frontier models by late 2025 (Gemini 3 Pro: 91.9%). The field has been forced into escalating benchmark creation: Humanity's Last Exam (frontier models score 8.8% as of early 2025), FrontierMath (2% success), BigCodeBench (35.5%), SWE-bench Pro. The Q1 2026 LayerLens report found: on MATH-500, top 15 models score above 96%; the top-5 gap is 0.4 points vs. run-to-run variation of 1.3 points — the ranking is statistically meaningless. The "diminishing returns" on *benchmarks* is real; whether this reflects diminishing returns on *capability* is contested.

**Surprise 4: METR's time-horizon data suggests capability is still growing exponentially.** Despite the benchmark saturation story, METR's March 2025 paper found that the task-completion time horizon (length of tasks frontier agents can complete with 50% success) has been doubling every ~7 months for 6 years. Claude 3.7 Sonnet had a ~1-hour time horizon; extrapolating suggests week-long task completion could arrive by ~2028. This metric is explicitly chosen to not saturate easily. It conflicts with the "diminishing returns" narrative — the returns on task complexity are still accelerating.

**Surprise 5: Reasoning compute scaling may already be near its own ceiling.** The Epoch AI gradient update ("How far can reasoning models scale?", May 2025) found: o3 is a 10x compute scale-up from o1, but this happened in ~4 months. If continued at 10x per few months, reasoning compute would hit the overall compute frontier within a year of that publication (by ~mid-2026). Dario Amodei wrote (Jan 2025): "we are still very early on the scaling curve: the amount being spent on the second, RL stage is small for all players." But labs have acknowledged this growth rate cannot be sustained — both OpenAI and Anthropic researchers were quoted saying RL scaling "couldn't be sustained for more than 1–2 years" by early 2025.

**Contradiction: The cadence *of releases* has accelerated even as the *substance per release* has become more heterogeneous.** In 2023, a major release meant "new base model, trained at X scale." By Q1 2026, a "release" can mean: a reasoning-effort update to an existing model (GPT-5 "Low" vs "High"), a new agentic configuration (Claude Code sub-agents), a context window expansion (Claude 4.6 with 1M context), a pricing change, or a genuinely new model. LayerLens tested 25 unique models in Q3 2025, 83 in Q4, and 44 in the first 2.5 months of Q1 2026. The *number* of things being released is increasing faster than genuine capability jumps.

---

## Assessment: Is the "Cadence" One Coherent Phenomenon?

No. What looks like a single accelerating cadence is at least **four overlapping phenomena**:

**1. The base-model generation cycle** (~18–24 months per generation): GPT-4 → GPT-5 is roughly a 2-year cycle. Claude 3 → Claude 4 is ~14 months. Gemini 1 → Gemini 2 → Gemini 3 is ~12 months each. These are genuinely new base models, representing massive capital allocation. The cycle has been roughly stable at 12–18 months per generation.

**2. The reasoning-iteration cycle** (~3–6 months): o1 → o3 was 4 months. DeepSeek-R1 → R1 0528 was ~5 months. Gemini 2.5 Pro → 2.5 Pro (I/O edition) was ~6 weeks. This cycle is new post-September 2024 and is faster than the base-model cycle.

**3. The post-training / tuning release cycle** (weeks to months): Claude 3.5 Sonnet → Claude 3.5 Sonnet (updated) was ~4 months but same base. Claude Opus 4.5 → 4.6 was ~3 months. These involve no new pretraining, just RL/DPO/distillation improvements. Increasingly common.

**4. The capability-feature release cycle** (continuous): Adding computer use, web search, 1M context, MCP integration, Claude Code sub-agents, etc. These are often announced with model version numbers but may represent deployability changes rather than capability improvements.

The confusion between these four cycles is where the "rapid release" perception comes from. What *feels* like a new frontier model every two months is often cycles 2–4 wearing the aesthetic of cycle 1.

---

## Open Gaps for Deep Dive

**Gap 1: What is actually changing inside post-training releases?** When Claude 3.5 Sonnet "updated" releases in October 2024, what specifically changed? RLHF data mix? A DPO stage? Reward model? Labs do not disclose this, and the community has no reliable way to tell whether a "point release" is a new RL stage vs. a different system prompt vs. a genuinely new model checkpoint. This makes the "anatomy of releases" question partially unanswerable from public data.

**Gap 2: How fast is RL reasoning compute actually scaling?** Epoch AI estimates o3 is at ~10^23–10^24 FLOP of RL compute (inferred). The overall frontier is >10^26 FLOP. If RL reasoning compute converges to overall training compute, what does the progress curve look like? The published data is sparse and the inference is uncertain. A deep dive on reasoning compute scaling evidence would clarify whether 2026 will see a reasoning plateau.

**Gap 3: What happened between GPT-4.5 (failed scale-up) and GPT-5 (succeeded reasoning)?** There appears to be a 6-month gap (Mar–Aug 2025) between OpenAI's last major release (o3, Apr 2025) and GPT-5 (Aug 2025). What changed architecturally? Was GPT-5 primarily a reasoning model with a larger base, or a new pretraining run? The technical report is sparse. This gap is analytically important for understanding whether pretraining scale is still contributing.

**Gap 4: Are METR time-horizon gains from base scaling, reasoning RL, or agent scaffolding?** METR's exponential trend is measured on frontier models regardless of type. But Claude 3.7 Sonnet (hybrid reasoning) likely jumped dramatically compared to Claude 3.5 Sonnet (pure RLHF). The decomposition — how much time-horizon gain comes from base model scale vs. RL reasoning vs. agentic harness improvements — is unclear from public data.

**Gap 5: Chinese lab economics and compute access.** DeepSeek-V3's $6M training cost is reported but not fully explained. What are the actual H800 availability constraints? What are Alibaba, ByteDance, and Moonshot training at? The Epoch AI US-China capability gap analysis (7-month lag in early 2026) needs more granular evidence on whether the gap is closing, stable, or widening at different capability tiers.

---

## Key Sources

1. **Epoch AI data insights — "AI capabilities progress has sped up"** (Dec 2025): https://epoch.ai/data-insights/ai-capabilities-progress-has-sped-up — Quantitative analysis showing capability acceleration breakpoint at April 2024 (8→15 ECI points/year); R²=0.97 piecewise linear fit. Authoritative.

2. **Epoch AI gradient update — "How far can reasoning models scale?"** (Josh You, May 2025): https://epoch.ai/gradient-updates/how-far-can-reasoning-models-scale — Best public analysis of reasoning compute scale. o3 = 10x reasoning compute over o1. Reasoning compute possibly 2–3 orders of magnitude below overall frontier. Authoritative/analytical.

3. **OpenAI — "Learning to reason with LLMs"** (Sep 12, 2024): https://openai.com/index/learning-to-reason-with-llms — Primary source for o1 release. Exact benchmark numbers (AIME, GPQA, Codeforces). First-party.

4. **Stanford HAI 2025 AI Index — Technical Performance chapter**: https://hai.stanford.edu/ai-index/2025-ai-index-report/technical-performance — Authoritative annual snapshot. Key finding: SWE-bench 4.4% → 71.7% in one year; GPQA 18.8pp gain; frontier convergence (top-10 Elo gap halved to 5.4%).

5. **METR — "Measuring AI Ability to Complete Long Tasks"** (Mar 2025): https://metr.org/blog/2025-03-19-measuring-ai-ability-to-complete-long-tasks/ — Exponential task-horizon growth (doubling every 7 months over 6 years). Most rigorous capability trajectory measurement. Peer-reviewed research-grade.

6. **Nathan Lambert (Interconnects) — "2025 year in review"** (Dec 2025): https://www.interconnects.ai/p/2025-interconnects-year-in-review — Practitioner perspective. 80 posts, 19 on model releases. "GPT-4.5: Not a frontier model?" listed as top article. Good for release-by-release reaction to content vs. marketing.

7. **Artificial Analysis — "GPT-5 Benchmarks and Analysis"** (Aug 7, 2025): https://artificialanalysis.ai/articles/gpt-5-benchmarks-and-analysis — Independent benchmark. Intelligence Index scores across all four reasoning effort levels. Key finding: GPT-5 High = 68 vs o3 = 67; increment "not comparable to GPT-3→4 or GPT-4o→o1." Token usage varies 23x between effort levels. Credible independent testing.

8. **LayerLens — "Q1 2026 Frontier Model Report"** (Apr 3, 2026): https://layerlens.ai/blog/q1-2026-frontier-model-report — 200+ model testing platform. Key data: 9 releases in 6 weeks; on MATH-500, top-5 gap is 0.4pp vs 1.3pp run-to-run variation (ranking statistically meaningless); 25 models tested in Q3 2025, 83 in Q4, 44 in first 2.5 months of Q1 2026. Marketing-oriented but quantitatively backed.

9. **Meta — "Llama 4 herd" blog** (Apr 5, 2025): https://ai.meta.com/blog/llama-4-multimodal-intelligence/ — Primary source. Scout: 17B active/109B total, 16 experts, 10M context. Maverick: 17B active/400B total, 128 experts. Behemoth: 288B active/~2T total. 30T+ training tokens. First-party.

10. **DeepSeek-V3 Technical Report** (Dec 27, 2024): https://arxiv.org/abs/2412.19437 — 671B total / 37B active MoE, 14.8T tokens, 2.788M H800 GPU-hours. MLA + DeepSeekMoE. Authoritative primary source.

11. **ScriptByAI — Anthropic Claude Timeline**: https://www.scriptbyai.com/anthropic-claude-timeline/ — Comprehensive Claude version dates with feature annotations. Secondary/aggregator but well-sourced. Used as reference chronology.

12. **ScriptByAI — Google AI Timeline**: https://www.scriptbyai.com/google-ai-timeline-biggest-moments/ — Comprehensive Gemini version dates with feature annotations. Same quality level.

13. **SCAND.Ai — "GPT-5 Arrives Late and Disappoints"** (tagged Mar 2025): https://scand.ai/scandal/gpt5-underwhelming — Useful aggregator of the "diminishing returns" narrative that circulated around GPT-5's early reception. Note: the publication date is ambiguous (may conflate early 2025 speculation with post-release reception). Treat as secondary narrative marker.

14. **Nathan Lambert (Interconnects) — "The state of post-training in 2025"** (Jan 8, 2025): https://www.interconnects.ai/p/the-state-of-post-training-2025 — Detailed taxonomy of post-training stages (instruction finetuning, preference finetuning, reinforcement finetuning). Estimates of cost escalation: Llama 2 post-training ~$10–20M, Llama 3.1 >$50M. Practitioner analysis, highly credible.
