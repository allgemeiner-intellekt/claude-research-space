# Survey: Anthropic's Position on Open-Weight Release and the Frontier Lab Landscape

## What Was Searched / Read

**Primary searches:**
- "Anthropic open-weight open-source AI models policy position statement"
- "Dario Amodei open source AI models quotes interview testimony"
- "Anthropic Responsible Scaling Policy RSP open weights ASL-3"
- "Meta Llama open source strategy Zuckerberg open letter AI 2024 2025"
- "OpenAI GPT-2 staged release open source history closed models evolution"
- "OpenAI gpt-oss open source reversal 2025 open weights reasoning model release"
- "Google Gemma open weights Gemini closed model strategy 2024 2025"
- "Centre for Future Generations Beyond the Binary tiered openness AI models report"
- "Dario Amodei open source AI 2024 2025 interview podcast"
- "Anthropic Dario Amodei 'open source' dangerous bioweapons CBRN safety risk"

**Pages read in full or near-full:**
- Anthropic RSP v3.0 announcement (Feb 24, 2026): https://www.anthropic.com/news/responsible-scaling-policy-v3
- OpenAI "Open weights and AI for all" (Aug 5, 2025): https://openai.com/global-affairs/open-weights-and-ai-for-all
- OpenAI "Introducing gpt-oss" (Aug 5, 2025): https://openai.com/index/introducing-gpt-oss/
- The Verge, Ilya Sutskever on GPT-4 closure (Mar 15, 2023): https://www.theverge.com/2023/3/15/23640180/openai-gpt-4-launch-closed-research-ilya-sutskever-interview
- Business Insider, Sam Altman on closed models (Nov 2, 2024): https://businessinsider.com/sam-altman-why-openai-closed-source-ai-models-2024-11
- Zuckerberg "Open Source AI Is the Path Forward" (July 2024), summarized via Spyglass: https://spyglass.org/zuckerberg-llama-open-source-ai/
- TechCrunch on Zuckerberg signaling future limits (July 30, 2025): https://techcrunch.com/2025/07/30/zuckerberg-says-meta-likely-wont-open-source-all-of-its-superintelligence-ai-models/
- Anthropic "Activating ASL-3 Protections" (May 22, 2025): https://anthropic.com/news/activating-asl3-protections
- OfficeChai summary of Amodei on open source vs. open weights (Sept 22, 2025): https://officechai.com/ai/anthropic-ceo-dario-amodei-explains-why-open-source-ai-isnt-the-same-as-open-source-software/
- Understanding AI (Tim Lee) on Claude Mythos Preview withheld release (Apr 8, 2026): https://www.understandingai.org/p/why-anthropic-believes-its-latest
- The Hill on Anthropic Mythos Preview / Project Glasswing (Apr 9, 2026): https://thehill.com/policy/technology/5824219-anthropic-new-ai-dangerous-public/
- CFG "Beyond the Binary" abstract/exec summary (arxiv.org/html/2602.19682v1, July 2025 / Feb 2026 arxiv)

---

## Key Findings

### 1. Anthropic: The Only Major Frontier Lab With Zero Open-Weight Releases

Anthropic has never released open-weight models. This is not an oversight — it is the deliberate outcome of a safety philosophy baked into the company from its founding. Anthropic was created in 2021 by Dario Amodei, Daniela Amodei, and others who left OpenAI partly because they believed the organization was not taking safety seriously enough. Their founding premise was that they were building potentially one of the most dangerous technologies in human history, and they should do so deliberately and cautiously.

The company's closest thing to a public statement on open weights comes through:
1. The Responsible Scaling Policy (RSP), which contains explicit provisions about model weight security
2. Dario Amodei's various public comments distinguishing "open weights" from "open source"
3. Implicit demonstration: every Claude generation has remained closed

**No dedicated blog post or policy document from Anthropic explicitly states "we will not release open-weight models."** The position is structural, not declarative. This is itself a notable fact.

### 2. Dario Amodei's Public Statements on Open Source / Open Weights

Amodei has been more active on this topic than Anthropic's official communications. Key statements:

