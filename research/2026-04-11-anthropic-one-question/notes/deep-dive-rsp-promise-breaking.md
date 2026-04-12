# Deep Dive: Did RSP v3.0 Break a Binding Promise?

## Question

The specific question is whether Anthropic's RSP v3.0 (February 2026) constitutes a broken promise — specifically a promise that people relied upon — or merely a revision of a voluntary policy. The underlying question for the report: has the RSP ever formally constrained Anthropic, or has it always left room for Anthropic to do what it wanted?

## Investigation

### 1. The Core Pause Commitment: What v1.0 Actually Said

The RSP v1.0 (September 2023) text is available in full. The pause commitment appears on page 2, highlighted in this passage:

> "Anthropic's commitment to follow the ASL scheme thus implies that we commit to pause the scaling and/or delay the deployment of new models whenever our scaling ability outstrips our ability to comply with the safety procedures for the corresponding ASL."

This appears in the main body of the document, in bold font. The RSP v2.0 executive summary also described the policy as "a public commitment not to train or deploy models capable of causing catastrophic harm unless we have implemented safety and security measures that will keep risks below acceptable levels."

However, even in v1.0, there was a modification clause embedded in the Procedural Commitments (Section on "Update Process"):

> "However, in a situation of extreme emergency, such as when a clearly bad actor (such as a rogue state) is scaling in so reckless a manner that it is likely to lead to imminent global catastrophe if not stopped (and where AI itself is helpful in such defense), we could envisage a substantial loosening of these restrictions as an emergency response."

This is significant: the loosening provision in v1.0 was framed as applying only in extreme emergencies involving rogue states causing imminent catastrophe — not ordinary competitive dynamics. The threshold was extremely high and the framing made it clear that the default was the pause commitment.

### 2. The V2.0 Escape Clause: The Real Genealogy

RSP v2.0 (October 2024) contained a footnote (footnote 18 in the document) that substantially widened the escape clause. This footnote, cited by Zvi as "section 7.1.7" (his numbering), reads:

> "It is possible at some point in the future that another actor in the frontier AI ecosystem will pass, or be on track to imminently pass, a Capability Threshold without implementing measures equivalent to the Required Safeguards such that their actions pose a serious risk for the world. In such a scenario, because the incremental increase in risk attributable to us would be small, we might decide to lower the Required Safeguards. If we take this measure, however, we will also acknowledge the overall level of risk posed by AI systems (including ours), and will invest significantly in making a case to the U.S. government for taking regulatory action to mitigate such risk to acceptable levels."

Key differences from v1.0: First, v1.0's escape was limited to "rogue states causing imminent global catastrophe" whereas v2.0's escape applies whenever "another actor" passes a threshold "without implementing equivalent safeguards." Second, v2.0's escape still required a condition of "serious risk to the world" — not merely competitive pressure. Third, v2.0's escape was still buried in a footnote, not the main text. The structural move from v2.0 to v3.0 was to promote this logic from a footnote escape to the primary organizing principle of the entire document.

GovAI (Williams and Freund, March 2026) correctly identified the lineage: "Under the old RSP, Anthropic started from a high level of mitigations and would only lower them if competitors weren't adopting similar ones. Under the new RSP, Anthropic starts from a lower level and will only adopt stronger ones if other companies do." This reversal of the default — from binding unless competitors are bad enough, to aspirational unless competitors match — is the operative change.

### 3. Evan Hubinger's 2023 Characterization

Hubinger (Alignment Forum username "evhub") posted "RSPs are pauses done right" on October 14, 2023 — the same month as v1.0 — as an Anthropic employee (he discloses his affiliation in the disclaimer). The post argues RSPs are superior to pause advocacy precisely because they provide concrete conditions for when to stop. He did not, in that post, make the specific "big bold font" claim about the pause commitment.

The "big bold font" quote comes from a later comment exchange documented by Oliver Habryka. Someone criticized the RSP for being unclear about pause conditions. Hubinger responded (across multiple comments):

