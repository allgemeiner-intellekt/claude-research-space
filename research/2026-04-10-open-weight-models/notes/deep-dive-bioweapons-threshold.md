# Deep Dive: The LLM Bioweapons Uplift Threshold — Reconciling RAND, Greenblatt, and VCT

## Question

Do we have measured harm from LLM bioweapons uplift, or is the safety case for restricting open-weight models a trajectory/precautionary argument? Specifically: how do the RAND 2024 null result, the Greenblatt ~100K fatalities/year estimate, and the VCT 2025 "outperforms expert virologists" finding fit together, and what does the evidence chain actually support?

---

## Investigation

### Thread 1: What RAND Actually Tested and Found

The RAND red-team study (Mouton, Lucas, Guest, RR-A2977-2, January 2024) is a carefully designed experiment, not a theoretical argument. Here is what it actually did:

**Design:** Several dozen researchers were divided into small teams and given seven weeks to plan a large-scale biological attack. Grading was done by an expert panel assessing plan viability. Some teams had LLM access plus internet; others had only internet. The study involved multiple LLMs (the report is cautious about naming specific models but the research spanned late 2022–2023 vintage models, primarily GPT-3.5/4 class systems).

**Key null result:** No statistically significant difference in plan viability between LLM-assisted and internet-only teams. Most plans had "major flaws" and fell between "problematic" and "unworkable." The highest-scoring team had LLM access but its plan drew on academic literature, not AI outputs — the LLM was redundant.

**On "unfortunate outputs":** In cases where LLMs provided biologically relevant information (e.g., maximizing casualties, cultivating plague bacteria), all such information was confirmed to be available on CDC websites or academic literature within a few clicks. The report explicitly states: "none of the AI outputs yielded any meaningful information that the internet-only teams could not also find."

**The key limitation the authors themselves flagged:** The study deliberately did not attempt to measure *how close* LLM capabilities are to the threshold where they would provide genuine uplift. The authors wrote that it "remains uncertain whether these risks lie 'just beyond' the frontier of existing AI models." This is a crucial caveat: a null result when testing against a threshold does not mean the threshold is far away.

**What models were being tested:** The preliminary report (RR-A2977-1, October 2023) noted that experiments were being run with models available at that time. The final report was published January 2024 but the research was conducted earlier. This means the RAND study tested roughly GPT-3.5/early-GPT-4 era models — the same generation that scores roughly 15–25% on specialized biology benchmarks like VCT.

---

### Thread 2: VCT — What the Finding Actually Means

The Virology Capabilities Test (Götting, Medeiros, Sanders, Li, Phan, Elabd, Justen, Hendrycks, Donoughe; arXiv 2504.16137; April 2025) is a benchmark of 322 multimodal questions testing practical virology troubleshooting knowledge. Here is what it actually measures and what it does not.

**What was tested:** The benchmark was constructed from the inputs of 57 PhD-level virologists (average experience ~6 years) contributing questions drawn from their actual lab work. Questions were peer-reviewed by two other experts, tested for Google-proofness (non-experts using web search should fail them), and filtered to focus on practical troubleshooting — "what went wrong in this experiment, what should you do next?" — often with an image of experimental results requiring interpretation.

**The headline claim:** OpenAI's o3 scored 43.8% accuracy, outperforming 94% of expert virologists on question subsets matched to their own declared areas of expertise. Expert virologists averaged 22.1% on their specialty-matched subsets.

**Why the 22.1% expert baseline looks surprising:** The paper explains this: VCT specifically targets knowledge that does not exist in textbooks — the tacit know-how that lives in lab meeting conversations and hallway consultations. Individual experts are being measured against their *own* sub-specialty, and experts apparently lack access to the full consensus of their field. The models, having processed vast amounts of text from across virology, have synthesized a "wisdom of the crowd" that individual specialists don't possess. The paper is careful about this interpretation.

**What VCT does not measure:** The paper is explicit on this point: "It is important to point out that VCT does not measure hazardousness per se." The benchmark covers "standard methods that are used daily for beneficial research." The "outperforms virologists" result is about practical troubleshooting for standard virology techniques — the kind of knowledge a first-year graduate student would need. It does not measure:
- Ability to design novel pathogens
- Knowledge of how to acquire dangerous materials
- Operational planning for a biological attack
- End-to-end synthesis or weaponization protocols