**Conceptual reframe (Sept 2025 interview):** Amodei has consistently argued that "open source" is a misleading label for AI — and that the AI industry should use "open weights" instead, since you cannot actually read or modify the model's logic by examining its weights. Quote:
> "I don't think open source works the same way in AI that it has worked in other areas primarily because with open source, you can see the source code of the model here. We can't see inside the model. It's often called open weights instead of open source, right, to kind of distinguish that. But a lot of the benefits, which is that many people can work on it, that it's kind of additive, it doesn't quite work in the same way." (OfficeChai, citing Sept 2025 interview)

**Open source as a "red herring" (Sept 2025):** Amodei has said he doesn't care whether a competing model is open-source:
> "I don't care whether it's open source or not... I ask, is it a good model?... That's the only thing that I care about. It actually doesn't matter either way."

This is a notable rhetorical move: it dismisses the open/closed binary as strategically irrelevant while implicitly defending Anthropic's own closed stance.

**Bioweapons / CBRN threat emphasis (July 2023, Senate testimony):** At a Senate Judiciary Committee hearing in July 2023, Amodei warned senators about the risk of AI being used to create biological weapons. He warned about the danger of "uplift" — AI providing meaningful assistance to bad actors seeking to build weapons of mass destruction. This testimony was explicitly invoked as justification for not releasing model weights without CBRN safeguards.

**"Adolescence of Technology" essay (darioamodei.com, ~2026):** Amodei's personal website hosts long-form essays. The "Adolescence of Technology" essay argues that AI is at a formative, adolescent phase where safety norms must be established before the technology fully matures. The open-weight question is part of this framing — releasing weights prematurely could lock in irresponsible norms.

### 3. Anthropic's Responsible Scaling Policy (RSP) and Open Weights

The RSP is Anthropic's most structural commitment on capability thresholds and associated safeguards. It has gone through three versions:
- **RSP v1**: September 2023 — first version, defined ASL-2 and ASL-3 tiers
- **RSP v2**: October 2024 — updates and clarifications
- **RSP v3**: February 24, 2026 — significant restructuring, separating unilateral commitments from industry-wide recommendations

**Open weights under ASL-3:** The ASL-3 Security Standard (activated May 22, 2025, alongside Claude Opus 4) explicitly includes:
> "The ASL-3 Security Standard involves increased internal security measures that make it harder to steal model weights"

The text directly frames model weight security as a core safety measure. At ASL-3, the threat model includes "sophisticated non-state attackers" who might try to steal weights. The implication: if weights were publicly released, the entire ASL-3 security apparatus would be moot. Open-weighting a model at ASL-3 capability is, by the RSP's own logic, incompatible with responsible deployment.

**RSP v3 on unilateral vs. multilateral commitments:** RSP v3 explicitly separates what Anthropic will do unilaterally from what needs industry coordination. One key observation from the RSP v3 text: higher ASLs (ASL-4+) may require national security community assistance to protect weights — the RAND "SL5" standard for model weight security is described as "currently not possible" to achieve unilaterally. This creates an interesting tension: as models become more capable, keeping them closed may become harder to justify economically but also harder to guarantee practically.

**ASL-3 Deployment Standard: CBRN focus (May 2025):** The deployment standard explicitly targets preventing "extended, end-to-end CBRN workflows" — biological weapons are highlighted as the primary concern. The weight security standard is presented as the other side of the same coin: even if deployment controls block misuse through Claude's API, weight theft could let a bad actor strip all safeguards and run the model without restrictions.

### 4. Project Glasswing / Claude Mythos Preview: A Live Demonstration of the Policy (April 2026)

The most recent and concrete demonstration of Anthropic's position is the April 2026 non-release of Claude Mythos Preview. This model — apparently the most capable Anthropic has built — was determined to have capabilities dangerous enough that:
- It was not released publicly at all
- It was released only to ~50 organizations doing defensive cybersecurity work (including Google, Microsoft, Apple, Amazon, Nvidia)
- Access is under strict terms limiting use to cybersecurity purposes
- Anthropic committed $100M in usage credits plus $4M to open-source security organizations

**Why this matters for the open-weight question:** Mythos Preview represents Anthropic's position in its purest form — not just no open weights, but constrained access even for closed deployment. The model found thousands of zero-day vulnerabilities in every major operating system and web browser; it achieved a 72% success rate exploiting Firefox's JavaScript engine (vs. <1% for Claude Opus 4.6). The framing: Anthropic believes a general public release could let malicious actors cause cascading harms before defenders can patch. This is the logical extension of the RSP's CBRN concern applied to cybersecurity.

