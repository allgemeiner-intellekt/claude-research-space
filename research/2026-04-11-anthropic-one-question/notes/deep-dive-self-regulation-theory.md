# Deep Dive: Self-Regulation Theory and the RSP

## Question

Does the track record of industry self-regulation in other domains predict whether Anthropic's RSP can credibly constrain behavior — and what specific institutional features distinguish binding self-regulation from cheap talk?

## Investigation

### 1. Credible Commitment Theory: What Makes a Voluntary Commitment Credible?

The canonical theoretical apparatus comes from two traditions. Schelling's *The Strategy of Conflict* (1960, Harvard University Press) established that precommitment is credible when it structurally removes the committing party's future ability to defect. Odysseus's binding to the mast is the prototype: the sirens cannot be resisted by willpower alone, so the mast does not merely communicate intent but physically eliminates optionality. The cost structure of the commitment device is what makes it informative — not the declaration.

North and Weingast's "Constitutions and Commitment" (1989, *Journal of Economic History*) formalized this in the institutional economics tradition. They analyze 17th-century England: the Crown's borrowing costs fell dramatically after the Glorious Revolution established parliamentary supremacy and an independent judiciary, because creditors could now sue the Crown in court. What changed was not the King's stated intentions but the *structural inability* to renege without catastrophic institutional consequences. The constitutional settlement of 1689 created external enforcement — Parliament could remove the King — that converted a weak, modifiable promise into a hard constraint. North and Weingast's central insight: credibility requires that the commitment cost to break exceeds the cost to keep, AND this cost structure is observable. Reputation helps but is insufficient; institutions must impose real penalties for defection.

Kydland and Prescott's "Rules Rather than Discretion" (1977, *Journal of Political Economy*, Nobel Prize 1994) established the time-inconsistency problem: even a benevolent policymaker, without binding constraints, will produce suboptimal outcomes because future-self's incentives diverge from present-self's announcements. The solution is institutional constraints — constitutional rules, central bank independence, debt ceilings — that remove future discretion. This is the same problem Anthropic faces: even a sincerely safety-motivated Anthropic today cannot bind a future Anthropic under competitive pressure, unless external mechanisms remove that future discretion.

Fearon (1997, *Journal of Conflict Resolution*) distinguishes two credibility mechanisms: "tying hands" (generating audience costs through public commitment — the cost of backing down rises because the audience will punish you) and "sinking costs" (paying upfront, non-recoverable costs that signal genuine intent). Both are relevant to the RSP, but neither, alone, is sufficient: tying hands requires an audience that can actually punish; sinking costs require costs that cannot be rationalized away as mere investment.

Crawford and Sobel (1982, *Econometrica*) showed that when interests conflict, cheap talk — costless, non-binding communication — cannot achieve full information transmission. A "babbling equilibrium" always exists where the communication conveys no information. Corporate safety pledges satisfy every condition for cheap talk: they cost nothing to issue, nothing to retract, and carry no enforcement mechanism. This is not a failure of sincerity; it is a structural feature of the game.

**The four criteria for credibility, drawn from this literature:**

1. **Costly signaling**: The commitment must impose observable, non-recoverable costs that a non-committed actor would not pay. (Spence 1973, *QJE*)
2. **External enforcement**: A third party with coercive power can punish defection — neither the committer nor their allies control the enforcement mechanism.
3. **Reputation stakes**: Defection creates durable reputational damage that cascades across multiple relationships, raising the effective cost of reneging.
4. **Unilateral modification foreclosed**: The committer lacks the structural ability to rewrite the terms without activating the enforcement mechanism. (This is what makes constitutions, contracts, and insurance different from policy statements.)

### 2. Mapping the Four Criteria onto the RSP

**Costly signaling — Weak to Moderate.** The RSP has imposed real costs. Roughly 8% of Anthropic headcount was on security-adjacent work by mid-2024 (Anthropic's own "Reflections on our RSP," May 2024). The ASL-3 infrastructure buildout required substantive investment. The Constitutional Classifiers were directly RSP-motivated. But the key question is whether these costs constrain future behavior or are merely sunk investments that now travel with the company regardless of whether the RSP is maintained. RSP v3.0 answered this definitively: Anthropic rewrote its pause commitment out of the policy. The costs incurred under v1.0 and v2.0 were not recoverable threats — they were investments that Anthropic made anyway. The sunk costs did not bind future behavior; they were compatible with the future rewrite.

**External enforcement — Absent.** The RSP's formal governance consists of board approval and Long Term Benefit Trust (LTBT) consultation for changes (RSP v1.0, 2023). But the LTBT is an Anthropic-affiliated body, not an independent counterparty. The board that "approved" v3.0 approved it on Anthropic's timetable and in response to Anthropic's recommendation. There is no third party with standing to sue, penalize, or block Anthropic if it modifies the RSP. METR's external reviews of Risk Reports exist under RSP v3.0, but METR can only evaluate and publish findings — not compel any action. The GovAI analysis (Williams and Freund, March 2026) notes that Risk Reports without a pause commitment are weaker enforcement mechanisms than pause + reports. Stelling et al.'s comparative assessment of 12 frontier safety frameworks (arXiv:2512.01166, December 2025) gives Anthropic the top score of 34% — but notes "vague commitments that make it difficult to predict company decisions, assess whether planned responses are adequate, or determine whether commitments have been kept." Even the best framework in the field scores below 35% on established risk management criteria.

**Reputation stakes — Moderate.** The RSP created a real reputational investment. Anthropic's identity as a safety-focused lab is embedded in its talent pipeline, its investor story, and its public positioning. The defection from the pause commitment in v3.0 generated genuine negative reactions from Evan Hubinger, Oliver Habryka, Zvi Mowshowitz, GovAI, METR (Chris Painter: "Anthropic believes it needs to shift into triage mode"), and even named Anthropic employees. Drake Thomas (Anthropic) publicly acknowledged: "the vibes of Anthropic and much of the v1.0 text and many of its employees' statements around the RSP circa 2023 and 2024 presented a much more ironclad view of these commitments than is reflected in RSP v3." This is a real reputational cost. But prediction markets on whether Anthropic's commitments will ever force a pause moved to approximately 0% after v3.0 — suggesting the market treats the reputational damage as resolved without behavioral change.

**Unilateral modification foreclosed — Absent.** This is the sharpest failure. The RSP v3.0 was written, approved by Anthropic's board (on Anthropic's own schedule), and published by Anthropic. RSP v1.0 was replaced by v2.0, then v2.1, v2.2, v3.0, and v3.1 — six versions in two and a half years. The pause commitment that was described by Anthropic employees "in big bold font on the second page" was rewritten out of existence without triggering any external enforcement. This is the precise definition of a commitment that fails the unilateral-modification test: the committer retained full discretion to revise the terms.