**The dual-use inference:** The authors argue, reasonably, that since these troubleshooting capabilities apply equally to methods with benign and dangerous uses, the finding raises governance concerns. A model that can answer "why did my plaque assay fail?" for standard cell culture can potentially apply the same reasoning to BSL-3/4 protocols — though VCT deliberately excluded questions the authors judged "excessively hazardous."

**Temporal finding:** Gemini 1.5 Pro (released February 2024) was the first model to beat the median expert virologist on VCT. This means the capability threshold described by VCT was crossed at roughly the same time RAND was publishing its null result — which is precisely the kind of capability movement that matters for reconciling the two findings.

**Methodological note:** VCT uses zero-shot prompting in a multiple-response format (identify all true statements from 4-10 options). This is a harder format than single-answer MCQ, but it remains a multiple-choice benchmark. The paper acknowledges that follow-up wet-lab uplift studies are needed to determine whether high VCT scores actually translate to higher success rates in real laboratory experiments.

---

### Thread 3: Greenblatt's 100K Estimate — Reasoning Chain Exposed

The June 2025 AlignmentForum post "When is it important that open-weight models aren't released?" by ryan_greenblatt is where the ~100K fatalities/year figure comes from. The reasoning chain is as follows:

**The hypothetical being evaluated:** Greenblatt is not estimating harm from *current* open-weight models. He is explicitly evaluating a hypothetical scenario: "AIs which are at this 'significantly helping amateurs' capability threshold are released with open weights." The capability threshold he defines is the Anthropic ASL-3 trigger: "the ability to significantly help individuals or groups with basic technical backgrounds (e.g., undergraduate STEM degrees) create/obtain and deploy CBRN weapons."

**The reasoning chain:**
1. COVID-19 killed ~30 million people.
2. Open-weight models at this capability threshold would increase the probability of comparable pandemics by "somewhat more than 0.1% per year."
3. 30 million × 0.1% = 30,000 per year as a floor. With "somewhat more than 0.1%" and uncertainty about pandemic severity distribution, he rounds up to ~100,000 expected fatalities per year.
4. Expected fatalities are dominated by tail events: the distribution of pandemic mortality is heavy-tailed, so a small number of catastrophic events drive most of the expected value.

**What this estimate depends on:**
- The claim that models at the ASL-3 threshold exist or will soon exist (plausible as of mid-2025, given Anthropic activating ASL-3 protections for Claude Opus 4)
- An estimate of the annual probability that a motivated amateur using such a model would succeed at causing a pandemic-scale event (his 0.1%+ figure)
- The assumption that the baseline rate of such attempts (without open-weight models) is negligible, i.e., models are the binding constraint
- The assumption that safeguarded closed-weight models can prevent most misuse (so the counterfactual is not "same models but closed")

**The acknowledged uncertainties:** Greenblatt is explicit that his estimate is "quite uncertain" and "depends a lot on the number of at-least-slightly-competent bioterrorists." He also notes that media salience could dramatically increase or decrease the risk by affecting how many people attempt bioterrorism.

**This is a Fermi estimate, not a model output or empirical finding.** It is an explicit subjective probability estimate by a researcher at Redwood Research reasoning through a plausible scenario. Greenblatt labels it as such. The estimate is not derived from observed attack attempts, from red-team data, or from epidemiological modeling of biosecurity threats. It is a structured argument from assumed priors.

**The context of the estimate:** Importantly, Greenblatt's conclusion is not that open-weight models above this threshold should be banned. His conclusion is the opposite: even accepting 100K expected fatalities/year, he believes open-weight models at this threshold would be net-beneficial because they reduce larger existential risks (by accelerating AI safety research outside labs, and by increasing societal awareness). His estimate is an *acknowledgment of cost*, not a prohibition argument.

---

### Thread 4: The Bridge — RAND 2025 Update Directly Addresses the Gap

The most important single piece of evidence I found for reconciling the tension is a December 2025 RAND "Expert Insights" paper (Brent and McKelvey, PE-A3853-1, DOI: 10.7249/PEA3853-1), titled "Contemporary Foundation AI Models Increase Biological Weapons Risk."

This paper was published by the same institution that found no risk in 2024, and it directly reverses the prior conclusion — for 2024 models. The authors tested three 2024-vintage models: **Llama 3.1 405B, ChatGPT-4o, and Claude 3.5 Sonnet (new)**, and found that these models "successfully provide accurate instructions and guidance for recovering a live poliovirus from a construct built from commercially obtained synthetic DNA" — a test case the authors describe as applicable to producing other pathogenic viruses.

