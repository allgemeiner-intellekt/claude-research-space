# Survey: What Do Independent Researchers Argue About Open vs. Closed AI Safety?

## What Was Searched / Read

**Searches conducted:**
- Stella Biderman / EleutherAI Senate testimony (Schumer AI Insight Forum)
- Irene Solaiman "gradient of generative AI release" (FAccT 2023)
- Elizabeth Seger et al. "Open-Sourcing Highly Capable Foundation Models" (SSRN 2023)
- Toby Shevlane "structured access" (2022)
- Widder, Whittaker, West "Why 'open' AI systems are actually closed" (Nature 2024)
- Arvind Narayanan + Sayash Kapoor AI Snake Oil blog posts (Princeton)
- Yoshua Bengio "Reasoning through arguments against taking AI safety seriously" (2024)
- Mozilla / EleutherAI / Hugging Face Joint Statement on AI Safety and Openness
- Divya Siddarth / CIP "Roadmap to Democratic AI" (2024)
- Foundation Model Transparency Index (Bommasani et al., Stanford HAI)
- Gyevnar & Kasirzadeh "AI Safety for Everyone" (Nature Machine Intelligence 2025)
- NTIA Dual-Use Foundation Models with Widely Available Weights report (2024)

**Key URLs fetched directly:**
- https://www.schumer.senate.gov/imo/media/doc/Stella%20Biderman.pdf (full text)
- https://www.normaltech.ai/p/ai-safety-is-not-a-model-property (full text)
- https://www.aisnakeoil.com/p/are-open-foundation-models-actually (full text)
- https://yoshuabengio.org/2024/07/09/reasoning-through-arguments-against-taking-ai-safety-seriously/ (full text)
- https://open.mozilla.org/ai-safety/ (full text — joint statement with 1800+ signatories)
- https://www.cip.org/research/ai-roadmap (Siddarth / CIP)
- https://arxiv.org/abs/2502.09288 (Gyevnar & Kasirzadeh abstract)
- Nature paper (Widder et al.) cached at https://www.nature.com/articles/s41586-024-08141-1.pdf

---

## Key Findings by Position

### PRO-OPEN: The case for open-weight release from non-commercial voices

#### Stella Biderman (EleutherAI) — Senate testimony, October 2023
- **Link**: https://www.schumer.senate.gov/imo/media/doc/Stella%20Biderman.pdf
- **Core argument**: "Closed models are not safe — their dangers are just hidden." Safety filters on commercial APIs are "much better at making models look safe than actually be safe." The alleged safety protocols "are very easily subverted and are frequently ineffective patches over deeper issues."
- **Transparency case**: Open models enable reproducible evaluation, bias auditing, and training data inspection — none of which are possible for closed models. Companies "actively censor" researchers trying to test limitations of their models.
- **Innovation case**: The academic/open-source ecosystem drove the core algorithmic innovations behind GPT-style models; closedness now severs this link and stifles safety research itself.
- **Institutional credibility**: Non-profit, independent. Biderman had co-authored the Seger et al. multi-stakeholder paper (below) — unusual given the papers take different positions; she was the dissenting voice there. Senate-level testimony context gives this primary-source weight.

#### Arvind Narayanan & Sayash Kapoor (Princeton) — AI Snake Oil
- **Links**:
  - "AI safety is not a model property" (March 2024): https://www.normaltech.ai/p/ai-safety-is-not-a-model-property
  - "Are open foundation models actually more risky than closed ones?" (Dec 2023): https://www.aisnakeoil.com/p/are-open-foundation-models-actually
