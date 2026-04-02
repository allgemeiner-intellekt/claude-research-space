# Deep Dive: The Dallas Fed Paradox

## Question

How can dating apps change almost nothing about *who* matches with *whom* (Cheremukhin et al. 2024, Dallas Fed) while simultaneously reducing *whether* people match at all (Ershov et al. 2026, NBER)? What is the specific mechanism? Investigate four hypotheses: (1) choice overload / evaluation mode shift; (2) platform incentive misalignment; (3) information degradation from desktop to mobile era; (4) outside option / perceived availability effect.

---

## What I Read and Searched

Primary sources accessed:
- Cheremukhin, Restrepo-Echavarria & Tutino (2024), "Marriage Market Sorting in the U.S.," Federal Reserve Bank of Dallas Working Paper 2023-023. Full PDF (112K chars), abstract confirmed via Semantic Scholar. DOI: 10.20955/wp.2023.023
- Ershov, Fong & Yildirim (2026), "What Happens When Dating Goes Online?", NBER WP 34757. Fetched from NBER website; abstract and mechanisms available via WebFetch summary.
- Finkel, Eastwick, Karney, Reis & Sprecher (2012), "Online Dating: A Critical Analysis From the Perspective of Psychological Science," *Psychological Science in the Public Interest*, 13(1): 3–66. Full 64-page PDF read (pages 1–47 in detail). DOI: 10.1177/1529100612436522
- Kanoria & Saban (2017), "Facilitating the Search for Partners on Matching Platforms: Restricting Agent Actions," working paper (Stanford GSB). PDF pages 1–15 read directly.
- Hu & Markowitz (2026), "Re-examining relational pursuit and mate selection in online dating," *Journal of Social and Personal Relationships*. Abstract via Semantic Scholar.
- Rusbult, Agnew & Arriaga (2011), "The Investment Model of Commitment Processes." Abstract confirmed.
- Le & Agnew (2003), "Commitment and its theorized determinants: A meta-analysis of the Investment Model." 733 citations.

---

## Investigation

### Part I: What the Dallas Fed Paper Actually Claims

The Dallas Fed paper (Cheremukhin et al. 2024) uses a "targeted search model" to analyze mate selection by education, age, race, income, and skill across the 2008–2021 period. The core finding is summarized directly in the abstract: "despite the rise of online dating, preferences, mate choice, and overall sorting patterns showed negligible change from 2008 to 2021." The paper explicitly falsifies two candidate explanations for long-run (1960–2020) trends toward greater assortative mating: (1) reduced search costs from online dating, and (2) growing spatial segregation. The surviving explanation is demographic: enhanced workforce participation and college attainment among women.

The critical sentence for resolving the paradox comes from their mechanism discussion: "people's capacity to process and evaluate information hasn't improved despite technological advancements."

This is a precise, falsifiable claim. Apps reduced the *cost* of accessing potential partners. They did not improve the *cognitive bandwidth* available for evaluating those partners. The sorting patterns that matter for assortative mating — who ends up with whom — reflect preference expression, which hasn't changed. What may have changed is a downstream behavior: the willingness to *stop searching* and commit to a particular match.

Note what the Dallas Fed paper does NOT measure: it measures matching outcomes (who pairs with whom) and preference structure. It does not measure marriage rates, cohabitation rates, or the fraction of the singles population that successfully pairs off at all. This is the measurement gap at the heart of the paradox.

### Part II: What Ershov et al. Are Measuring

The Ershov et al. (2026) paper uses county-level marriage and divorce data 2002–2023 matched to online dating usage data across hundreds of US platforms. Their central finding distinguishes eras:

- **Desktop era (2002–2013)**: 1% increase in online dating sessions → 0.50% *rise* in divorce rates. Marriage rates roughly unaffected.
- **Mobile era (2017–2023)**: 1% increase in online dating activity → 0.40% *decline* in marriage rates and 0.33% decline in divorce rates.