**Summary assessment against the four criteria:** The RSP satisfies costly-signaling weakly and reputation-stakes moderately. It fails external enforcement and unilateral-modification-foreclosed entirely. In standard credible commitment theory, an actor who retains full discretion to modify their stated constraints is not credibly committed. The RSP is, in the vocabulary of Kydland-Prescott, a policy statement (discretion) rather than a rule (commitment).

### 3. Industry Track Record: Five Comparison Cases

**Case A: Chemical Industry — Responsible Care (1985–present)**

Responsible Care was launched by the Canadian Chemical Producers Association in 1985, one year after Bhopal, and adopted by the U.S. Chemical Manufacturers Association in 1988. Post-Bhopal, the chemical industry faced a genuine threat: legislative action that would impose strict regulatory requirements. Responsible Care was explicitly designed as a pre-emptive self-regulatory move to demonstrate seriousness and forestall harder regulation.

The most-cited academic study: King and Lenox, "Industry Self-Regulation Without Sanctions: The Chemical Industry's Responsible Care Program" (*Academy of Management Journal*, 43:5, August 2000, 1,636 citations). Their finding, based on panel data from U.S. chemical firms, is damning: Responsible Care membership had no positive effect on environmental performance. Worse, non-members improved faster than members. King and Lenox concluded that the program suffered from "organizational opportunism" — firms joined for reputational benefits without actually improving practices, and the lack of third-party verification or sanctions meant there was no mechanism to screen out opportunistic joiners. The program was "a club that welcomes anyone, charges no initiation fee, and enforces no standards."

A follow-up by Gamper-Rabindran and Finger (*Journal of Regulatory Economics*, 43:1, 2012) found that Responsible Care membership was associated with reduced pollution only after 1997, when the program added independent verification requirements — i.e., when it began to resemble actual third-party enforcement. Li, Khanna, and Vidovic (2014; 2018) showed that third-party certification (introduced in 1997) significantly reduced accident rates, while pre-certification membership had no detectable effect. The pattern is consistent: the voluntary commitment without verification did nothing; the same nominal commitment with verification and external checking did something.

Gunningham (1995, "Environment, Self-Regulation, and the Chemical Industry," *Law & Policy*) emphasized that Responsible Care's effectiveness also depended on the "shadow of hierarchy" — the latent threat of regulatory action that made membership non-trivially costly. When regulatory pressure relaxed, member behavior regressed. The program is most accurately described as industry capture of the regulatory agenda: it prevented stricter regulation while delivering marginal improvement only under conditions of strong external pressure.

**Structural lessons for the RSP**: The key variable that distinguished Responsible Care's pre-1997 uselessness from its post-1997 partial effectiveness was third-party verification with real auditing access. The RSP has METR reviews of Risk Reports and government AISI evaluations — these are analogous to the 1997 Responsible Care improvement. But unlike the chemical industry's certification system, METR and AISI cannot impose consequences: they can only publish. The RSP is structurally closer to pre-1997 Responsible Care (membership without sanctions) than to the post-1997 version.

**Case B: Nuclear — INPO (1979–present)**

The Institute of Nuclear Power Operations was created in 1979, weeks after Three Mile Island, by the nuclear utilities themselves. The mechanism that made it work is analytically crucial: Price-Anderson Act creates joint liability among U.S. nuclear operators. A catastrophic accident at any plant creates claims that the entire industry (via an insurance pool) must satisfy. This is a structural internalization of externalities — each plant's recklessness imposes direct, measurable financial costs on all other plants. INPO is the collective response to this incentive.

The Devanney analysis (Substack, February 2025) identifies the key feature: INPO inspectors have "skin in the game" because the cost of a major accident falls on their own principals. INPO is "in theory voluntary; but it would be nearly impossible to obtain insurance for a US plant that was not a member of INPO." The voluntary commitment is backed by an insurance market that makes non-membership prohibitively expensive — which is functionally equivalent to mandatory participation.