- **Core argument**: Safety is not a property of models — it depends on deployment context, platform-level defenses, and downstream enforcement. "Trying to make an AI model that can't be misused is like trying to make a computer that can't be used for bad things." This reframes the entire open/closed debate: if safety can't be built into models, the marginal risk difference between open and closed release is much smaller than claimed.
- **On marginal risk**: The relevant question is not whether open models can be misused (yes, always) but the *marginal* risk over what is already possible. For cybersecurity and biosecurity risks, the evidence that open models provide meaningful uplift above existing resources is "overstated." For CSAM/NCII, marginal risk is genuinely substantial.
- **Incentives critique**: Red teaming by developers is systematically biased — firms have incentives not to discover capabilities they cannot fix, leading to performative safety theater.
- **On the open/closed distinction**: Recommends defenses be located at downstream platforms (attack surfaces), not inside models. Notes that "there are other ways to address these harms that are downstream of the model itself."
- **Credibility**: Narayanan is a Princeton CS professor and co-author of the book "AI Snake Oil" (Princeton UP, 2024). Kapoor is a PhD student at Princeton. Non-commercial. Both were signatories to the Mozilla joint statement below. The NTIA cited the Stanford HAI policy brief they co-produced.

#### Mozilla / EleutherAI / Hugging Face — Joint Statement on AI Safety and Openness
- **Link**: https://open.mozilla.org/ai-safety/
- **Core argument**: "The idea that tight and proprietary control of foundational AI models is the only path to protecting us from society-scale harm is naive at best, dangerous at worst." Openness accelerates independent risk research, enables regulatory monitoring, lowers barriers for responsible entrants.
- **Signatories** (non-commercial subset): Stella Biderman (EleutherAI), Joy Buolamwini (Algorithmic Justice League), Deborah Raji (UC Berkeley), Abeba Birhane (Mozilla Fellow), Bruce Schneier (Berkman Center), Alexandra Reeve Givens (CDT), Irina Rish (Mila), Arvind Narayanan (Princeton), Shayne Longpre (MIT), and ~1800 others.
- **Notable**: The statement explicitly acknowledges open models "come with risks and vulnerabilities" but argues the historical pattern from open-source software shows "public access and scrutiny makes technology safer, not more dangerous."
- **Credibility**: Civil society coalition including academic, non-profit, and advocacy voices. Not a research paper — a position statement. Carries weight as a coordinating signal for what the open-source AI community believes. Note Yann LeCun (Meta) also signed, but he has commercial interests; the civil society signatories above do not.

#### Irene Solaiman — "Gradient of Generative AI Release" (FAccT 2023)
- **Link**: https://arxiv.org/pdf/2302.04844 (132 citations)
- **Core argument**: Release is not binary (open vs. closed) but a gradient of six levels from fully closed to fully open. Key insight: "release methods come with tradeoffs, especially around the *tension between concentrating power and mitigating risks*." Both closedness and openness can concentrate power in different ways. Diverse multidisciplinary perspectives are needed throughout the development lifecycle, not just at deployment.
- **Credibility**: FAccT peer-reviewed paper. Solaiman was at Hugging Face (now independent). Has commercial adjacency but the framework itself is a research contribution. One of the most-cited papers on this topic (132 cites).
- **Companion paper (2025)**: "Beyond Release: Access Considerations for Generative AI Systems" (Solaiman, Bommasani, Hendrycks et al.) — extends the framework to argue that "access variables" like compute infrastructure, technical usability, and utility better predict risks than simple open/closed distinctions. Both open-weight and closed-weight frontier models raise similar access considerations.

---

### ANTI-OPEN (or skeptical): The case for caution/restriction from non-commercial voices

#### Yoshua Bengio — personal blog posts and International Scientific Report
- **Links**:
  - "Reasoning through arguments against taking AI safety seriously" (July 2024): https://yoshuabengio.org/2024/07/09/reasoning-through-arguments-against-taking-ai-safety-seriously/
  - Senate testimony (July 2023): https://www.judiciary.senate.gov/imo/media/doc/2023-07-26_-_testimony_-_bengio.pdf