An "Understanding AI" (Tim Lee) analysis from April 8, 2026 notes that this is the first general-release delay since GPT-2 in 2019, and speculates that Anthropic may be pioneering a model where frontier labs increasingly keep their best models for internal/restricted use — exactly the opposite trajectory from Meta.

### 5. OpenAI: From "Open" to Closed to Reversal

**Origin:** OpenAI was founded in 2015 as an explicitly open nonprofit. Its founding blog post promised to "freely collaborate" and "build value for everyone." The name itself encoded this commitment.

**GPT-2 staged release (2019):** OpenAI initially released only smaller versions of GPT-2, citing fears about misuse for disinformation. This was controversial — critics called it overcautious or self-serving. Eventually the full 1.5B model was released. This established a staged-release model that the field has debated ever since.

**GPT-3/GPT-4 closure (2020–2023):** GPT-3 was never open-weighted. GPT-4 (March 2023) was released with essentially no technical transparency — no training data, no architecture details, no parameter count. Ilya Sutskever, asked about this at GPT-4's launch, said simply: "We were wrong. Flat out, we were wrong. If you believe, as we do, that at some point, AI — AGI — is going to be extremely, unbelievably potent, then it just does not make sense to open-source. It is a bad idea... I fully expect that in a few years it's going to be completely obvious to everyone that open-sourcing AI is just not wise." (The Verge, March 15, 2023)

**Sam Altman's 2024 position:** In a November 2024 Reddit AMA, Altman said closed models offer "an easier way to hit the safety threshold we want to hit" — framing closed source as a safety choice, not just a commercial one. He also said "I would like us to open source more stuff in the future."

**gpt-oss reversal (August 5, 2025):** OpenAI released gpt-oss-120b and gpt-oss-20b under Apache 2.0. These are described as "state-of-the-art open-weight language models... trained using a mix of reinforcement learning and techniques informed by OpenAI's most advanced internal models, including o3." The 120B model achieves "near-parity with OpenAI o4-mini on core reasoning benchmarks."

**OpenAI's stated justification for the reversal:** The accompanying blog post "Open weights and AI for all" frames the release in strikingly geopolitical terms: open models as "democratic AI" vs. "autocratic AI" (China), a way to build US-led AI infrastructure internationally, and as analogous to Linux as an open standard. The post explicitly invokes the White House AI Action Plan and frames open weights as "soft power." There is virtually no mention of safety considerations. This is a nearly complete inversion of Sutskever's 2023 framing. The justification is strategic and commercial (developer ecosystem, US geopolitical competition), not safety-based.

**Key observation:** OpenAI's reversal appears driven by competitive pressure from Meta's Llama ecosystem and geopolitical framing under the Trump administration's AI Action Plan, not by any new safety argument. Safety concerns that were "self-evident" in 2023 are not addressed in the 2025 gpt-oss announcement.

### 6. Meta / Zuckerberg: Open by Default (with Evolving Caveats)

**Core position (2024):** Zuckerberg published "Open Source AI Is the Path Forward" to accompany the Llama 3.1 release in July 2024. Key arguments:
- Open source prevents lock-in to competitor closed ecosystems (explicitly cited: Apple's platform restrictions)
- "A world of only closed models results in a small number of big companies plus our geopolitical adversaries having access to leading models"
- Meta's open-source releases historically benefit Meta by reducing costs and building ecosystems (PyTorch, React, Open Compute Project)
- Safety: "these models are trained by information that's already on the internet, so the starting point when considering harm should be whether a model can facilitate more harm than information that can quickly be retrieved from Google"

**Yann LeCun's position:** LeCun (Meta's chief AI scientist) has consistently argued that open-source AI is not only safer but necessary for healthy AI development. His position: closed models concentrate power dangerously, while open models allow societal oversight and competition. LeCun explicitly rejects the AGI-safety concerns that Amodei and Sutskever invoke.

**Business model clarity:** Meta's business is advertising, not AI APIs. Open-sourcing Llama does not cannibalize Meta's revenue. This gives Meta a genuine structural advantage in being able to release openly — a point Zuckerberg has made explicitly.