INPO's measurable effects are substantial. Capacity factors in the U.S. nuclear industry rose from approximately 60% in the late 1970s to above 90% by the 1990s. Refueling outage durations fell by roughly half. No U.S. commercial nuclear plant has experienced a core-damage accident since TMI. The contrast with international benchmarks (Chernobyl, Fukushima — both lacking INPO-equivalent structures) is instructive.

The True North analysis (Landrey, June 2025) emphasizes INPO's dynamic standard-setting: plants rated INPO-5 are forced to shut down, and plants must demonstrate continuous improvement to maintain top ratings. INPO sets and raises the bar rather than merely verifying a static minimum. This is the "race to the top" dynamic that voluntary programs rarely achieve.

**Why INPO worked:** (1) Structural internalization of externalities via Price-Anderson joint liability; (2) Insurance pricing linked to INPO ratings, creating a market signal with real financial stakes; (3) Inspector expertise (former plant operators, not paper-pushers); (4) Real sanctions (INPO-5 = cannot get insurance = forced shutdown); (5) Shared ownership of the problem — members inspect each other knowing that a peer's accident is their financial problem.

**Structural lessons for the RSP**: The RSP is missing every one of these mechanisms. There is no joint liability among AI labs — an Anthropic accident does not impose direct financial costs on OpenAI or Google DeepMind. There is no insurance pricing linked to RSP compliance. There are no inspectors with skin in the game (METR reviews RSP Reports but has no financial exposure to the outcomes). There are no real sanctions — Anthropic cannot be forced to suspend operations by any RSP mechanism. The RSP is structurally incomparable to INPO.

**Case C: Finance — Basel Accords (1988–present) and Pre-2008 Risk Management**

The Basel Accords are often cited as evidence that international voluntary standards can work, but the history is more complicated. Basel I (1988) and Basel II (2004) were formally non-binding guidelines from the Basel Committee on Banking Supervision, a body with no direct enforcement authority. Their effectiveness derived entirely from domestic regulators (the Fed, Bank of England, ECB, BaFIS) incorporating them into binding national law. The "voluntary" international standard was implemented through mandatory domestic regulation — a two-step process in which soft law triggers hard law.

Pre-2008 risk management frameworks under Basel II are the definitive case study in voluntary commitment failure in finance. Banks adopted internal risk models under Basel II's "IRB approach" — regulatory blessed frameworks that allowed them to calculate their own capital requirements. This created an extraordinary conflict of interest: the regulated entities chose their own risk models, subject to regulatory review but using proprietary methodology regulators could not fully audit. The result was systematic underestimation of tail risk. The Benink analysis (2020, *Journal of Risk and Financial Management*) documents that capital ratios in 2008, while technically Basel-compliant, were "at historically low levels" — banks had used model flexibility to minimize capital requirements.

The critical observation: banks made "voluntary" disclosures in their annual reports about their risk management practices, all of which described sophisticated, prudent approaches to risk. None predicted the 2008 collapse. The disclosures were cheap talk in the Crawford-Sobel sense: they conveyed no information because firms had strong incentives to project safety regardless of actual practices.

Basel III (2010, post-crisis) strengthened requirements significantly, but the crucial change was reduced model flexibility — banks lost the ability to use their own models for key risk categories, replacing discretion with rules. This is the Kydland-Prescott lesson applied to banking: the solution to time-inconsistent risk management is rules rather than discretion, specifically rules that remove the regulated entity's ability to choose favorable model assumptions.

**Structural lessons for the RSP**: Basel pre-2008 is the direct analogue for "voluntary commitments within a competitive industry with no external enforcement." The AI labs' self-assessments of their own model capabilities are structurally identical to banks' self-assessment of their own risk: the entity with the most information also has the strongest incentive to minimize the reported risk. The solution — external audits with genuine access, reduced self-assessment authority — is precisely what the Brundage et al. "Frontier AI Auditing" paper (arXiv:2601.11699, January 2026) recommends: AI Assurance Levels with rigorous third-party verification and deep, secure access to non-public information.

**Case D: Technology — Platform Trust & Safety and Privacy Self-Regulation**

The EU Code of Practice on Disinformation (2018) was signed by Google, Facebook, Twitter, and Mozilla as a voluntary self-regulatory commitment to counter disinformation. Academic analysis (Zvozdetska, 2021, *Mediaforum*) concludes that "self-regulation was the first logical and necessary step, but few stakeholders were fully satisfied with the process or its outcome." The EU's response was the Digital Services Act (2022), which converted voluntary commitments into binding obligations with fines up to 6% of global revenue. This is the standard pattern: voluntary commitment → demonstrated inadequacy → binding regulation.

The analogous trajectory in privacy: COPPA (1998) was the outcome of demonstrated inadequacy of voluntary privacy commitments by children's platforms; GDPR (2018) followed documented failures of tech self-regulation in Europe. The Coggins et al. analysis (arXiv:2509.24394, September 2025) applied the same affordance methodology to OpenAI's Preparedness Framework v2 and found that it "encourages deployment of systems with 'Medium' capabilities for unintentionally enabling 'severe harm'" (defined as more than 1,000 deaths or $100B in damages) and "allows OpenAI's CEO to deploy even more dangerous capabilities." The gap between what is said and what is actually allowed is large and structurally predictable.