The proposed mechanisms in their search-and-matching model involve three technological changes that differ between eras: search costs, market size, and "market noise." Market noise is the key term. Desktop-era sites (OkCupid, eHarmony, Match.com) had detailed profiles — questionnaires, essays, stated preferences. Mobile apps (Tinder, Hinge, Bumble) have photo-first swipe interfaces with minimal profile content. The information quality per interaction degraded dramatically in the mobile era.

The decline in divorces in the mobile era is interpreted mechanically: fewer marriages → fewer divorces. It is not evidence of better matches; it is evidence of fewer matches being formed at all.

These two papers are measuring *different outcome variables*. Cheremukhin et al. ask: among people who do form partnerships, how has the demographic structure of those partnerships changed? Ershov et al. ask: has the aggregate rate of partnership formation changed? The apparent contradiction dissolves once this is recognized. There is no contradiction at all in the following joint claim: **apps changed nothing about who matches with whom, but reduced how many people match at all.**

The real question becomes: what mechanism would produce this specific pattern?

### Part III: The Evaluation Mode Mechanism (Finkel et al. 2012 — Strongest Evidence)

The Finkel et al. 2012 paper provides the most detailed psychological mechanism, and it is directly supported by experimental evidence. The key argument, developed across pages 28–32 of the paper, involves the distinction between **joint evaluation mode** and **separate evaluation mode**.

When browsing profiles, users engage in joint evaluation: they compare multiple potential partners nearly simultaneously, ranking them against each other. This triggers what Kruglanski et al. (2000) call an **assessment mindset** — critical evaluation of alternatives relative to other alternatives. When pursuing a relationship with a specific person, users are in separate evaluation mode, assessing a single partner on their own terms. This activates a **locomotion mindset** — committing psychological resources toward attaining a goal.

The problem: people make mating choices in joint evaluation mode (browsing profiles) but experience the consequences in separate evaluation mode (actually dating someone). The Finkel paper documents that preference reversals reliably occur between these modes. Attributes that are easy to evaluate in a profile comparison (income, height, physical attractiveness score) tend to be **overweighted** in joint mode relative to their actual importance once a relationship begins. Attributes that matter most in actual relationships (rapport, humor, chemistry, how someone handles conflict) are **non-searchable** and cannot be assessed from a profile.

The experimental evidence for this is strong. Eastwick & Finkel (2008a) showed that when research participants rated potential partners on three profile-assessable traits (physical attractiveness, earning prospects, personality), then met them at a speed-dating event, the traits that participants said they prioritized had no differential predictive power for their romantic interest in specific individuals at the event. In other words, stated profile-based preferences for specific traits did not predict who participants were attracted to in person. This has been replicated in multiple samples and with longitudinal designs.

The **commoditization effect** follows directly. Finkel et al. (pp. 31–32) document that profile-browsing leads users to adopt a "relationshopping" orientation (Heino et al. 2010; Whitby & Carr 2006) — treating potential partners as product offerings in a marketplace. One dater quoted in the paper: "You know, 'I'll take her, her, her' — like out of a catalog." This framing is not merely metaphorical: it activates a marketplace exchange orientation rather than a communal orientation, and close relationships are "especially satisfying to the degree that they involve... relatively high levels of social exchanges that are low in concreteness and high in particularism, such as love and affection" (Foa, 1993; Clark, 1984, cited in Finkel et al. p. 32). The marketplace frame suppresses exactly the orientation that makes relationships work.

The mobile era intensified all of this. Desktop sites (eHarmony, OkCupid) had detailed questionnaires that partially shifted the search context toward relationship-relevant information. Mobile swipe apps are almost purely photo-first, eliminating even the minimal richness of profile-based compatibility signals. Ershov et al.'s "low-quality information" mechanism maps onto the same underlying reality.

**The evaluation mode mechanism is the strongest candidate for resolving the paradox.** It explains why:
1. Sorting patterns don't change: preferences for demographic attributes (education, income, race) are expressed similarly in both online and offline contexts, because these are stable, easily expressed preferences — Cheremukhin et al. find them unchanged.
2. Marriage rates decline: the joint evaluation / assessment mindset induced by profile-browsing is anti-committal. It keeps users in a perpetual evaluation mode that postpones or prevents the transition to serious pursuit of any specific partner.