> "It's hard to take anything else you're saying seriously when you say things like this; it seems clear that you just haven't read Anthropic's RSP. The conditions under which Anthropic commits to pausing in the RSP are very clear. In big bold font on the second page it says: Anthropic's commitment to follow the ASL scheme thus implies that we commit to pause the scaling and/or delay the deployment of new models whenever our scaling ability outstrips our ability to comply with the safety procedures for the corresponding ASL. ...the security conditions could trigger a pause all on their own, and there is a commitment to develop conditions that will halt scaling after ASL-3 by the time ASL-3 is reached. ...This is the basic substance of the RSP: I don't understand how you could have possibly read it and missed this. I don't want to be mean, but I am really disappointed in these sort of exceedingly lazy takes."

Habryka's account: "This was, in my experience, routine." He describes Hubinger's response as representative of how Anthropic employees generally engaged when the RSP's binding nature was questioned.

After RSP v3 was released, Hubinger continued to defend his original position — arguing he was merely describing where the lines were, not claiming they were permanent. Habryka and Zvi find this unpersuasive given the plain reading of "exceedingly lazy takes."

### 4. Oliver Habryka's Account: Where and How Specific

Habryka's account of the "more than a dozen occasions" is published in the LessWrong comment thread on the RSP v3 post (February 24, 2026), in a comment with 330 points (extremely high for LW) that was subsequently quoted in Zvi's April 1 post. The full relevant passage:

> "Yes, Anthropic employees on more than a dozen occasions told me that the RSP binds them to a mast. I had many very explicit conversations with many Anthropic employees about this, because I was following up on what I thought was Anthropic violating what I perceived to be a promise to not push forward the state of AI capabilities, which many employees disputed had happened. In almost every conversation I had with Anthropic employees about this, they explicitly said that in contrast to any potential vague promises that were made about not pushing forward the state of capabilities, that the RSP was very much such an explicit commitment, and I should absolutely hold Anthropic accountable to the..."

The comment continues but is truncated in the scraped version. Habryka elaborates in the same thread:

> "At various events I was at, and conversations I had with people, Anthropic employees told me they were aiming to achieve robustness from state-backed hacking programs, and that they were ready to pause if they could not achieve that (as the RSP 'committed' them to such things)."

Habryka also notes that Holden Karnofsky was the exception — Karnofsky consistently communicated a weaker version of the commitment, consistent with his later role drafting v3.0.

The source is the LessWrong RSP v3 post comment thread: https://www.lesswrong.com/posts/HzKuzrKfaDJvQqmjh/responsible-scaling-policy-v3?commentId=WriWrtXL6oGqdchF6

### 5. Drake Thomas's Admission: The Most Significant Internal Acknowledgment

Drake Thomas, identified as an Anthropic employee, responded to a pointed question from Seán Ó hÉigeartaigh in the same LessWrong thread. Ó hÉigeartaigh asked:

> "At what point was it decided that the previous commitments were 'subject to a favourable environment' and not 'firm commitments', and was this communicated across staff? The whole point of commitments is an expectation of being able to rely on them when the environment is not favourable, not just when they're easy to make. It also seems clear at this point that these commitments were presented as harder than this, and used by Anthropic/their staff to (a) dismiss and undermine critics (b) in recruitment of safety-concerned talent (c) in arguing for voluntary if-then commitments at a time when there was more government appetite for considering harder regulation."

Drake Thomas replied with a partial defense but then conceded:

> "All that said: I think the vibes of Anthropic and much of the v1.0 text and many of its employees' statements around the RSP circa 2023 and 2024 presented a much more ironclad view of these commitments than is reflected in RSP v3 (and much more than I now think made sense), and I think this reflected pretty poor judgement and merits criticism. (I count myself among the Anthropic employees who acted poorly in hindsight here, though AFAIK Holden has been consistent and reasonable on this since the beginning.)"

This is the most direct internal acknowledgment that the earlier presentation was misleading. Thomas also disclosed:

> "I know of early discussion around something like an RSP v3 regime widely accessible to Anthropic staff as early as January 2025 and even wider visibility into drafts of something pretty similar to this RSP for at least the past 3 months, though again I don't think it's like there was ever some formal conception that this was Forbidden which had to change at a discrete point."

This confirms the shift had been planned internally well before it was communicated externally.