- **Core argument**: Bengio's main concern is existential risk from AGI/ASI, not near-term open-weight models specifically. On open-source AI specifically, he writes: "Open-sourcing of AI systems may plausibly currently be more beneficial than detrimental to safety because they enable AI safety research in academia while current systems are apparently not yet powerful enough to be catastrophically dangerous in bad hands or with loss of control. **But in the future,** who should decide where to draw the line?"
- **Key concern**: Fine-tuning of open-source systems "would reveal dangerous capabilities from the point of view of loss of control." Once released, an open-source system "cannot be fixed against newly discovered vulnerabilities, unlike a closed-source system." He also raises the bioweapons vector: a rogue AI (or human using an open model) could design pathogens in silence.
- **Power concentration concern**: He specifically does *not* favor raw corporate closedness as a solution. He wants "trustworthy researchers given controlled access" and "multistakeholder governance" — a structured-access model, not free-market closedness.
- **Credibility**: Turing Award winner, chair of the International Scientific Report on AI Safety (30 countries + UN). Non-commercial (Mila/Université de Montréal, non-profit aligned). His position has *evolved* — earlier he was more focused on bias/fairness concerns; by 2023-2024 he publicly shifted to existential risk framing.
- **Assessment**: His position on open-weight is nuanced and threshold-dependent, not a blanket anti-open stance. He accepts that current open models may be net-positive; his concern is about a capability threshold that may not yet be crossed but could be. This is importantly *different* from the commercial frontier labs' closedness rationale.

#### Elizabeth Seger et al. — "Open-Sourcing Highly Capable Foundation Models" (2023)
- **Link**: https://arxiv.org/pdf/2311.09227 (61 citations)
- **Core argument**: For "highly capable foundation models likely to be developed in the near future," open-sourcing may pose "sufficiently extreme risks to outweigh the benefits." Key argument: irreversibility — once weights are released, safety vulnerabilities cannot be patched. Argues for "alternative strategies" (structured access, staged release) rather than full open-sourcing as capability increases.
- **Importantly**: This paper has Stella Biderman as a co-author — she was a dissenting voice within the collaboration, illustrating genuine internal disagreement. The paper represents a range of positions, not a monolithic anti-open stance.
- **Affiliation complexity**: Most authors are from Constellation / Centre for Long-Term Resilience / GovAI — EA-adjacent think tanks. Technically non-commercial but with funding/ideological ties to the EA safety community. This limits how "independent" the voice is.
- **Key recommendations**: Graduated release, staged access, independent auditing before full open release, formal structured access mechanisms for researchers.

#### Toby Shevlane — "Structured Access: An Emerging Paradigm for Safe AI Deployment" (2022)
- **Link**: Semantic Scholar paperId `4f08def1c8843e8d9878a89c4582a84fa29ca644` (60 citations)
- **Core argument**: Instead of open dissemination, AI developers should provide controlled API access — "arm's length interactions" — that allows useful research and deployment while preventing direct model extraction, fine-tuning for harmful purposes, and capability modification. Key insight: cloud-based interfaces give developers more scope to monitor, control, and patch model behavior than locally-running weights can.
- **Credibility**: Shevlane was at GovAI (Oxford, non-commercial safety research center), now at DeepMind. The GovAI origin makes it non-commercial but safety-lab-adjacent. The 2022 paper is widely cited as the canonical academic case for structured access as a middle path.

---

### MIDDLE GROUND / FRAMEWORK-BUILDERS

#### Widder, Whittaker & West — "Why 'open' AI systems are actually closed, and why this matters" (Nature 2024)
- **Link**: https://www.nature.com/articles/s41586-024-08141-1 (46 citations in Nature)
- **Core argument**: Neither the pro-open nor anti-open camp uses "open" with precision. Real openness requires transparency across models, data, labor, frameworks, and computational power — not just weight release. Most "open" AI models are actually closed on multiple dimensions (training data, compute, architecture details). Opening weights alone does not perturb concentration of power; just as in open-source software, large tech companies can co-opt "open" rhetoric while maintaining structural dominance.
- **Safety valence**: The paper sidesteps the direct safety debate to undermine both sides' premises. The safety claims of closed labs are false (their models are not made safe by being closed). But the democratization claims of open labs are also false (releasing weights does not meaningfully redistribute power when training data, compute, and distribution remain concentrated).
- **Authors**: David Gray Widder (Cornell/CMU), Meredith Whittaker (AI Now Institute / Signal Foundation), Sarah Myers West (AI Now Institute). Whittaker and West are non-commercial civil society researchers with strong anti-concentration-of-power orientations.
- **Credibility**: Nature — highest prestige venue. Non-commercial authors. 46 citations in ~1 year. Represents the most sophisticated structural critique of the entire open/closed framing.