### Part IV: The Platform Incentive Misalignment (Kanoria & Saban 2017 — Evidence Is Theoretical, Not Empirical)

The Kanoria & Saban (2017) paper is frequently cited in the context of platform incentive problems in dating markets. It should be clarified: this paper does *not* argue that dating platforms deliberately engineer failure to keep users subscribed. Its argument is more nuanced and concerns search environment design.

The paper models two-sided matching platforms and finds that:
- In asymmetric markets (where one side has higher screening costs), platforms can significantly boost welfare by restricting who proposes and who waits.
- The "long side" of the market (usually men, who face rejection more often) ends up as perpetual proposers in equilibrium, which reduces their welfare and selectivity.
- A platform that "hides quality information" can in some cases improve welfare by preventing premature filtering.

The platform incentive argument in the popular form — platforms profit from continued searching, not from successful matches — is stated more directly in the Finkel et al. paper (p. 32), which notes that "dating sites appear to have an incentive to entice nonpaying members to send... messages because it can help convert nonpaying members to paying members." This is a real incentive. However, the Kanoria & Saban paper explicitly footnotes: "There may still be some tension between maximizing revenues and maximizing user welfare, which we suppress, noting only that agent welfare is crucial even for a revenue maximizing platform, since user retention depends on it."

No published empirical paper directly tests whether platforms deliberately engineer lower match rates to retain subscribers. The popular claim that Tinder/Match Group profits from failed matches is plausible but has no peer-reviewed empirical support. The Finkel et al. paper does document that at some sites (Match, eHarmony), free members can receive messages from paying members but must pay to respond — an incentive structure that generates engagement activity without generating matches. This is the strongest empirical grounding for the platform incentive argument, and it is at the level of business model observation, not causal analysis.

**Assessment of this mechanism**: Real as an incentive, plausible as an effect, but evidentially weak. It cannot explain the Dallas Fed finding (changing platforms did not change sorting) unless we believe the incentive misalignment is specifically about the *quantity* of matching (fewer total marriages) rather than the *quality* of sorting (who matches whom). This is technically consistent — you can have unchanged preference expression while having suppressed follow-through — but the direct evidence for the platform-profit driver of this is thin.

### Part V: Information Degradation from Desktop to Mobile Era (Ershov et al. 2026 — Moderate Evidence)

The Ershov et al. (2026) split between desktop and mobile eras is the most direct empirical evidence for the information-quality mechanism. Desktop sites (2002–2013) raised divorce rates: they likely improved the pool of accessible partners (reducing false matches through better screening) but expanded the alternative set enough to destabilize existing marriages or attract people who discovered better options post-marriage. Mobile apps (2017–2023) reduced marriage rates: they provide access to large pools of potential partners but with such minimal information per profile that commitment decisions are either postponed or not made at all.

This mechanism is distinct from choice overload in an important way. Choice overload predicts that more options → worse decisions because of cognitive fatigue. The information-degradation mechanism predicts that the *type* of information matters: photo-first interfaces generate a shallow evaluation context that is structurally unsuited to commitment formation, regardless of the number of options. The Hu & Markowitz (2026) paper actually provides evidence *against* simple choice overload: in two preregistered experiments (n=193 and n=342), participants who chose from 31 profiles reported *greater* relational pursuit with their selected partner than those who chose from only 6 profiles, mediated by perceived compatibility. This is a direct counter-finding to the Iyengar jam experiment analogy that Finkel et al. invoke.

The Finkel et al. paper itself (pp. 32–33) references evidence that online daters do not become less satisfied with the search process as choice sets expand to 64 profiles (Lenton et al. 2008; Lenton & Stewart 2008). The subjective experience of choice overload is not confirmed in online dating contexts at experimentally tractable scales.

This suggests that **information quality is the more proximate mechanism than choice overload per se.** The problem is not that there are too many options, but that the options are evaluated on the wrong dimensions (searchable but relationship-irrelevant attributes) using the wrong cognitive mode (joint/assessment rather than separate/locomotion).

### Part VI: The Outside Option / Investment Model Mechanism (Theoretical Grounding, Limited Direct Evidence)

