# Survey: Empirical Evidence on the Marginal Risk of Open-Weight Models

## What Was Searched / Read

Primary searches and sources consulted:

- arXiv 2508.03153 (Wallace et al., OpenAI gpt-oss paper) — full abstract + OpenAI landing page
- RAND Corporation "The Operational Risks of AI in Large-Scale Biological Attacks" (RR-A2977-2, Jan 2024) — full page content
- RAND red-team article (March 2024) — full content
- NTIA "Dual-Use Foundation Models with Widely Available Model Weights" (July 2024) — press release + legal summary
- CSET Georgetown: "How to Assess the Likelihood of Malicious Use of Advanced AI Systems" (March 2025); "The Use of Open Models in Research" (October 2025)
- Anthropic Constitutional Classifiers paper/blog (Feb 2025) — full page content
- Qi et al. (2023) "Fine-tuning Aligned Language Models Compromises Safety" (ICLR) — Semantic Scholar full record
- Yang et al. (2023) "Shadow Alignment: The Ease of Subverting Safely-Aligned Language Models" — Semantic Scholar abstract
- Kapoor et al. (2024) "On the Societal Impact of Open Foundation Models" (ICML) — abstract + TLDR
- AlignmentForum post by Cheng et al. / FAR.AI, Feb 2025, "Illusory Safety: Redteaming DeepSeek R1 and the Strongest Fine-Tunable Models" — full content
- AlignmentForum post by ryan_greenblatt, June 2025, "When is it important that open-weight models aren't released?" — full content
- VCT (Virology Capabilities Test, arXiv 2504.16137) — title and partial metadata
- FORTRESS benchmark (Scale AI, 2025) — Semantic Scholar abstract
- Pannu et al. (2025) "Dual-use capabilities of concern of biological AI models" (PLoS Comp Bio) — Semantic Scholar abstract
- Sophie Kim / The Counterfactual, March 2026, "The Open-Weight Problem" — partial read

---

## Key Findings, Organized Thematically

### 1. The RAND Red-Team Study (Mouton, Lucas, Guest 2024) — Most Directly Relevant Empirical Test

**Study design:** Several dozen researchers were divided into small teams and given seven weeks to plan a large-scale biological attack. Some teams had access to one or more LLMs plus the internet; others had only the internet. Expert panelists graded plans on viability.

**Finding:** No statistically significant difference in plan viability between teams with and without LLM access. Most plans had major flaws regardless of AI access. The team that scored highest used LLMs but its final plan drew on academic literature, not AI outputs; the AI was essentially redundant.

**On "unfortunate outputs":** In cases where an LLM provided biologically relevant information (e.g., discussion of how to maximize casualties, instructions for cultivating plague bacteria), the researchers confirmed the same information was accessible via a few clicks on CDC or academic websites. The LLM provided no meaningful uplift over internet baseline.

**Caveat the authors themselves note:** The study did not measure *how close* the LLM capability frontier is to the knowledge threshold required for a viable biological attack. The rapid improvement curve means this question deserves ongoing monitoring.

**Credibility:** Published by RAND, a major policy research institution with rigorous peer review. The study involved genuine red-team participants under controlled conditions with real LLMs. This is among the strongest empirical designs in this literature — not a theoretical argument or a benchmark, but an actual uplift test.

**DOI:** https://doi.org/10.7249/RRA2977-2

---

### 2. OpenAI gpt-oss Paper: Malicious Fine-Tuning Methodology (Wallace et al., arXiv 2508.03153, Aug 2025)

**Study design:** OpenAI introduced "malicious fine-tuning" (MFT) as a methodology for estimating worst-case open-weight risk. They applied MFT to gpt-oss (their open-weight model) in two domains: biology (threat creation tasks, trained via RL with web browsing) and cybersecurity (agentic capture-the-flag training). They compared MFT gpt-oss against frontier closed-weight and open-weight models on dedicated frontier risk evaluations.

**Key finding:** MFT gpt-oss underperforms OpenAI's o3 model on both biorisk and cybersecurity evaluations — and o3 is itself *below* OpenAI's Preparedness "High" capability threshold. On open-weight comparison, "gpt-oss may marginally increase biological capabilities but does not substantially advance the frontier." These results "contributed to [OpenAI's] decision to release the model."

**Methodological contribution:** MFT is the first rigorous attempt to estimate worst-case post-release risk from open weights rather than relying on default, unmodified model behavior. It represents a serious attempt to find the ceiling of harm rather than the floor.