#### Foundation Model Transparency Index (Bommasani et al., Stanford HAI)
- **Links**:
  - FMTI 2023: https://arxiv.org/abs/2310.12941 (108 citations)
  - FMTI 2024: Trans. Machine Learning Research (21 citations)
  - FMTI 2025: Robotics venue (7 citations)
- **Core argument**: Transparency and open-weight are not equivalent. The FMTI measures 100 indicators spanning upstream resources, model details, and downstream use. Key 2025 finding: average transparency score fell from 58/100 in 2024 to 40/100 in 2025 — even as open models became more common. Open model developers score higher than average, but even they disclose very limited information about training compute and downstream impact.
- **On the debate**: The FMTI implicitly argues that transparency (which can be partial, with open weights) is more governable and auditable than full opacity, but that releasing weights alone is not sufficient transparency.
- **Credibility**: Stanford HAI, academic institution. Bommasani and Liang are non-commercial CS academics. The FMTI has become a policy reference document (EU AI Act discussions cite it). Rishi Bommasani is also a co-author on the 2025 "Open Technical Problems in Open-Weight AI Model Risk Management" paper (with Bengio, Hendrycks, et al.).

#### Gyevnar & Kasirzadeh — "AI Safety for Everyone" (Nature Machine Intelligence 2025)
- **Link**: https://arxiv.org/abs/2502.09288 (published in Nature Machine Intelligence, April 2025)
- **Core argument**: Recent AI safety discourse has "increasingly emphasized the deep connection between AI safety and existential risk from advanced AI systems," which has three harms: (1) excludes researchers doing practical safety work from different angles, (2) misleads the public into thinking safety = existential risk only, (3) creates resistance among those who disagree with x-risk predictions.
- **Safety valence for open/closed debate**: This paper argues that the frontier-lab framing of safety (dominated by x-risk concerns, which tend to favor closedness) systematically excludes the broader safety community working on adversarial robustness, interpretability, bias, and systems safety. By extension, the "safety" argument for closedness is actually the argument of a narrow epistemic community, not the full range of safety expertise.
- **Credibility**: Nature Machine Intelligence — top venue. Non-commercial (University of Edinburgh / independent). Recent (2025), so it captures the current state of the debate.

#### Divya Siddarth / Collective Intelligence Project — "Roadmap to Democratic AI" (2024)
- **Link**: https://www.cip.org/research/ai-roadmap
- **Core argument**: The safety/openness debate is framed wrong by both sides. The real question is whether AI development produces adaptive, accountable institutions and distributes benefits and risks broadly. Neither raw openness nor raw closedness achieves "democratic AI." The CIP focuses on mechanisms for collective stewardship — participatory processes, distributed governance, multi-stakeholder oversight.
- **On open/closed**: Siddarth's earlier Journal of Democracy piece ("Reimagining Democracy's Defense," 2023) critiques both the "US must win the AI race" framing and the accelerationist position. Her implicit position is that concentration of power in any single entity — whether a closed lab or an open-weight dominant provider — is the real threat.
- **Credibility**: Non-commercial R&D lab. Siddarth is a scholar-practitioner, non-commercial. The CIP organized the OpenAI Alignment Assembly, which gives them an unusual inside-outside position.

---

## The Strongest Steelmanned Cases

### Steelman for PRO-OPEN (non-commercial voice)
**Best source: Narayanan & Kapoor, "AI safety is not a model property" (2024)**

Safety cannot be a property of model weights because the model lacks the contextual information needed to determine whether any given use is harmful. A model cannot know if it's writing a marketing email or a phishing email — the harm is in the downstream deployment, not the model output. This means that (a) safety guardrails on closed models are theater that impedes legitimate use without preventing harm, (b) the marginal risk of releasing open weights is low for the harms where defenses exist at the platform/distribution layer, and (c) the genuine benefits of open weights — diverse safety research, independent auditing, academic study of capabilities and biases — are foregone without commensurate safety gain. The commercial incentive structure means closed-model red-teaming is systematically biased toward not finding unpatchable problems. Openness realigns these incentives by bringing in researchers with no stake in the outcome.