Rusbult's Investment Model of Commitment (meta-analyzed by Le & Agnew 2003, 733 citations) identifies three drivers of commitment: relationship satisfaction, investment size, and quality of alternatives. Commitment decreases as the perceived quality of alternatives increases. Apps structurally increase the *perceived* availability of alternatives — which is different from actual availability. Even if apps don't change who people ultimately match with, they may change people's subjective sense that better alternatives are always available, which would reduce commitment to any current partner.

This mechanism is theoretically coherent and widely cited in popular discourse. The 2026 Medium essay by Conor Watkins articulates it clearly: "Here's what the optionality trap actually looks like in practice. You meet someone, the connection is real, the conversation is easy, and then you quietly throttle it... committing attention to one person feels like closing a door before you've checked what's behind the others."

However, direct empirical tests of whether apps increase *perceived* alternative quality (as distinct from actual match rates) are rare. The SwipeStats data (7,079 Tinder profiles) does document that most users — particularly men with low match rates — face a factual desert of alternatives, not an abundance. For these users, the outside option mechanism runs backward: apps may reduce *actual* perceived alternatives for the majority of (low-match) users, while increasing the perceived sense that alternatives exist for high-match users. The aggregate effect on commitment could be heterogeneous in a way that reduces overall market formation rates without showing up in sorting patterns.

---

## Synthesis: Resolving the Paradox

The Dallas Fed paradox is not a paradox. It rests on measuring different things:

- **Cheremukhin et al. (2024)** measure the *structure* of marriages that form: who pairs with whom demographically. They find stability 2008–2021. This is consistent with stable underlying preferences.
- **Ershov et al. (2026)** measure the *rate* of marriage formation. They find a decline in the mobile era. This is consistent with reduced willingness to commit.

You can have stable preferences (unchanged sorting) while having reduced follow-through (reduced marriage rates) if there is a mechanism that blocks preference expression from converting into commitment. Several converging mechanisms do this:

**Primary mechanism (strongest evidence): Evaluation mode shift**

Mobile-era swipe apps structurally induce a joint evaluation / assessment mindset that is cognitively anti-committal. Profile-browsing activates the wrong mode for relationship formation. The attributes that drive profile-based evaluation (searchable characteristics like appearance, income, stated interests) are poor predictors of relationship success once people actually meet. The attributes that predict relationship success (rapport, humor, chemistry, conflict style) cannot be assessed from a swipe interface. The net result: people's *preferences* are expressed correctly (they still end up with similar types), but their *willingness to commit* to any specific individual is suppressed by the perpetual-evaluation frame.

This is consistent with Finkel et al.'s findings that CMC-based pre-date communication of more than ~3 weeks makes subsequent face-to-face meetings *worse* (Ramirez & Zhang 2007), because the idealized CMC impression is violated by in-person reality. Mobile apps don't even generate the rich CMC interaction of desktop sites — they more directly route users to a perpetual profile-browsing state without a clear commitment escalation path.

**Secondary mechanism (moderate evidence): Information degradation in mobile era**

Desktop-era sites had detailed profiles, compatibility questionnaires, and in some cases (eHarmony) algorithmic screening. These provided more relationship-relevant signal. Mobile apps provide photo-first, minimal-text interfaces. The shift increased access (more people, easier to reach) while reducing information quality. Ershov et al.'s model formalizes this as "market noise" — more signal corruption per interaction in the mobile era. Consistent with the observation that desktop apps *raised* divorces (people found real alternatives and left bad marriages) while mobile apps *reduced* marriages (people didn't commit at all).

**Tertiary mechanism (weak empirical evidence): Platform incentive misalignment**

Platforms have real financial incentives that are not fully aligned with user welfare — engagement metrics (daily active users, time on app) versus successful matches. The structure of free-to-receive/pay-to-respond messaging documented in Finkel et al. creates engagement without matches. However, this mechanism lacks causal empirical support beyond business model observation. It is plausible but not demonstrated to be a primary driver.

**Quaternary mechanism (theoretically coherent, limited direct evidence): Outside option perception**