The Yew and Judge paper (EAAMO 2025, "Anti-Regulatory AI") offers the sharpest critique: AI safety practices — evaluations, alignment techniques, open-source releases — can function as "mechanisms of change that direct regulatory focus towards industry-controlled voluntary standards and self-governance," precisely the strategy the chemical industry deployed with Responsible Care. In this reading, voluntary safety frameworks are not genuine attempts at constraint but strategic moves to preempt harder regulation by demonstrating apparent seriousness.

**Structural lessons for the RSP**: Platform self-regulation shows the consistent trajectory: voluntary commitment → partial compliance → external pressure → conversion to mandatory rules. The RSP is currently in the "voluntary commitment" phase. The EU AI Act's GPAI Codes of Practice and elements of California SB-53 (explicitly influenced by the RSP, per Anthropic's v3.0 announcement) represent early stages of the conversion to mandatory rules. Whether that conversion happens fast enough to matter for the next generation of models is an open question.

**Case E: Pharmaceuticals — Clinical Trial Standards Before FDA Mandates**

Pre-FDCA pharmaceutical self-regulation (before the 1938 Food, Drug, and Cosmetic Act) consisted of voluntary industry standards that were demonstrably inadequate until sulfanilamide killed over 100 people, forcing congressional action. The Kefauver-Harris Amendment (1962), requiring proof of efficacy, followed thalidomide. The pattern is consistent: voluntary pharmaceutical standards sufficed only when the technology was insufficiently powerful to cause mass harm; as potency increased, voluntary standards failed, and catastrophe prompted mandatory regulation.

The parallel for AI is structurally exact: voluntary standards may be adequate when model capabilities are insufficient to cause mass harm (ASL-2, all models pre-2025), but become inadequate as capabilities cross thresholds where deployment errors could have catastrophic consequences (ASL-3 and beyond). The question is whether Anthropic's RSP creates adequate mandatory-equivalent constraints before a capability-triggered catastrophe, or whether it functions like pre-1938 pharma self-regulation — adequate for a low-capability era, failing precisely when capabilities become genuinely dangerous.

### 4. Mechanism Design: What Kind of Constraint Is the RSP?

In mechanism design, the designer creates rules that align agents' incentives with the designer's objective function. The RSP claims to be such a mechanism: if capabilities exceed a threshold, Anthropic will pause. The mechanism design question is whether the RSP actually achieves this incentive alignment, or whether Anthropic retains too much discretion for the mechanism to function as specified.

Consider the four comparators the assignment proposes:

**(a) Constitution**: Hard to amend, requires supermajority, often requires ratification outside the original drafting body. The RSP fails this test entirely: it is amended by Anthropic's leadership, approved by Anthropic's board, with LTBT "consultation" (not veto). The RSP has been amended six times in under three years, including a fundamental restructuring that eliminated its central commitment. A constitution that can be rewritten by the party it constrains in response to competitive pressure is not a constitution — it is a policy statement.

**(b) Contract**: Enforceable by a counterparty who did not draft the terms and who has legal standing to compel compliance. The RSP has no counterparty with enforcement rights. METR's role is advisory. Government AISI evaluations are informational. Anthropic's customers have no rights derived from the RSP. No court has jurisdiction over RSP compliance. The RSP is not a contract.

**(c) Norm**: Enforced by reputation and community. The RSP has some norm-like characteristics: Anthropic's identity investment creates reputational stakes, and the AI safety community does respond negatively to RSP violations (as v3.0 demonstrated). But norms enforce only up to the cost of defection. When competitive pressure (the race with OpenAI and DeepMind) exceeds the reputational cost of policy revision, the norm bends. RSP v3.0 represents exactly this point: Anthropic explicitly acknowledged that unilateral pausing while competitors advance "may make the world less safe" — using the safety logic itself to justify abandoning the binding safety commitment. This is the mechanism by which norms fail under competitive pressure: the defection is rationalized as actually norm-consistent.

**(d) Cheap talk**: Costless to make, costless to break. The RSP is not pure cheap talk — the investment it generated was real. But as Crawford-Sobel defines cheap talk, the relevant question is whether the communication constrains future actions conditional on the sender's interests. RSP v3.0 shows that when Anthropic's interests diverged sufficiently from the RSP's original commitments, the RSP was revised. This satisfies the functional definition of cheap talk: the communication does not bind behavior beyond the point where the sender finds it costly to comply. The signal is informative about Anthropic's stated intentions; it is not informative about Anthropic's future actions under competitive pressure. This is precisely Crawford-Sobel's babbling equilibrium prediction.

**The mechanism design verdict**: The RSP is closest to (c) a norm, with some characteristics of (d) cheap talk. It has generated real investment and real reputational stakes, distinguishing it from pure cheap talk. But it lacks the structural features of (a) a constitution or (b) a contract — specifically, external enforcement and unilateral-modification foreclosure. In mechanism design terms, the RSP is a form of pre-announcement that is credible conditional on competitive incentives remaining aligned with the announcement; it is not a mechanism that constrains behavior when incentives diverge.