**Limitation / Note:** This is an OpenAI self-assessment. The company has an obvious interest in clearing its own model for release. While the methodology is reasonable, independent replication would strengthen the conclusion. Accepted at ICLR 2026, which provides some external validation.

**Link:** https://arxiv.org/abs/2508.03153

---

### 3. NTIA Report: Government Recommends Against Restrictions (July 2024)

**Summary:** The US National Telecommunications and Information Administration completed a congressionally-directed review of dual-use foundation models with widely available weights. Its conclusion: "the government should not restrict the wide availability of model weights for dual-use foundation models at this time." The NTIA employed a "marginal risk analysis" — asking not whether open-weight models can enable harm in principle, but whether they *add* harm beyond pre-existing alternatives.

**Reasoning:** The report identified that the marginal risk from open weights (versus closed-access alternatives) was insufficient to justify restrictions given the significant benefits: innovation, competition, access for small organizations and researchers, transparency, and national security interests in broad AI capability.

**What it called for:** Active monitoring, not restriction. Developing government capacity to evaluate evidence and react if risks escalate.

**Credibility:** Official US government policy document, developed after a February 2024 public comment period. Reflects the considered view of the Biden-era Commerce Department.

**Link:** https://www.ntia.gov/press-release/2024/ntia-supports-open-models-promote-ai-innovation

---

### 4. Kapoor, Bommasani et al. (2024): Marginal Risk Framework — "Current Research is Insufficient"

**Summary:** This Stanford/AI policy paper (published at ICML 2024, 91 citations as of search) is perhaps the most comprehensive academic treatment of the question. It argues for a marginal risk framework: the question is not "can open-weight models enable harm?" but "do they enable harm *beyond what pre-existing technologies already enable*?"

**Key finding:** "Across several misuse vectors (e.g., cyberattacks, bioweapons), we find that current research is insufficient to effectively characterize the marginal risk of open foundation models relative to pre-existing technologies."

**Implication:** The paper is not saying risk is low — it's saying we don't have good enough evidence to say either way. But the framework itself is damaging to simple safety arguments, because it redirects the question from absolute capability to comparative advantage: a model that can explain bioweapon synthesis but not better than Wikipedia provides no marginal uplift.

**Paper ID:** arXiv:2403.07918

---

### 5. Fine-Tuning Safety Removal: The "Illusory Safety" Problem

Several studies converge on a troubling empirical finding: safety alignment in both open-weight and API-gated models is fragile and easily removed via fine-tuning.

**Qi et al. 2023 (ICLR, 1045 citations):** GPT-3.5 Turbo's safety guardrails were removed by fine-tuning on just 10 adversarially designed examples, costing under $0.20 via OpenAI's own fine-tuning API. Even benign fine-tuning data degraded alignment to some extent. This was done on a *closed-weight* API model.

**Yang et al. 2023 (Shadow Alignment, 277 citations):** 100 malicious examples plus 1 GPU-hour was sufficient to subvert 8 open-source models from 5 organizations (LLaMa-2, Falcon, InternLM, BaiChuan2, Vicuna) into freely generating harmful content while retaining helpfulness on benign queries.

**FAR.AI / Cheng et al. 2025 (AlignmentForum, Feb 2025):** Fine-tuning removed guardrails from DeepSeek R1, GPT-4o, Claude 3 Haiku, and Gemini 1.5 Pro. Before fine-tuning: near-100% refusal. After fine-tuning: over 80% harmfulness score across all models. The attack extended to closed fine-tuning APIs, not just open-weight models, because these APIs don't monitor training data robustly enough.

**Scale AI FORTRESS Benchmark (2025):** Found dramatic variation across closed-weight frontier models. DeepSeek-R1 scored highest risk at 78.05 ARS (out of 100). But critically: Claude-3.5-Sonnet scored 14.09 ARS. Gemini 2.5 Pro scored 66.29 ARS. This suggests variance within closed-weight models is as large as any open/closed distinction.

**What this means for the open-weight risk argument:** The finding that fine-tuning removes alignment from *both* closed and open models is a double-edged finding for the open-weight debate. It shows:
(a) Open-weight models are not uniquely vulnerable — API-gated models are also vulnerable via fine-tuning APIs;
(b) But it also shows that "safety-aligned" open-weight models should not be treated as safe — the alignment is cosmetic and easily stripped.