**Llama licensing caveat:** Critics (including the Open Source Initiative) have pointed out that Llama's license is not technically "open source" — companies with >700M monthly active users must request special permission. Meta disputes this characterization.

**Shift at the frontier (July 2025):** When launching "Meta Superintelligence Labs," Zuckerberg signaled that superintelligence-level models may not be open-sourced: "superintelligence will raise novel safety concerns. We'll need to be rigorous about mitigating these risks and careful about what we choose to open source." TechCrunch (July 30, 2025) noted this as a significant shift. Meta's spokesperson clarified: the company plans "a mix of open and closed models going forward." Reports indicate Meta paused its Llama Behemoth model and refocused on a closed model.

**Implication:** Meta's open-weight commitment, always partly strategic, appears to soften precisely at the capability frontier where Anthropic's concerns apply.

### 7. Google: The Hedge

Google pursues both tracks openly and without apparent embarrassment. Gemini (1.0, 1.5, 2.0, and beyond) remains closed. Gemma (1.0, 2, 3, 4) is open-weight. Gemma 4 was released April 2, 2026. Google's approach:
- Open Gemma models serve the developer/research community and generate ecosystem goodwill
- Closed Gemini models remain the commercial and capability-frontier offering
- No public statements from Google suggesting the two tracks are in tension

Google's dual-track strategy is more pragmatic than ideological — a hedge that lets the company participate in both ecosystems without committing to either philosophy. It also arguably generates less scrutiny than a purely closed approach.

### 8. The CFG "Beyond the Binary" Report (Centre for Future Generations, July 2025 / arxiv Feb 2026)

Authors: Bengüsu Özcan, Alex Petropoulos, Max Reddel (CFG Brussels)

**Key argument:** The paper explicitly rejects the open/closed binary and proposes a tiered, safety-anchored release framework. Key findings:
- Open-weight models are "rapidly closing the performance gap" with closed alternatives
- Once released, they "cannot be recalled" — fine-tuning/jailbreaking can bypass safeguards
- Current governance frameworks (EU, US, China, UK) show "significant disparities in safety practices" with "no commonly adopted standards"
- Recommends determining openness by "rigorous risk assessment and demonstrated safety rather than ideology, precedent, or commercial pressure"

**Relevance to Anthropic's position:** The CFG report essentially provides an academic/policy framework that aligns with Anthropic's implicit stance — but formalized as a governance proposal. It maps onto the RSP's capability-threshold logic. Anthropic's approach (ASL tiers, conditional protections) is closer to what CFG recommends than either Meta's default-open or OpenAI's arbitrary reversal.

---

## Surprises, Contradictions, and Gaps

**Surprise 1: Anthropic has never made a clear, stand-alone public statement saying "we don't release open weights and here's why."** The position is embedded in the RSP and in scattered interviews. There is no "Anthropic's Case Against Open Weights" document analogous to Zuckerberg's "Open Source AI Is the Path Forward." This makes Anthropic's position harder to critique or engage with on its own terms.

**Surprise 2: OpenAI's justification for gpt-oss completely dropped the safety framing.** Sutskever in 2023 said open-sourcing was "flat out wrong" on safety grounds. The gpt-oss announcement in 2025 said nothing substantive about safety — it was entirely about democratic access and geopolitical soft power. This is a remarkable inconsistency that nobody in the coverage I found directly confronted.

**Surprise 3: Meta's open-weight commitment has a clear commercial logic that makes it structurally different from others.** Meta doesn't sell AI API access, so open-sourcing Llama genuinely doesn't cannibalize revenue. This makes Meta's position more stable and less contradictory than it sometimes appears in debates — but also means it's less transferable as a model for companies like Anthropic or OpenAI.

**Contradiction: Zuckerberg's July 2025 shift.** Having built a brand identity around open-source AI, Zuckerberg quietly signaled he will apply safety criteria at the frontier — exactly the position he had criticized Anthropic and OpenAI for holding. Meta's "position on open source AI is unchanged" spokesperson statement is difficult to square with "careful about what we choose to open source" in the Zuckerberg letter.

**Gap: No primary-source Anthropic document specifically articulating why they don't release open weights.** The RSP addresses weight *security*, but from the perspective of preventing theft — not explaining the public-release decision. Amodei's interviews are the closest thing, but they're oblique.