Rusbult's Investment Model predicts that perceived alternative quality reduces commitment. Apps may elevate perceived alternative availability even for users with objectively low match rates, reducing investment in any current relationship. The mechanism is theoretically well-grounded but the specific pathway (apps → perceived alternatives → reduced commitment) has not been tested cleanly in empirical studies.

**What does NOT work: Simple choice overload**

The simple choice overload argument (too many options → paralysis → no choice) is not well supported in dating contexts. Hu & Markowitz (2026) find the opposite in a preregistered experiment. Finkel et al. acknowledge that the literature does not confirm reduced satisfaction from larger choice sets in online dating at experimentally accessible scales. This mechanism is vivid and plausible but the direct evidence for it in dating specifically is weak.

---

## Key Findings

1. **The "paradox" is a measurement gap, not a contradiction.** Cheremukhin et al. measure who pairs with whom (sorting structure). Ershov et al. measure whether people pair off at all (rate). Both can be simultaneously true: stable who + declining how-many. [Strong evidence — both papers are clear about their measurement scope]

2. **The Dallas Fed's core insight is about information processing capacity, not preferences.** The key sentence: "people's capacity to process and evaluate information hasn't improved despite technological advancements." Apps gave people more options but not more cognitive bandwidth to evaluate them. This explains stable sorting (people still express the same underlying preferences when they do match) while being consistent with fewer matches (people are overwhelmed not by number of choices but by the evaluation context). [Strong evidence — directly stated in paper abstract and consistent with theoretical framework]

3. **The Finkel et al. evaluation mode mechanism is the most empirically grounded explanation.** Joint evaluation (profile-browsing) vs. separate evaluation (actual dating) are cognitively distinct modes. Apps lock users in joint/assessment mode; commitment requires separate/locomotion mode. Profile-based attributes predict who people *say* they want; experiential attributes predict who people *actually commit to*. This explains both stable sorting (demographic preferences expressed in who-you-contact are consistent) and reduced marriage (the mode-shift prevents commitment escalation). [Strong evidence — multiple experimental studies across 12+ years of cumulative research]

4. **Information degradation from desktop to mobile era is real and empirically documented.** Ershov et al.'s split finding (desktop raised divorces, mobile reduced marriages) is the most direct evidence. Desktop-era information richness allowed better matching and expansion of alternative awareness; mobile apps' photo-first interface degrades the quality of evaluation without proportionally degrading access. [Moderate evidence — Ershov et al. is a working paper, not yet peer-reviewed, but methodology is credible]

5. **Platform incentive misalignment is real as a business model observation, but its causal contribution to the paradox is not empirically demonstrated.** The popular claim (apps profit from failed matches) has no peer-reviewed causal evidence. The theoretical platform design literature (Kanoria & Saban 2017) focuses on search environment design and welfare, not on deliberate match suppression. [Speculative as causal mechanism; moderate as structural observation]

6. **The Investment Model / outside option mechanism is theoretically sound but empirically undertested in dating app contexts.** Rusbult's investment model is one of the most-replicated frameworks in relationship psychology (Le & Agnew 2003 meta-analysis, 733 citations). The specific link between app use and inflated perceived alternative quality has not been cleanly tested. [Speculative as a dating-app-specific mechanism; strong as general relationship science]

7. **Simple choice overload is not well supported in dating.** The most recent experimental evidence (Hu & Markowitz 2026) finds larger option sets *increase* relational pursuit in online dating. This is a direct counter to the popular analogy between online dating and Iyengar's jam experiment. [Moderate evidence against simple choice overload; main caveat is that experimental profiles are hypothetical, not the full app experience]