The "marginal risk" question then becomes: does weight access add meaningful uplift over fine-tuning-API access? The evidence suggests the gap is smaller than it might appear, but not zero (weight access allows embedding-space attacks and other techniques unavailable via API).

---

### 6. CSET / Georgetown: Framework for Assessment

**Goldstein & Sastry 2025 (CSET, March 2025):** Proposed the "PPOu" framework: Plausibility (can it do Y at all?), Performance (how well?), Observed use (is it actually being used for Y?). This is a more sophisticated framework than existing red-team studies, which mostly measure Plausibility or Performance but rarely Observed use.

**Significance:** The absence of documented real-world cases of open-weight model-enabled mass-casualty events (as distinct from individual cybercrimes, deepfakes, etc.) is relevant evidence — but easy to dismiss, since the technology is relatively new and bioterrorism has long latencies. The framework emphasizes that all three stages matter.

**CSET "Use of Open Models in Research" (Oct 2025):** 250+ published papers analyzed. Found that five of eight high-level use cases for AI models exclusively require open weights (continuous pretraining, compression, model combining, hardware performance testing, model internals examination). API access is dramatically more restricted. This finding is relevant to the risk debate: the capabilities that most benefit legitimate research (interpretability, fine-tuning, mechanistic study) are the same ones that most benefit malicious actors.

---

### 7. Anthropic Constitutional Classifiers (Feb 2025): API-Gated Models Can Be Hardened

**Study design:** Anthropic developed a classifier-based defense system specifically for CBRN queries. In a formal red-team program, 183 active participants spent 3,000+ hours over two months attempting to find a "universal jailbreak" (one strategy that bypasses all 10 forbidden CBRN queries). None succeeded.

**In live demo:** After public launch, 339 jailbreakers spent 3,700 collective hours across 300,000+ chats. Four participants eventually passed all eight challenge levels. One found a true universal jailbreak on day 6.

**Baseline comparison:** Without Constitutional Classifiers, 86% of advanced jailbreak attempts against Claude 3.5 Sonnet succeeded. With them, only 4.4% succeeded.

**Implication for the open/closed debate:** This is evidence that closed-weight models can be made substantially more robust to jailbreaks than open-weight models (where weight access enables attacks that classifiers cannot prevent). But the key caveat: the Constitutional Classifiers framework applies *only* to deployed API systems, not to open-weight models anyone can run locally. The hardening advantage is fundamentally asymmetric.

**Link:** https://www.anthropic.com/research/constitutional-classifiers

---

### 8. Ryan Greenblatt (AlignmentForum, June 2025): The Bioweapons Capability Threshold Debate

This is a detailed analysis post by an Anthropic researcher (writing personally), not peer-reviewed, but substantive and unusually explicit about quantitative estimates.

**Key claim:** Anthropic's Opus 4 was assessed as possibly triggering ASL-3 safeguards due to CBRN capabilities. Several frontier models (o3, Gemini 2.5 Pro, Claude Sonnet 4) now outperform expert virologists on the Virology Capabilities Test — which suggests the threshold for "significantly helps amateurs make bioweapons" may be near or crossed for some models.

**Estimated harm if open-weight models at this capability level are released:** ~100,000 fatalities per year in expectation, primarily through increased probability of pandemic-scale events. This is the author's rough estimate with acknowledged high uncertainty.

**Key argument:** Despite this cost, Greenblatt argues open-weight releases at *this* (but not higher) capability level are likely net positive because of benefits to alignment research, interpretability, and societal awareness — which reduce larger catastrophic risks (AI takeover). This is a sophisticated argument that doesn't minimize the harm but contextualizes it against alternative risks.

**Relevance:** This is important because it represents an AI safety insider conceding that the empirical marginal harm from open-weight models at current capability levels is real but modest compared to what could be done with internet access alone — while also arguing the capability threshold is being approached.

**Link:** https://www.alignmentforum.org/posts/TeF8Az2EiWenR9APF

---

### 9. The "Thecounterfactual" Explainer (Sophie Kim, March 2026)

A policy-focused explainer (Substack, not peer-reviewed) framing the open-weight problem primarily for biosecurity audiences. Key points documented: abliteration (a technique using ~7GB GPU and basic Python knowledge to strip refusals from models), and the structural claim that open-weight models can be run locally with no monitoring, no usage logging, no ability to revoke access or patch vulnerabilities.