The Stelling et al. comparative assessment confirms this diagnosis: the frameworks are "limited as accountability functions, with vague commitments that make it difficult to predict company decisions, assess whether planned responses are adequate, or determine whether commitments have been kept." Anthropic scores highest at 34%, meaning the best current framework in the field fails two-thirds of established risk management criteria.

### 5. Academic Literature on AI Safety Commitments Through an Institutional Economics Lens

The most analytically sophisticated piece I found is the Adhithyan Ajith essay (Medium, March 3, 2026): "The credible commitment problem in AI safety: lessons from the Anthropic-Pentagon standoff." Despite being a non-peer-reviewed analytical essay, it applies the formal game theory apparatus correctly and with primary source citation, including: Schelling (1960), Crawford-Sobel (1982), Spence (1973), Olson (1965), Armstrong-Bostrom-Shulman racing model (2016), Fearon (1997), Fudenberg-Levine reputation equilibrium (1989), and Finnemore-Sikkink norm cascade (1998, *International Organization*).

The essay's central thesis: voluntary AI safety commitments satisfy the formal definition of cheap talk, but the Anthropic-Pentagon standoff (Anthropic refused a $200M Pentagon contract and accepted blacklisting rather than abandon its safety restrictions) constitutes a costly signal that may shift the coordination equilibrium. Key analytical moves:
- OpenAI's trajectory (2018 charter to 2025 restructuring to 2026 Pentagon deal) is presented as the empirical prediction of the babbling equilibrium: commitments without enforcement dissolve when incentives shift
- Mancur Olson's collective action problem applies directly: AI safety is a public good (non-rivalrous, non-excludable), and large groups systematically underprovide public goods without coercion or selective incentives
- The Pentagon's action inverts the "shadow of hierarchy" — rather than the state enforcing safety norms (the usual voluntary-regulation backstop), the state is actively punishing the safety-conforming firm

The Ajith essay cites "Maman and Feldman (2025), a systematic literature review on compliance and effectiveness of industry self-regulation," finding high compliance only in 41% of cases, with success requiring: (1) credible enforcement, (2) measurable outcomes, (3) third-party monitoring, and (4) the shadow of hierarchy. I could not independently verify this SSRN paper through Semantic Scholar searches, but the reference appears credible and the empirical pattern it describes is consistent with the case studies above.