### Steelman for ANTI-OPEN (non-commercial voice)
**Best source: Bengio (2024) on the asymmetry of catastrophic misuse**

The current debate about marginal risk is conducted entirely in the regime of current models. But the case for closedness is not about current models — it is about models at or near human-level capability in domains like bioweapons synthesis. For such a model, the asymmetry is fatal: a single actor (a state, a terrorist, a suicidal individual) who uses the model to design a novel pathogen provides a first strike that cannot be recalled. The inability to "patch" released weights becomes irreversible catastrophe, not inconvenience. At this capability threshold, the open-source case collapses: the democratization benefits are genuine but finite; the catastrophe risk, if it materializes, is unbounded. Open weights at GPT-3 scale: probably net positive. Open weights at hypothetical-AGI scale: a qualitatively different question. The hard governance problem is that by the time you know you've crossed the threshold, it may be too late to act. This is a specifically non-commercial argument (Bengio gains nothing from closedness) and it is structurally distinct from the commercial labs' safety rhetoric.

---

## Gaps and Assessment

**What's clear:**
- There is no unified "non-commercial" position. Independent researchers split along two axes: (1) their estimate of near-term catastrophic risk, and (2) their view on whether safety can be achieved at the model level at all. Narayanan/Kapoor and Biderman share skepticism about model-level safety, leading to pro-open conclusions. Bengio and Seger accept model-level safety concerns but with different calibrations of catastrophic risk.
- The strongest independent arguments against open models are *conditional* — they depend on capability thresholds that may not yet be crossed. This conditional structure is often lost in policy debates, where Bengio's nuanced position gets recruited as cover for blanket closedness.
- The Widder/Whittaker/West critique (Nature 2024) is the most sophisticated: it argues that both camps in this debate are arguing about a framing ("open" AI) that misrepresents the actual distribution of power and control in the AI ecosystem.

**What's contested:**
- How large is the marginal risk of open vs. closed? The NTIA report (2024) concluded the evidence was insufficient to justify restrictions at current capability levels. Narayanan/Kapoor agree. Seger et al. (with Biderman dissenting) argue that planning for future thresholds justifies caution now.
- Does releasing weights enable meaningfully more harmful fine-tuning than closed API access with jailbreaks? Bengio says yes (he cites the asymmetry of attack and defense in this space). Narayanan says the evidence for uplift in biosecurity and cybersecurity is overstated relative to what's already available.

**Under-explored:**
- The empirical question of actual uplift. Almost all papers note that the evidence base is thin. The few studies (e.g., on biosecurity) are methodologically contested and often funded by groups with priors.
- The non-Western non-commercial voice is largely absent. All sources are US/European. AI governance perspectives from the Global South — which may have very different risk/benefit calculations — are systematically excluded from this debate.
- The distinction between open-weight release *by labs* vs. open-weight development *by the community*. Releasing Llama-3 is not the same as BLOOM (trained by a research consortium). The governance and accountability differ substantially, but safety discourse treats them as equivalent.
- The interaction with compute concentration. Widder et al. and Siddarth both point out that open weights are nearly irrelevant to power distribution if the ability to train frontier models is concentrated in 3-5 organizations. This structural point is absent from most safety-framed discussions.

**Surprises:**
- Stella Biderman co-authored the Seger et al. paper that argues *against* open-sourcing highly capable models, while her own Senate testimony argues the opposite. This suggests the paper was a genuine attempt at consensus that included a significant internal dissenter — not a manufactured position.
- Bengio's position on open weights is considerably more nuanced than he is typically portrayed. He explicitly says open-sourcing *current* models "may plausibly currently be more beneficial than detrimental to safety" — a position that would surprise many who cite him as an anti-open authority.
- The Mozilla joint statement (1800+ signatories) includes Bruce Schneier (a genuine security expert not affiliated with any AI lab) and Joy Buolamwini — voices who have historically criticized AI industry safety claims. Their presence adds weight to the pro-open civil society coalition.
- The "AI Safety for Everyone" paper (Nature Machine Intelligence 2025) is a direct attack on the epistemic closure of the frontier-lab safety community. It frames the safety/open debate as partly a turf war over what counts as safety expertise.