**Gap: Timeline ambiguity around RSP activation and what it implies.** The RSP v1 (Sept 2023) established the framework; ASL-3 was actually activated only in May 2025. This means that for the first ~20 months after founding the RSP framework, Anthropic was operating under ASL-2 standards while the open-weight question was already live in public debate (Meta released Llama 1 in Feb 2023). There's no public documentation of what internal Anthropic discussions looked like during this gap.

**Gap: Dario Amodei's personal essays (Machines of Loving Grace, Oct 2024; Adolescence of Technology, ~2026) are relevant but I only skimmed summaries.** They discuss AI development philosophy at length but may contain additional framing of the open/closed question that I couldn't access in full due to file size constraints.

---

## Assessment of Coverage Quality

**Anthropic's position:** Good coverage via RSP documents, ASL-3 activation announcement, Mythos Preview coverage, and scattered Amodei quotes. The main gap is that there is no single comprehensive Anthropic statement to cite — the position must be pieced together.

**OpenAI's arc:** Excellent coverage. The Verge/Sutskever 2023 piece is a definitive primary source; the gpt-oss announcement provides the reversal; Business Insider provides Altman's 2024 bridging position. The story is well documented.

**Meta/Zuckerberg:** Good coverage for the 2024 open-source push; the July 2025 shift is well captured by TechCrunch. LeCun's philosophical position is cited but not deeply analyzed here (he had a major split from AMI Labs in early 2026 that may be relevant to future tracking).

**Google:** Thin. I know the facts (Gemma series alongside closed Gemini) but have no primary statements from Google leadership articulating their philosophy. This is a genuine gap.

**CFG report:** Good coverage of key claims and framework. Full text was inaccessible due to length, but the abstract and exec summary were captured.

**Key missing primary source:** Dario Amodei's Senate testimony (July 26, 2023) — the URL was found but the PDF content was not retrieved. This testimony likely contains his most direct public statement on AI risks from open release.

---

## Source List

1. Anthropic RSP v3.0 — https://www.anthropic.com/news/responsible-scaling-policy-v3 (Feb 24, 2026)
2. Anthropic "Activating ASL-3 Protections" — https://anthropic.com/news/activating-asl3-protections (May 22, 2025)
3. OpenAI "Open weights and AI for all" — https://openai.com/global-affairs/open-weights-and-ai-for-all (Aug 5, 2025)
4. OpenAI "Introducing gpt-oss" — https://openai.com/index/introducing-gpt-oss/ (Aug 5, 2025)
5. The Verge, Sutskever on GPT-4 closure — https://www.theverge.com/2023/3/15/23640180/openai-gpt-4-launch-closed-research-ilya-sutskever-interview (Mar 15, 2023)
6. Business Insider, Altman on closed models — https://businessinsider.com/sam-altman-why-openai-closed-source-ai-models-2024-11 (Nov 2, 2024)
7. Zuckerberg "Open Source AI Is the Path Forward" (summary) — https://spyglass.org/zuckerberg-llama-open-source-ai/ (Jul 23, 2024)
8. TechCrunch, Zuckerberg on superintelligence limits — https://techcrunch.com/2025/07/30/zuckerberg-says-meta-likely-wont-open-source-all-of-its-superintelligence-ai-models/ (Jul 30, 2025)
9. OfficeChai, Amodei on open source vs. open weights — https://officechai.com/ai/anthropic-ceo-dario-amodei-explains-why-open-source-ai-isnt-the-same-as-open-source-software/ (Sept 22, 2025)
10. Understanding AI (Tim Lee), Mythos Preview analysis — https://www.understandingai.org/p/why-anthropic-believes-its-latest (Apr 8, 2026)
11. The Hill, Anthropic Mythos/Project Glasswing — https://thehill.com/policy/technology/5824219-anthropic-new-ai-dangerous-public/ (Apr 9, 2026)
12. CFG "Beyond the Binary" (arxiv) — https://arxiv.org/html/2602.19682v1 (published July 2025, arxiv Feb 2026)
13. Dario Amodei Senate testimony URL — https://www.judiciary.senate.gov/download/2023-07-26-testimony-amodei (not retrieved in full)