8. **Cheremukhin et al. (2024) identify the long-run driver of assortative mating increases as demographic, not technological.** The paper falsifies both reduced-search-costs and spatial-segregation explanations. Female labor force participation and college attainment account for roughly half the increased household income inequality attributable to assortative mating 1960–2020. Online dating is a bystander, not a driver, of these trends. [Strong evidence — this is the paper's central empirical finding]

---

## Assessment

The Dallas Fed "paradox" is, on careful examination, a false puzzle created by conflating two distinct outcome variables. Cheremukhin et al. and Ershov et al. are measuring different things: the demographic structure of couples vs. the probability of couple formation. Both findings are correct and mutually compatible.

The genuine puzzle — why apps reduced marriage rates in the mobile era despite increasing access — is resolved most convincingly by the evaluation mode mechanism from Finkel et al. (2012). Profile-browsing induces a cognitive state (joint evaluation, assessment mindset) that is structurally hostile to the commitment formation that marriage requires. Users express the same underlying preferences (explaining stable sorting) but remain stuck in evaluation mode (explaining declining commitment rates). The mobile era's information degradation amplified this: swipe interfaces are even more purely profile-comparison environments than desktop sites were.

This resolution has a troubling implication for policy and product design. The problem is not that people are making worse choices or have worse preferences. The problem is structural: the interface itself suppresses the cognitive mode that commitment requires. Apps are not broken because they show you the wrong people. They are broken because the act of using them puts you in the wrong mental state for choosing any of them.

The strongest evidence chain runs: Cheremukhin (stable sorting → unchanged preferences) + Finkel (evaluation mode shift → anti-committal cognition) + Ershov (mobile era → reduced marriages, mobile = more extreme profile-comparison interface). The weakest link is that Ershov et al. do not directly measure the evaluation mode shift — their mechanism discussion invokes "market noise" and "choice overload" as labels for what the Finkel framework provides mechanistic grounding for.

**What the evidence supports firmly:** Apps changed the evaluation context without changing underlying preferences. The evaluation context suppresses commitment. Mobile apps are worse at this than desktop apps because they provide less relationship-relevant information per interaction.

**Where uncertainty remains:** We do not have direct experimental evidence that mobile app use specifically induces an assessment mindset in a way that reduces commitment formation. The chain of inference from Finkel's profile-browsing studies (conducted mostly with website-based platforms) to the swipe-era apps is theoretically coherent but not directly tested. A clean experiment — randomly assigning people to swipe vs. rich-profile interfaces and measuring subsequent commitment rates — does not appear to exist in the literature.

---

## Sources

1. Cheremukhin, A., Restrepo-Echavarria, P., & Tutino, A. (2024). "Marriage Market Sorting in the U.S." Federal Reserve Bank of Dallas Working Paper 2023-023. https://s3.amazonaws.com/real.stlouisfed.org/wp/2023/2023-023.pdf

2. Ershov, D., Fong, J., & Yildirim, P. (2026). "What Happens When Dating Goes Online? Evidence from U.S. Marriage Markets and Health Outcomes." NBER Working Paper 34757. https://www.nber.org/papers/w34757

3. Finkel, E.J., Eastwick, P.W., Karney, B.R., Reis, H.T., & Sprecher, S. (2012). "Online Dating: A Critical Analysis From the Perspective of Psychological Science." *Psychological Science in the Public Interest*, 13(1), 3–66. https://doi.org/10.1177/1529100612436522

4. Kanoria, Y. & Saban, D. (2017). "Facilitating the Search for Partners on Matching Platforms: Restricting Agent Actions." Columbia/Stanford GSB working paper. https://web.stanford.edu/~dsaban/facilitating-search.pdf

5. Hu, J.M. & Markowitz, D.M. (2026). "Re-examining relational pursuit and mate selection in online dating." *Journal of Social and Personal Relationships*. https://doi.org/10.1177/02654075261429319

6. Le, B. & Agnew, C.R. (2003). "Commitment and its theorized determinants: A meta-analysis of the Investment Model." *Personal Relationships*. 733 citations.

7. Buyukeren, M., Makarin, A., & Xiong, W. (2026). "The Impact of Dating Apps on Young Adults: Evidence From Tinder." SSRN/AEA Applied Economics. DOI: 10.2139/ssrn.4240140

8. Eastwick, P.W. & Finkel, E.J. (2008a). "Sex differences in mate preferences revisited: Do people know what they initially desire in a romantic partner?" *Journal of Personality and Social Psychology*, 94(2), 245–264.

9. Rusbult, C.E., Agnew, C.R., & Arriaga, X.B. (2011). "The Investment Model of Commitment Processes." In Van Lange et al. (Eds.), *Handbook of Theories of Social Psychology*.