The paper explicitly challenges the "tacit knowledge" defense (the argument that biological weapons development requires tacit knowledge that LLMs cannot provide) by analyzing a historical case: a Norwegian ultranationalist who successfully synthesized a complex explosive using publicly available knowledge, despite lacking formal chemistry training. The authors argue that the same pattern of success — motivated actor + available detailed information — is now reproducible in virology.

This is the bridge: RAND tested 2022-2023 era models in 2023 and found no uplift. RAND tested 2024 models in 2025 and found meaningful uplift on a specific, narrow but consequential task.

---

### Thread 5: Anthropic's ASL-3 Activation — Institutional Confirmation

Anthropic activated AI Safety Level 3 protections for Claude Opus 4 in May 2025. The key language from their announcement (anthropic.com/news/activating-asl3-protections) is important for calibrating how real the threshold crossing is:

"We have not yet determined whether Claude Opus 4 capabilities actually require the protections of the ASL-3 Standard" — this is a precautionary/provisional activation, not a confirmed threshold crossing.

But the rationale matters: "due to continued improvements in CBRN-related knowledge and capabilities, we have determined that *clearly ruling out* ASL-3 risks is not possible for Claude Opus 4 in the way it was for every previous model." Anthropic also explicitly cited VCT: "Model performance on evaluations like the Virology Capabilities Test had been steadily increasing over time."

Anthropic also noted partial uplift from earlier models: "Experiments showed that access to Claude Sonnet 3.7 helped participants do somewhat better on tasks related to CBRN weapon acquisition than those with standard internet access (although all participants' plans still had critical failures)." This is a critical data point: even in early 2025, before Opus 4, Anthropic's own red-team work was showing partial uplift — not null results, but not complete success either.

---

## Key Findings

- **RAND 2024 null result: strong evidence, but narrow scope.** The study tested LLMs available in 2022-2023 (roughly GPT-3.5/early GPT-4 era). The null result applies to that capability level. The study's own authors flagged uncertainty about how close the frontier was to the threshold. This is a real finding, not hype, but it is temporally bounded. (Strong evidence for 2022-2023 models; not informative about 2024-2025 models.)

- **VCT 2025: meaningful capability signal, but not direct uplift evidence.** o3 scores 43.8% on a hard virology troubleshooting benchmark vs. 22.1% for specialist humans. The first model to beat the median human expert appeared in February 2024 — the same month RAND's null result paper was published. VCT does not measure attack planning uplift, but it measures the underlying capability that makes such uplift possible. The paper explicitly calls for wet-lab uplift studies to bridge this gap. (Strong evidence of capability; moderate evidence of uplift risk, contingent on the dual-use inference holding.)

- **Greenblatt 100K: a Fermi estimate of expected harm conditional on a specific future state.** Not a measurement of current risk. Not an empirical finding. Explicitly hedged as highly uncertain. The estimate applies to a capability threshold (ASL-3) that was approaching but not confirmed as of mid-2025. The estimate's internal logic is coherent but rests on an unverified 0.1%/year pandemic probability — a number that nobody has a reliable way to estimate. (Speculative; structurally sound argument from uncertain priors.)

- **RAND 2025 update: this is the missing piece in the survey notes.** The Brent and McKelvey paper (December 2025) tested 2024-vintage models and found they successfully guided poliovirus synthesis from commercial DNA — a specific, narrow, but highly consequential task. This directly bridges the RAND null result and the VCT capability signal. (Strong evidence for a specific task; scope is narrower than general bioweapons planning.)

- **Anthropic ASL-3 activation (May 2025): institutional confirmation of capability approach.** Anthropic could not rule out ASL-3 capability for Opus 4, had evidence of partial uplift from earlier models, and explicitly cited VCT as a contributing signal. This is precautionary, not confirmed, but the institutional weight matters. (Moderate evidence; precautionary framing, not confirmed threshold crossing.)

---

## Assessment

The three-way tension in the survey notes dissolves when you read the sources carefully. Here is the coherent story:

**What 2022-2023 models could not do (RAND null result):** The first generation of frontier LLMs provided no meaningful uplift over internet access for attack planning. The information they provided mirrored CDC and academic sources. This was a genuine finding for that moment in time, not a permanent verdict on LLMs and bioweapons. The RAND authors themselves said the result did not reveal how close the frontier was to the threshold.