**Relevance:** Captures the security policy argument most cleanly — the issue is not just what models can do but the *unmonitored, unrevocable* nature of open-weight access. This is a qualitatively different threat model than "better performance on harmful tasks."

**Note:** This is a Substack post, not a peer-reviewed source.

---

## Surprises, Contradictions, and Gaps

**Surprise 1:** The RAND study — the most rigorously controlled empirical uplift test that exists — found no statistically significant uplift from LLMs for bioweapon attack planning as of 2024. This is a remarkably strong null result that is not widely cited in AI safety discourse, which tends to assume uplift exists and argues about its magnitude.

**Surprise 2:** Fine-tuning attack vulnerability is symmetric between open and closed models — closed-weight API models are also vulnerable to safety removal via fine-tuning APIs, as demonstrated on GPT-3.5, GPT-4o, Claude 3 Haiku, and Gemini. The open/closed distinction is less binary than commonly assumed.

**Surprise 3:** The NTIA explicitly concluded that restrictions were not warranted in 2024 after a rigorous public comment process. This is US government policy directly contradicting the precautionary safety case.

**Contradiction:** The RAND null result (no measurable uplift from current LLMs) sits in tension with Greenblatt's expert estimate (~100K expected annual deaths if open-weight models above the "amateur bioweapons" threshold are released). These are not necessarily incompatible — RAND tested LLMs from 2023; by 2025 the VCT data suggests frontier models may have crossed the capability threshold. The empirical question of whether today's open-weight models are above or below that threshold remains genuinely open.

**Gap 1:** Almost no published work measures "Observed use" (the third stage of CSET's PPOu framework) — there is essentially no public empirical record of real-world mass-casualty events caused by open-weight models. The argument for restriction rests almost entirely on worst-case capability assessments, not actualized harms.

**Gap 2:** The MFT methodology in Wallace et al. is a first attempt; it has not been independently replicated, and it was conducted by the company seeking to release the model it evaluated.

**Gap 3:** The fine-tuning literature does not cleanly separate the question "can safety be removed?" (clearly yes) from "does safety removal plus open weights produce meaningful net uplift over existing tools?" (much less clear — a freely available bomb-making manual on the internet may be equally or more useful than a fine-tuned LLM).

**Gap 4:** Cyberattack uplift is much less studied than biorisk. The OpenAI MFT paper addresses CTF performance but CTF challenges differ substantially from real offensive cyber operations.

---

## Assessment: Does the Empirical Evidence Support or Undermine the Safety Case Against Open-Weight Models?

**The safety case is weakened but not refuted by the evidence.**

The strongest evidence against restriction:
- RAND 2024 found zero measurable uplift from LLMs for bioweapon planning vs. internet-only baseline (the most rigorous direct test available)
- NTIA 2024 concluded against restriction after examining the full evidence base
- Fine-tuning attacks work on closed-weight models too, weakening the "open = uniquely vulnerable" claim
- The Kapoor et al. framework shows that most "risk" arguments fail to compare against counterfactual baselines (internet, textbooks, prior knowledge)

The safety case is sustained by:
- The fine-tuning literature (Qi 2023, Yang 2023, FAR.AI 2025) shows alignment is technically cosmetic and universally removable — safety labels on open-weight models should not be taken seriously as real barriers
- The unmonitored/unrevocable nature of open-weight access is qualitatively different from API access even if raw capability is similar
- There is a plausible and growing concern that frontier open-weight models are approaching a genuine capability threshold for biosecurity uplift (VCT data, Greenblatt estimate)
- The "small marginal risk today" argument does not handle the future trajectory — a model that provides 10% uplift today may provide 80% uplift in three years, but once weights are released they cannot be recalled

**The empirical evidence, taken honestly, currently supports the NTIA position: open-weight models at current (2024-2025) capability levels do not appear to substantially advance harm beyond what determined bad actors can achieve without them.** The safety argument depends heavily on forward-looking extrapolation rather than measured actualized harm. That extrapolation may be correct, but it is a different argument than an empirical one — it is a capability trajectory argument, and those have been wrong before.

The most intellectually honest summary: the empirical gap between open-weight and closed-weight models in enabling harm is currently small to negligible at current capability levels, but the gap may widen sharply as frontier capabilities increase, and by the time it is empirically confirmed to be large, restricting open-weight models will be much harder.