Additionally, in another exchange, Thomas acknowledged that Anthropic employees "acting poorly" extended to himself personally, not just institutional messaging. His defense (that there was no formally secret internal RSP with "even more footnotes") is a weak defense: the point is not that Anthropic had secret contradictory documents, but that the public presentation was misleading.

Source: https://www.lesswrong.com/posts/AkzauoTt2Lwn2yAvj?commentId=DFbTE3BLPyNanx4rQ (Zvi's LW cross-post thread) and the main RSP v3 thread.

### 6. Jared Kaplan's Explanation

Jared Kaplan, identified as Anthropic's Chief Science Officer, stated publicly (quoted in Zvi's post):

> "We felt that it wouldn't actually help anyone for us to stop training AI models. We didn't really feel, with the rapid advance of AI, that it made sense for us to make unilateral commitments… if competitors are blazing ahead. ...I don't think we're making any kind of U-turn."

This is Anthropic's most direct explanation for the change, and it is simultaneously a confirmation that the prior commitments were understood by leadership as unilateral (they now reject unilateral commitments) and a denial that this constitutes a U-turn (which is contested by observers). The "competitors are blazing ahead" rationale precisely matches the escape clause logic that was buried in v2.0's footnote 18 and is now the primary organizing principle of v3.0.

### 7. The Prediction Market

Oliver Habryka created a Manifold Markets prediction market in late October 2023 titled: "Will Anthropic's RSP security commitments (as of Oct. 28 2023) cause them to pause scaling for at least one month?"

URL: https://manifold.markets/OliverHabryka/will-anthropics-rsp-security-commit

The market shows 11% probability as of current date (April 2026), down from higher levels, with resolution criteria: "This question will resolve based on whatever the consensus answer between me and Evan (Hubinger) is whether Anthropic did indeed delay scaling or developing more powerful systems for at least one month as a result of those security commitments." The market is set to resolve whenever Anthropic reaches ASL-4 or when Habryka and Hubinger agree the question won't really change anymore.