The Brundage et al. "Frontier AI Auditing" paper (arXiv:2601.11699, January 2026, 50+ authors including METR's Chris Painter and Yoshua Bengio) proposes four AI Assurance Levels (AALs), defining AAL-1 as baseline and AAL-2 as near-term goal for frontier developers. The paper explicitly identifies the gap between current industry practice and genuine third-party auditing, noting that audits "should not be limited to a company's publicly deployed products, but should instead consider the full range of organization-level safety and security risks, including internal deployment of AI systems, information security practices, and safety decision-making processes." This is analogous to financial auditing requirements: the constraint must cover not just public disclosures but internal processes that are not otherwise visible.

The Coggins et al. affordance analysis of OpenAI's PF v2 (arXiv:2509.24394, September 2025) and the Stelling et al. comparative assessment of 12 frameworks (arXiv:2512.01166, December 2025) together constitute the most rigorous academic treatment of what current AI safety frameworks actually commit labs to do. Their findings are consistent: frameworks are underspecified, internally discretionary, and fail most criteria from established high-risk industry governance.

The Campos et al. "Frontier AI Risk Management Framework" (arXiv, 2025, 11 citations) draws explicitly on aviation and nuclear risk management to propose what rigorous frontier AI governance should look like. Its four components (risk identification, risk analysis with quantitative metrics and clear thresholds, risk treatment through containment and deployment controls, and risk governance with clear organizational accountability) map onto the AAL system and onto the gaps in the current RSP.

### 6. Race to the Top vs. Race to the Bottom: Conditions and Application

The regulatory competition literature identifies two equilibrium outcomes under voluntary standards. David Vogel's "Trading Up" (1995) and the associated "California effect" or "Brussels effect" (Bradford, *The Brussels Effect*, Oxford 2020) describe conditions under which a high-standard jurisdiction exports its standards upward: producers comply with the most demanding market's requirements because the cost of product differentiation exceeds the cost of universal compliance, so the highest standard becomes the effective global standard.

The countervailing "race to the bottom" (or "Delaware effect" in corporate law) occurs when regulatory arbitrage is feasible: producers exit high-standard jurisdictions for low-standard ones, exporting the low standard globally.

Flowers, Matisoff, and Noonan's LEED study (2020, *Business Strategy and the Environment*) found evidence for a race to the top in voluntary green building certification — later adopters certifying at higher levels than early adopters, suggesting competitive certification dynamics. The mechanism: when certification is publicly visible and consumer-valued, firms compete to signal quality through increasingly stringent self-certification. This is the voluntarily-induced race to the top.

**Conditions predicting race to top vs. race to bottom:**
1. **Observability of compliance**: Can customers/markets distinguish genuine high compliance from symbolic compliance? (If no: race to the bottom, as free-riding is undetectable)
2. **First-mover advantage**: Does early high-standard adoption create a durable market position? (If yes: race to the top incentivized)
3. **Cost structure**: Is compliance with the high standard a variable cost (avoidable by exit) or fixed cost (unavoidable regardless)? (Variable → race to bottom; Fixed → race to top)
4. **Regulatory shadow**: Does credible regulation threaten firms that fail to self-regulate? (Shadow of hierarchy → temporary race to top; shadow removal → race to bottom)
5. **Competitive structure**: Do high-standard firms benefit from competitors also adopting high standards (coordination complement) or benefit from competitors adopting low standards (competitive advantage from differentiation)?

**Application to AI safety frameworks:**

The key question is conditions 1 and 5. AI safety compliance has very low observability: Anthropic's claim to have paused or not paused model training is verifiable only by insiders. Model capabilities are opaque. The difference between a "precautionary ASL-3 activation" (Anthropic's framing) and a "commercial deployment rationalized as precautionary" (a skeptic's reading) is genuinely hard to distinguish from the outside. This low observability creates strong race-to-the-bottom pressure: if safety-washing is hard to detect, the equilibrium is symbolic compliance.

On condition 5: the structure of AI competition is not obviously cooperative. If Anthropic pauses and OpenAI does not, OpenAI captures market share. This is a prisoner's dilemma, not a coordination game. Anthropic's own v3.0 RSP acknowledges this: "a developer unilaterally pausing while others advance may make the world less safe." This framing converts safety investment from a public good into a competitive liability, actively discouraging unilateral compliance.

The Ajith essay identifies this as the Olson problem: large groups underprovide public goods without selective incentives or coercion. The current structure has neither. The closest analogue to Vogel's California effect would be EU AI Act enforcement creating a high-standard anchor that gets exported globally via the Brussels effect — but this requires the EU to actually enforce its AI Act's GPAI provisions, which remains unproven.

### 7. The "Mast" Problem: What Actual Binding Would Look Like

Anthropic employees literally used the "binding to the mast" metaphor (Oliver Habryka, quoted in Zvi Mowshowitz's April 2026 post). The Odysseus story is instructive precisely because the binding was physical, external, and out of Odysseus's own hands once executed. The sailors received orders in advance — when Odysseus would beg to be untied, ignore him. The constraint was enforced by people who were themselves immune to the sirens.

What is the AI equivalent?

**Escrowed code / external kill switches**: Model weights held in escrow with a third-party trustee who can prevent deployment if specified conditions are not met. This is analogous to nuclear launch control — dual-key authorization where neither party alone can launch. No AI lab has implemented this. The closest existing structure is the "egress bandwidth controls" and "2-party authorization for weight access" that Anthropic describes under ASL-3 — but these are Anthropic's own internal controls, not externally held.

**Legally binding deployment limits**: Contracts or regulatory orders that prevent deployment above specified capability levels without prior regulatory approval, with penalties for violation. Analogous to aviation: no airline can introduce a new aircraft type without FAA certification. The EU AI Act's GPAI provisions for "systemic risk" models require registration and notification, but these are not pre-deployment blocking mechanisms. FDA pre-market approval of drugs is the best analogy — you cannot sell until you receive approval — but no AI jurisdiction has enacted this.

**Insurance requirements tied to third-party safety ratings**: The Reti and Weil "AI Catastrophe Bonds" proposal (AI Frontiers, January 2026) is the most sophisticated version of this idea. Cat bonds would require labs to pay premiums proportional to an independently assessed "Catastrophic Risk Index" — creating financial incentives equivalent to insurance pricing in the nuclear industry. Labs with weaker safety practices pay higher premiums; labs that cause catastrophes trigger bond payouts. This converts the voluntary safety commitment into an ongoing financial stake. The mechanism design is sound: even a lab that does not care about safety would care about premiums. The proposal is not implemented and faces the practical challenge of specifying verifiable trigger conditions.

**Third-party capability restrictions**: METR or a government body that holds veto authority over model deployment when capabilities exceed defined thresholds. Brundage et al.'s AAL framework points toward this: AAL-4 (the highest level) would involve auditors with "deep, secure access to non-public information" and the authority to certify compliance before deployment. This is genuinely external enforcement — the auditor is not the company's employee, and the certification has legal consequences.

**RSP against these archetypes**: The RSP lacks all four. The "mast" in Anthropic's self-description is Anthropic's own policy, approved by Anthropic's own board, modifiable by Anthropic's own leadership. The sailors in the Odysseus story were not Odysseus's direct reports following his standing orders; they were people with their own agency who had been given specific, bounded instructions. An RSP that Anthropic can rewrite is not a mast — it is a preference expressed in the present tense.

### 8. The Pentagon Standoff: A Natural Experiment

The Anthropic-Pentagon dispute (February 27, 2026) — in which Anthropic refused to remove safety restrictions from a $200M military contract and was designated a "supply chain risk to national security" — is, as the Ajith essay argues, a rare instance of a costly signal that converts cheap talk into potentially credible commitment. The costs are concrete: $200M in lost contract revenue, supply chain designation threatening enterprise relationships, potential Defense Production Act invocation.

The Spence signaling model predicts that this signal is credible because a "safety-washing" firm — one that merely pretends to care about safety for marketing — would not absorb these costs. The single-crossing condition holds: only a firm genuinely committed to its safety restrictions would find refusal cheaper than capitulation.

But the Ajith essay is careful to note the limits. The Pentagon's counter-narrative (Undersecretary Emil Michael calling Amodei a "liar" with a "God-complex") represents adversarial type-reclassification: the same observable action (refusing a contract) is reframed not as costly sacrifice for principle but as power-seeking behavior. If the broader market accepts this reframing, the signal's information content is destroyed without changing its cost structure.

More importantly for this analysis: the Pentagon standoff is a signal about Anthropic's resolve when confronted with state coercion, not a structural commitment device. Even if the signal is entirely credible, it constrains Anthropic's behavior only insofar as the reputational damage from backdown exceeds the cost of maintaining the position. When circumstances change — if a future government removes the designation, if competitive dynamics shift, if the financial pressure becomes severe — the signal creates no structural impediment to policy change. This is the "tying hands" mechanism (Fearon 1997), which creates audience costs but does not remove future discretion.

## Key Findings

- **The RSP fails all standard credible commitment criteria** (external enforcement, unilateral modification foreclosed) and partially fails the cost criteria (real costs imposed but not binding for future behavior). In North-Weingast terms, Anthropic retained the sovereign's power to rewrite the constitution without external enforcement, and exercised that power in RSP v3.0. (Strong evidence — documented by Anthropic's own version history and confirmed by GovAI and Zvi's analyses.)

- **Responsible Care's core lesson**: The voluntary commitment without third-party verification and real sanctions had zero measurable effect on chemical industry pollution (King and Lenox, *AMJ* 2000, 1,636 citations). Effectiveness emerged only after 1997 certification requirements — i.e., when it began to resemble actual external auditing. The RSP's METR reviews without enforcement authority are analogous to pre-1997 Responsible Care. (Strong evidence — peer-reviewed with high citation count.)

- **INPO is the most effective voluntary safety framework in industrial history**, but its effectiveness derives from structural features absent in AI: joint liability creating shared financial stakes, insurance pricing linked to safety ratings, real sanctions (forced shutdown), inspectors with skin in the game. The RSP has none of these. (Strong evidence — INPO's performance record is well-documented.)

- **The Basel II pre-crisis model is the direct analogue for AI self-assessment of risks**: when regulated entities use their own models to calculate their own risk levels, systemic underestimation is the rational equilibrium outcome. AI labs assessing their own capability thresholds reproduce this structure exactly. (Strong evidence — well-documented in financial regulatory literature.)

- **The comparative assessment of 12 AI safety frameworks** (Stelling et al., arXiv:2512.01166) gives Anthropic the top score of 34%, confirming that even the leading framework fails most established risk management criteria. The median score is 18%. (Strong evidence — formal assessment using established criteria.)

- **Race conditions predict race to bottom, not top, for AI safety**: low observability of compliance, prisoner's dilemma incentive structure, and no credible regulatory shadow in the U.S. combine to create conditions where symbolic compliance is the rational equilibrium. (Moderate evidence — applies the regulatory competition literature's conditions; the counterfactual of EU AI Act enforcement is genuinely uncertain.)

- **AI catastrophe bonds are the most promising "mast" equivalent**: the Reti-Weil proposal creates financial incentives structurally analogous to INPO's insurance mechanism, but is unimplemented and faces trigger-specification challenges. (Speculative — well-reasoned proposal without empirical validation.)

- **The Anthropic-Pentagon refusal is a genuine costly signal** in the Spence-Fearon sense, but is a tying-hands mechanism rather than a mast-binding mechanism: it creates audience costs without structurally foreclosing future modification. (Moderate evidence — the signaling analysis is theoretically sound but the empirical outcome depends on unresolved questions about market framing and norm cascade.)

## Assessment

The track record of industry self-regulation in comparable domains is pessimistic but not uniformly so. The pessimistic reading: Responsible Care (pre-1997), platform privacy self-regulation, and Basel II pre-crisis all demonstrate that voluntary commitments without external enforcement and real sanctions produce symbolic compliance rather than behavioral change. The RSP, as a unilaterally modifiable policy statement with no enforcement counterparty and no real sanctions, satisfies every condition for cheap talk in the Crawford-Sobel sense.

The more nuanced reading: INPO demonstrates that industry self-regulation can be highly effective under specific structural conditions — joint liability, insurance pricing, real sanctions, expert inspectors. Responsible Care after 1997 shows that adding verification and certification to an otherwise weak framework can produce real behavioral change. The question is not whether self-regulation works in principle, but whether the specific institutional features that make it work are present or can be created.

For the RSP specifically, the institutional gap is large. The RSP is closest to pre-1997 Responsible Care or to pre-2008 Basel II bank risk self-assessment: a voluntary framework in which the regulated entity retains full discretion over its own compliance assessment and can revise its commitments when competitive pressure rises. The evidence from these analogues predicts that the RSP will not reliably constrain behavior when capabilities reach the levels where constraining behavior is most important.

The genuine open question — and the one where I cannot form a confident view — is whether the Anthropic-Pentagon standoff represents a phase transition. If Anthropic's refusal establishes a Schelling focal point that triggers a norm cascade (other labs adopt similar contractual red lines, regulatory enforcement provides the shadow of hierarchy, the EU AI Act's GPAI provisions get enforced with real consequences), then the RSP and its analogues at other labs could evolve into something closer to binding commitment. The Finnemore-Sikkink norm cascade model (1998, *International Organization*) predicts this is possible: norm emergence can trigger cascade and internalization, especially when the focal point is simple, visible, and morally resonant.

But the Olson collective action logic predicts the opposite: without coercion or selective incentives, large groups systematically underprovide public goods. The AI industry's competitive structure is a prisoner's dilemma, not a coordination game. The Pentagon's actions (rewarding OpenAI for dropping safety restrictions, punishing Anthropic for maintaining them) actively invert the shadow of hierarchy. In this structural context, voluntary self-regulation's failure is not a contingent fact but a predicted equilibrium.

The honest answer is that the RSP is currently somewhere between "elaborate cheap talk with real investment" and "early stage of a norm that could harden into binding commitment." Whether it travels toward the binding-commitment end of that spectrum depends almost entirely on external institutional developments — EU AI Act enforcement, U.S. congressional action (as Lawfare recommends), insurance market development on the Reti-Weil model — rather than on anything Anthropic can do unilaterally. The mast that Anthropic employees have described does not yet exist. What exists is a well-publicized intention to build one, posted on a website that Anthropic controls and can update at will.

### Sources

Peer-reviewed and primary:
- King and Lenox (2000). "Industry Self-Regulation Without Sanctions: The Chemical Industry's Responsible Care Program." *Academy of Management Journal* 43(5). DOI: 10.5465/1556362
- Gamper-Rabindran and Finger (2012). "Does industry self-regulation reduce pollution? Responsible Care in the chemical industry." *Journal of Regulatory Economics* 43(1). DOI: 10.1007/s11149-012-9197-0
- Gunningham (1995). "Environment, Self-Regulation, and the Chemical Industry." *Law & Policy*
- North and Weingast (1989). "Constitutions and Commitment." *Journal of Economic History*. https://pscourses.ucsd.edu/ps200b/North%20and%20Weingast%20-%20Constitutions%20and%20Commitment.pdf
- Kydland and Prescott (1977). "Rules Rather Than Discretion." *Journal of Political Economy*
- Crawford and Sobel (1982). "Strategic Information Transmission." *Econometrica* 50(6)
- Spence (1973). "Job Market Signaling." *Quarterly Journal of Economics* 87(3)
- Fearon (1997). "Signaling Foreign Policy Interests." *Journal of Conflict Resolution* 41(1)
- Finnemore and Sikkink (1998). "International Norm Dynamics and Political Change." *International Organization* 52(4)
- Olson (1965). *The Logic of Collective Action*. Harvard University Press
- Schelling (1960). *The Strategy of Conflict*. Harvard University Press
- Armstrong, Bostrom, and Shulman (2016). "Racing to the Precipice." *AI & Society* 31(2)
- Flowers, Matisoff, and Noonan (2020). "In the LEED: Racing to the Top in Environmental Self-Regulation." *Business Strategy and the Environment*
- Vogel and Kagan (2002). *Dynamics of Regulatory Change*
- Bradford (2020). *The Brussels Effect*. Oxford University Press
- Benink (2020). "Global Bank Capital and Liquidity after 30 Years of Basel Accords." *Journal of Risk and Financial Management*

Academic preprints and reports:
- Stelling, Murray et al. (2025). "Evaluating AI Companies' Frontier Safety Frameworks." arXiv:2512.01166
- Coggins, Saeri et al. (2025). "The 2025 OpenAI Preparedness Framework does not guarantee any AI risk mitigation practices." arXiv:2509.24394
- Campos, Papadatos et al. (2025). "A Frontier AI Risk Management Framework." arXiv
- Brundage, Dreksler et al. (2026). "Frontier AI Auditing: Toward Rigorous Third-Party Assessment." arXiv:2601.11699
- Yew and Judge (2025). "Anti-Regulatory AI: How 'AI Safety' is Leveraged Against Regulatory Oversight." EAAMO 2025. DOI: 10.1145/3757887.3763017

Industry and policy sources:
- Anthropic (2023). RSP v1.0. https://www.anthropic.com/news/anthropics-responsible-scaling-policy
- Anthropic (2024). "Reflections on our RSP." https://www.anthropic.com/news/reflections-on-our-responsible-scaling-policy
- Anthropic (2026). RSP v3.0. https://www.anthropic.com/news/responsible-scaling-policy-v3
- GovAI — Williams and Freund (2026). RSP v3.0 Analysis. https://www.governance.ai/analysis/anthropics-rsp-v3-0-how-it-works-whats-changed-and-some-reflections
- Reti and Weil (2026). "Making Extreme AI Risk Tradeable." AI Frontiers. https://ai-frontiers.org/articles/ai-catastrophe-bonds-extreme-risk-tradeable
- Devanney (2025). "Why is INPO a far better regulator than the NRC?" Substack. https://jackdevanney.substack.com/p/why-is-inpo-far-more-effective-than
- GAO (1991). "NRC's Relationship with INPO." https://www.gao.gov/assets/rced-91-122.pdf

Analytical essays:
- Ajith (2026). "The credible commitment problem in AI safety: lessons from the Anthropic-Pentagon standoff." Medium. https://medium.com/@adhix/the-credible-commitment-problem-in-ai-safety-lessons-from-the-anthropic-pentagon-standoff-917652db4704
- Mowshowitz (2026). "RSP v3: A Matter of Trust." https://thezvi.wordpress.com/2026/04/01/anthropic-responsible-scaling-policy-v3-a-matter-of-trust/
