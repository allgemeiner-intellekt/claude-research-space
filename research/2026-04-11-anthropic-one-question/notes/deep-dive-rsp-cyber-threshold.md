# Deep Dive: Does RSP v3.0 Contain a Formal Cyber Threshold That Mythos Triggered?

## Question

Does RSP v3.0 (February 2026) contain a formal cyber-relevant deployment threshold that would have governed the Mythos deployment restriction? Specifically: does the "high-stakes sabotage" category cover offensive cyber capabilities, and did the Mythos system card cite this category (or any RSP v3 threshold) as having been triggered?

## Investigation

### Step 1: Read RSP v3.0 for the word "cyber"

The RSP v3.0 PDF (https://anthropic.com/responsible-scaling-policy/rsp-v3-0, effective February 24, 2026) was retrieved in full (51,386 characters of extracted text). A search for the word "cyber" returns **zero occurrences**. The word "offensive" also returns zero occurrences. This is not an omission — it is a deliberate architectural choice. The GovAI analysis (March 17, 2026) confirms this explicitly in a footnote: "Note that cyber operations were not listed as a formal category in the old RSP, but were identified as a capability under 'active assessment'. [They have now been removed entirely.]" Zvi Mowshowitz's RSP v3 analysis (April 3, 2026) is blunter: "Cyber Operations is fully gone. Perhaps because it would pass every test? This is despite it being a core test for both OpenAI and Google."

In the prior RSPs (v2.x), cyber capabilities were under "active assessment" — meaning they were being monitored but had not been formalized into a triggering threshold. In RSP v3.0, even that informal status was dropped. Cyber is not a capability category in v3.0 in any form.

### Step 2: What is "high-stakes sabotage" in RSP v3.0?

The RSP v3.0 capability-threshold table defines "High-stakes sabotage opportunities" as follows (quoted directly from the PDF text):

> "AI systems that are highly relied on and have extensive access to sensitive assets as well as moderate capacity for autonomous, goal-directed operation and subterfuge—such that it is plausible these AI systems could (if directed toward this goal, either deliberately or inadvertently) carry out sabotage leading to irreversibly and substantially higher odds of a later global catastrophe. In the near term, this possibility will likely be most applicable to AI systems that are extensively used within major AI companies, with the opportunity to manipulate how their successor systems are trained and deployed as well as the evidence used to assess their safety."

This definition is about **AI alignment sabotage** — the risk that a model operating inside an AI company could manipulate the training of its successors, corrupt safety evaluations, or take autonomous adversarial actions against its own developers. It is not about, and does not encompass, the model's ability to help external users find and exploit software vulnerabilities. The threat model is internal (AI-on-AI-company), not external (AI-on-third-party-targets).

The RSP v3.0 unilateral commitment Anthropic makes at this threshold is minimal: "We will detail the state of our AI systems' capabilities and propensities, our monitoring practices, and the overall level of risk in our Risk Reports." This is a **documentation obligation**, not a deployment gate. The industry-wide recommendation at this threshold is to "make a strong argument that AI systems will not carry out sabotage leading to irreversibly and substantially higher odds of a later global catastrophe" — but this is explicitly framed as a recommendation to the industry, not a unilateral hard commitment by Anthropic.

### Step 3: What formal mechanism governed the Mythos restriction?

The Mythos "Alignment Risk Update" (https://www.anthropic.com/claude-mythos-preview-risk-report, April 7, 2026) covers the high-stakes sabotage threat model — it is structured around alignment failure modes, not offensive cyber capabilities. The word "sabotage" appears zero times in that document; the word "cyber" appears five times, all in the context of describing Mythos's cybersecurity task performance and its implications for internal monitoring, not as a threshold category that was triggered.

The Mythos system card (https://www.anthropic.com/claude-mythos-preview-system-card, PDF) describes the deployment restriction in terms of cybersecurity capability evaluations: performance on Cybench, CyberGym, and a Firefox 147 browser exploit benchmark. These evaluations showed Mythos could autonomously chain exploits in ways Opus 4.6 could not. But these evaluations are not cited as triggering a formal RSP threshold. The Kingy.ai summary (which provides detailed coverage of the system card's contents) describes the restriction as follows: "This is the first model released under Anthropic's updated Responsible Scaling Policy (RSP) version 3.0, which introduced new risk assessment frameworks and safeguard requirements. The release decision process itself is described in the System Card as more structured than previous iterations, with formal risk reports, updated threat models, and explicit safety thresholds informing whether and how a model can be deployed." This is accurate but imprecise — the system card invokes RSP v3's **process** (Risk Reports, threat model analysis) but does not cite a specific RSP v3 capability threshold as having been crossed.

The restriction operates through RSP v3's new **Risk Reports** mechanism rather than through any binary capability threshold. Under RSP v3.0 Section 3, Anthropic commits to publishing Risk Reports every 3–6 months and to providing a discussion of how a new model's capabilities affect the Risk Report analysis when a significantly more capable model is publicly deployed (or within 30 days for internal deployment). The Mythos system card appears to fulfill the latter obligation. The decision to restrict Mythos to Project Glasswing partners rather than the general public is framed as a judgment call informed by the Risk Report analysis, not a mandatory stop triggered by crossing a threshold. As Zvi notes directly: "There is no pre-deployment gate mechanism here. You can just release things."

### Step 4: Does the Sabotage Risk Report framework constitute a formal deployment gate?

The prior Sabotage Risk Report (for Claude Opus 4.6, March 2026) was Anthropic's first Risk Report under RSP v3.0. It assessed whether Opus 4.6 posed high-stakes sabotage risks and concluded the risk was "very low but not negligible." This was a public documentation of the high-stakes sabotage threat model. It did not function as a deployment gate in the sense that passing or failing it would have automatically stopped or permitted deployment — the RSP v3.0 language is that Anthropic "will detail" its systems' risk posture, not that it must demonstrate a negative before deploying.

The Mythos risk report continues this framework but is titled "Alignment Risk Update: Claude Mythos Preview" — explicitly scoped to alignment risks (the high-stakes sabotage category under RSP v3). The cyber restriction is handled in the system card under a separate cybersecurity evaluations section, which feeds into the deployment decision under the RSP v3 "strong argument" standard but is not itself a threshold trigger.

## Key Findings

- **RSP v3.0 contains no cyber threshold whatsoever.** The word "cyber" appears zero times in the full policy text. Cyber operations were removed from even informal "active assessment" status relative to prior RSPs. (Strong evidence — from primary source text)

- **"High-stakes sabotage" in RSP v3.0 refers to AI-on-AI-company alignment sabotage, not offensive cyber capability.** The definition specifies systems that could manipulate successor training and deployed evidence — an internal alignment risk, not an external cyberattack risk. (Strong evidence — direct quote from policy text)

- **Anthropic's unilateral commitment under the high-stakes sabotage threshold is a documentation obligation only.** The commitment is to detail capabilities in Risk Reports, not to meet a deployment standard. The deployment gate interpretation requires conflating the documentation obligation with a blocking condition. (Strong evidence — from policy text; confirmed by GovAI and Zvi analyses)

- **The Mythos system card does not cite any RSP v3 capability threshold as having been "triggered."** The restriction is framed as a deployment judgment informed by cybersecurity evaluations, made under RSP v3's general "strong argument" framework, not under a formal threshold that was crossed. (Strong evidence — from Kingy.ai comprehensive system card summary and Simon Willison's account)

- **The Mythos "Alignment Risk Update" is scoped to alignment/sabotage risk (RSP v3 category), not to cyber.** It is the RSP v3-mandated Risk Report update for the high-stakes sabotage category. The cyber restriction appears in the system card's separate cybersecurity section. These are two distinct documents addressing two distinct concerns. (Strong evidence — from document titles, structure, and keyword search)

- **RSP v3.0 has no pre-deployment gate mechanism of any kind.** Under RSP v3, the process is: publish Risk Reports, make a "strong argument" for safety, and proceed. Zvi's characterization is accurate: "There is no pre-deployment gate mechanism here. You can just release things." (Strong evidence — from GovAI and Zvi analyses, confirmed by RSP v3.0 Section 3 text)

## Assessment

The essay's central empirical claim holds without qualification: the RSP's formal mechanism did not cause the Mythos deployment restriction, because RSP v3.0 contains no formal cyber threshold at all.

The "high-stakes sabotage" category, while new in RSP v3.0, covers a completely different threat model than the one that motivated the Mythos restriction. Sabotage is about internal AI alignment failure — a model manipulating its own training. The Mythos restriction was motivated by external cyber capability — the model's ability to help (or autonomously conduct) offensive security research and exploit development. These are different threat models, governed by different mechanisms, with different mitigations.

There is one nuance worth noting for the essay: the Mythos restriction was not made *outside* the RSP v3 framework — it was made *within* it, just not by triggering a specific threshold. RSP v3 replaced hard threshold triggers with a judgment-based "strong argument" standard and Risk Reports. Anthropic's decision to restrict Mythos to Project Glasswing is the RSP v3 mechanism functioning as designed: the team assessed cybersecurity risks through formal evaluations, published those in the system card, and made a deployment judgment. The system card explicitly connects the decision to RSP v3's frameworks. But this is importantly different from triggering a formal threshold — it is the exercise of discretion within a policy that replaced mandatory thresholds with mandatory candor.

So the claim should be precise: the RSP's **threshold mechanism** did not cause the Mythos restriction (because there is no cyber threshold to trigger). The RSP's **process framework** (Risk Reports, public documentation, "strong argument" standard) did shape the decision's form and transparency. This is not merely semantic — the distinction between "formal trigger" and "policy-shaped judgment" is exactly what the essay's argument turns on. The claim holds: the restriction reflects genuine safety concern translated into a deployment judgment by people, not a formal mechanism that activated automatically when a capability threshold was crossed.

### Sources

- RSP v3.0 full text: https://anthropic.com/responsible-scaling-policy/rsp-v3-0
- RSP v3.0 announcement blog post: https://www.anthropic.com/news/responsible-scaling-policy-v3
- Mythos Alignment Risk Update: https://www.anthropic.com/claude-mythos-preview-risk-report
- Mythos system card (PDF, CDN redirect): https://www.anthropic.com/claude-mythos-preview-system-card
- GovAI RSP v3.0 analysis: https://www.governance.ai/analysis/anthropics-rsp-v3-0-how-it-works-whats-changed-and-some-reflections
- Zvi Mowshowitz RSP v3.0 deep dive: https://thezvi.substack.com/p/anthropic-responsible-scaling-policy-46a
- Simon Willison on Project Glasswing: https://simonwillison.net/2026/Apr/7/project-glasswing/
- Kingy.ai Mythos system card summary: https://kingy.ai/ai/claude-mythos-preview-system-card-a-comprehensive-summary/