**What 2024-2025 models can do (VCT + RAND 2025 + Anthropic):** Models crossing the median human virologist on VCT benchmarks, providing accurate poliovirus synthesis instructions from commercial DNA, and prompting Anthropic to activate precautionary ASL-3 protections — these are evidence of a qualitative shift from the 2022-2023 baseline. The capability is real. The wet-lab uplift gap (from knowing what to do to successfully doing it) has not been bridged in public research, but RAND 2025 closes part of that gap.

**Where the trajectory points:** The trajectory is clear and undisputed. Models improve on biology benchmarks at roughly the same rate as other capabilities. The question is not whether LLMs will eventually provide serious bioweapons uplift — the direction is clearly toward that — but when and at what capability level. The debate is about whether we're already there (RAND 2025 says partially yes for specific tasks; Greenblatt says arguably yes for the ASL-3 threshold; Anthropic says "cannot rule out" for Opus 4).

**What's measured vs. extrapolated vs. argued from precaution:**

*Measured:* RAND 2024 null result for 2022-2023 models; VCT benchmark scores showing o3 at 94th expert percentile; RAND 2025 confirmation that 2024 models guide poliovirus synthesis; Anthropic partial uplift findings for Sonnet 3.7.

*Extrapolated:* That VCT troubleshooting capability = bioweapons uplift risk (reasonable inference, but not demonstrated); that current models are at the ASL-3 capability threshold (plausible but not confirmed).

*Argued from precaution:* Greenblatt's 100K estimate; Anthropic's ASL-3 activation for Opus 4.

**The overclaims:**

*Anti-open-weight camp overclaims:* Citing VCT's "outperforms expert virologists" headline without noting that (a) VCT tests troubleshooting for standard research methods, not bioweapons planning; (b) virologists scored only 22.1% in their own specialty, so "outperforming" them is not as alarming as it sounds — VCT scores are low across the board; (c) no wet-lab uplift study has confirmed that VCT scores translate to actual attack success rate increases. Citing Greenblatt's 100K as though it were a measured or modeled figure rather than a Fermi estimate.

*Pro-open-weight camp overclaims:* Citing RAND 2024 null result as though it settles the question for current models, ignoring the temporal scope the authors acknowledged; dismissing trajectory evidence; ignoring RAND 2025's updating of the 2024 finding with newer models.

**The honest answer for the report:** The safety case for restricting open-weight models above a certain capability threshold is primarily a trajectory/precautionary argument that is being increasingly backed by specific empirical observations. The claim is not "we have measured X deaths caused by open-weight LLMs" — nothing remotely like that exists. The claim is "models have crossed measurable capability thresholds in a domain where the knowledge itself is dual-use, and current models may be approaching or at the threshold where meaningful attack uplift begins." The evidence for the capability threshold being real (and being crossed recently) is now fairly strong. The evidence for the harm function (that capability threshold crossing translates to actual bioterrorism deaths) remains highly uncertain and is argued from prior-based reasoning, not from observed outcomes.

---

## Sources

- RAND RR-A2977-2 (Mouton, Lucas, Guest, January 2024): https://www.rand.org/pubs/research_reports/RRA2977-2.html — DOI: 10.7249/RRA2977-2
- RAND PE-A3853-1 (Brent, McKelvey, December 2025): https://www.rand.org/pubs/perspectives/PEA3853-1.html — DOI: 10.7249/PEA3853-1
- VCT paper (Götting et al., April 2025): https://arxiv.org/abs/2504.16137 — DOI: 10.48550/arXiv.2504.16137
- VCT authors' blog (securebio.substack.com, April 23, 2025): https://securebio.substack.com/p/ais-can-provide-expert-level-virology
- Greenblatt, "When is it important that open-weight models aren't released?" (AlignmentForum, June 9, 2025): https://www.alignmentforum.org/posts/TeF8Az2EiWenR9APF/when-is-it-important-that-open-weight-models-aren-t-released
- Greenblatt & Shlegeris, "Managing catastrophic misuse without robust AIs" (AlignmentForum, January 16, 2024): https://www.alignmentforum.org/posts/KENtuXySHJgxsH2Qk/managing-catastrophic-misuse-without-robust-ais
- Anthropic, "Activating AI Safety Level 3 protections" (May 22, 2025): https://www.anthropic.com/news/activating-asl3-protections
- RAND RR-A3124-1 (Persaud et al., June 2025): https://www.rand.org/pubs/research_reports/RRA3124-1.html — automated grading for biological capabilities