The current 11% is actually higher than the "~0%" cited in the survey. But the market creator himself — Habryka — has predicted NO, and after RSP v3's release changing the commitment structure, the market's resolution criteria are now contested (Habryka's comment: "If the new security commitments seem approximately strictly stronger than present ones, then I would resolve it as 'Yes'... If they change in a bunch of different ways that aren't strictly stronger, I would resolve it as 'No'"). Given that RSP v3 weakened future security commitments while maintaining current ASL-3 ones, resolution as NO seems likely.

The Metaculus mirror market "Will OpenAI, DeepMind, or Anthropic announce a pause on large training runs for safety reasons, before 2026?" resolved NO.

### 8. Holden Karnofsky's Position: The Outlier Who Shaped v3.0

Karnofsky is described by both Habryka and Thomas as having been "consistent and reasonable" — i.e., consistently held a weaker view of the RSP's binding nature even before v3.0. His post on "If-Then Commitments for AI Risk Reduction" (cited in the thread) explicitly discussed "escape clauses" and presented the theory of change as running through policy and regulation, not unilateral action.

Karnofsky was "not at Anthropic when the commitments were made" (Zvi). He led development of v3.0. This creates a structural explanation: the person who later rewrote the RSP never held the strong interpretation that the RSP was binding.

The Sam Bowman (Anthropic, identified as such in the thread) endorsement of the davidad comment ("Voluntary commitments to AI slowdowns were a nice idea in 2024 when it was plausible... In the strategic landscape of 2026, racing is the right move") further indicates that the RSP shift reflects genuine changes in internal views, not just messaging.

### 9. GovAI's Assessment

GovAI (Sophie Williams, Jonas Freund, March 5, 2026) provides the most careful third-party analysis. Key assessments:

- "Our initial reaction to the update was rather negative. We were particularly concerned about the pause commitment being dropped, mainly because it makes it more likely Anthropic will deploy models that pose unacceptable risks."
- "Despite the escape clause, Anthropic gave the impression that its pause commitment was binding. At least that's how many appear to have interpreted the commitment, and Anthropic failed to correct that impression."
- "We're less concerned about this change than others, partly because we already thought it was unlikely Anthropic would actually pause, and partly because the commitment has always been conditional due to the escape clause."
- "On balance, we think it's better to be honest about constraints than to keep commitments that won't be followed in practice."

GovAI's framing of "three options" is analytically useful: (1) keep the pause and actually pause when unsafe, (2) keep the pause and use the escape clause to proceed anyway, (3) drop the pause and be transparent. They argue option 3 is preferable to option 2 — but their admission that option 2 was already the de facto situation is crucial. It confirms that the escape clause was always available to be invoked.

Source: https://www.governance.ai/analysis/anthropics-rsp-v3-0-how-it-works-whats-changed-and-some-reflections

### 10. Anthropic's Response to the "Broken Promise" Framing

Anthropic has not used the words "broken promise" in its official communications. In the RSP v3.0 blog post, Karnofsky frames the change as recognizing that prior commitments were not well-suited to the actual goal (achieving industry coordination through regulation). Kaplan explicitly denies a "U-turn."

The only internal acknowledgment that something went wrong is Drake Thomas's LW comment, which is notable as an Anthropic employee speaking informally (and which explicitly applies criticism to himself).

Notably, Anthropic released a v3.1 update on April 2, 2026 (one day after Zvi's post) that added one clarification directly responsive to criticism: "We now clarify that, even if not required by the RSP, we remain free to take measures such as pausing the development of our AI systems in any circumstances in which we deem them appropriate." This is a subtle but significant addition — it acknowledges that Anthropic can still voluntarily pause, even if not required to do so. This is responsive to the critique that v3.0 seemed to eliminate any pause scenario.

## Key Findings

- **RSP v1.0's pause commitment was stated unconditionally in the main body text ("in big bold font"), with only an extreme-emergency loosening provision (rogue state causing imminent catastrophe).** [Strong evidence; primary source: RSP v1.0 PDF]

- **RSP v2.0 added a competitor-based escape clause as a footnote (footnote 18 in the October 2024 document), which allowed lowering Required Safeguards if another actor passed a threshold without equivalent safeguards.** [Strong evidence; primary source: RSP v2.0 PDF]

- **RSP v3.0 inverted the default: competitor-conditional commitments became the organizing structure, and the pause commitment was dropped entirely.** [Strong evidence; primary source: RSP v3.0 text, GovAI analysis]

- **Multiple Anthropic employees — including Evan Hubinger — actively and aggressively promoted the "binding pause" interpretation to outside critics, dismissing questions about the pause conditions as evidence of not having read the RSP.** [Strong evidence; primary source: Habryka's account with Hubinger quote in the LW thread]

- **Oliver Habryka received explicit verbal assurances from Anthropic employees "on more than a dozen occasions" that the RSP "binds them to a mast."** [Moderate evidence; primary source: Habryka's LW comment, corroborated by Hubinger's public written statement]

- **Drake Thomas (Anthropic) explicitly acknowledged that "the vibes of Anthropic and much of the v1.0 text and many of its employees' statements around the RSP circa 2023 and 2024 presented a much more ironclad view of these commitments than is reflected in RSP v3... and I think this reflected pretty poor judgement and merits criticism."** [Strong evidence; primary source: Thomas's LW comment]

- **Jared Kaplan (Anthropic CSO) stated the company no longer believes "it made sense to make unilateral commitments... if competitors are blazing ahead."** [Strong evidence; primary source: quoted in Zvi's post, attributed to public statement]

- **Holden Karnofsky, who led v3.0's development, was the one Anthropic senior figure who had consistently held a weaker interpretation of the RSP's binding nature even before v3.0.** [Moderate evidence; derived from multiple accounts in the LW thread]

- **The Manifold prediction market created by Habryka, with Hubinger as co-resolver, is at ~11% for the RSP causing a month-long pause — effectively confirming market consensus that it never will.** [Strong evidence; primary source: Manifold market URL]

- **Seán Ó hÉigeartaigh specifically named three harms from the misleading presentation: (a) dismissing critics, (b) safety-concerned talent recruitment, (c) influencing policy discussions toward voluntary frameworks.** [Moderate evidence — the claim is Ó hÉigeartaigh's, but Drake Thomas did not dispute the factual accuracy of points a-c, only the framing]

- **The RSP v3.1 update (April 2, 2026) added language clarifying that Anthropic can still voluntarily pause even if not required to, which is responsive to the criticism but does not walk back the substance of v3.0.** [Strong evidence; primary source: Anthropic RSP updates page]

## Assessment

The evidence establishes that what happened was not merely "Anthropic changed a voluntary policy" but something more significant: **Anthropic made specific representations, both in writing and verbally, that a large number of people in the AI safety community relied on, and then walked them back while simultaneously denying that any U-turn had occurred.**

The case for "broken promise" is strong on four grounds:

**First, the text itself.** RSP v1.0 stated the pause commitment in the main body in unambiguous language, with an escape clause limited to rogue-state-induced global emergency. The v2.0 escape clause was a footnote, not the main text. Presenting a footnote-level exception as the document's primary structure (as v3.0 does) is not a natural extension of the document's plain meaning.

**Second, verbal assurances.** Habryka's account of "more than a dozen occasions" of explicit verbal assurances is corroborated by the documented written behavior of at least one Anthropic employee (Hubinger) who publicly attacked skeptics as not having read the document. The verbal and written pattern is consistent and mutually reinforcing.

**Third, the internal acknowledgment.** Drake Thomas's LessWrong comment is internally significant: a senior Anthropic employee, speaking in his own name, acknowledged the earlier presentation was misleading and constituted "pretty poor judgement." This is not standard PR language — it is a specific person taking personal responsibility for a specific failure.

**Fourth, the strategic reliance.** Ó hÉigeartaigh's three-part enumeration of how the misleading presentation was relied on — to dismiss critics, recruit talent, and influence policy discussions — is not contradicted by any Anthropic employee in the thread. Drake Thomas's response addressed the question of "when was it formally decided" but did not deny the reliance pattern. GovAI independently raised the reliance question.

**The case for "merely a policy revision" rests on two arguments:**

One, the RSP always had an update process, and Anthropic reserved the right to revise it with board approval. This is true as a formal matter, but the escape provisions built into earlier versions had different thresholds than what v3.0 effectively implements. The formal right to revise is not equivalent to having communicated that competitive dynamics would be the trigger.

Two, Karnofsky always held the weaker interpretation, and his position is now the company's official position. This is true, but it means that Karnofsky's view was not the view communicated by most Anthropic employees to outside observers, which is precisely the problem.

**Where genuine uncertainty remains:** Was the stronger interpretation of the RSP held by Hubinger, Thomas, and others a genuine belief that was later abandoned due to changed circumstances, or was it always a strategic posture that Karnofsky's faction knew was unsustainable? The Drake Thomas disclosure that draft v3.0-style documents were circulating internally by January 2025 — roughly 15 months before release — is relevant here. If Anthropic leadership was already reconsidering the model internally by early 2025, why were employees still actively defending the strong interpretation in public through the period covered by GovAI's "escape clause already made it conditional" assessment?

The most charitable reading: a genuine internal disagreement existed between the Karnofsky interpretation (always weaker) and the Hubinger/Thomas interpretation (stronger at the time, later regretted), and the company did not explicitly adjudicate or communicate this disagreement externally. The result was external audiences receiving the stronger interpretation as Anthropic's position.

The least charitable reading: Anthropic leadership knew the stronger interpretation was unsustainable, benefited from outside actors treating it as binding (for talent, policy, and reputational reasons), and delayed the revision until competitive conditions made it necessary.

**The most defensible verdict:** The RSP never had the ironclad, unconditional force that many people believed it to have based on Anthropic's communications. The escape clauses were always present. But the gap between the document's formal escape provisions and the way Anthropic employees communicated about those provisions was large enough — and the reliance was significant enough — that calling v3.0 a simple "policy update" understates what happened. Anthropic made representations that implied the strong interpretation, those representations were used in ways that benefited Anthropic, and v3.0's change imposed costs on those who had relied on the strong interpretation. The self-regulation experiment, as Zvi notes, is over. Whether it was conducted honestly is a separate question from whether it was a good idea.
