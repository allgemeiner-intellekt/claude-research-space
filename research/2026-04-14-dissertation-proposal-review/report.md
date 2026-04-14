# The Proposal, Re-Read: What It's Actually Doing, Where It Breaks, and How to Fix It

## Three paragraphs for when you wake up

You wrote a proposal asking whether generative AI is closing the door on young workers trying to enter high-exposure occupations, using a shift-share (Bartik) instrument built from 2019 U.S. commuting-zone occupational shares and Eloundou et al.'s GPT-exposure scores. The substantive thesis is real and timely — the newest empirical papers (Brynjolfsson-Chandar-Chen's "Canaries in the Coal Mine" [2025] with its 16% employment decline for 22-25-year-olds in AI-exposed occupations; Galdin & Silbert's November 2025 Freelancer.com paper quantifying signal erosion; Lodefalk et al.'s Swedish register data) all support the phenomenon you're interested in. But your identification strategy, as currently written, does not actually test that thesis. **The single most important finding of this review is that the "iPad" reviewer's key concern is structurally correct: a CZ-level instrument cannot identify occupation-specific entry effects.** This is not a nitpick — it is a violation of what the canonical shift-share literature (Borusyak-Hull-Jaravel, Goldsmith-Pinkham et al., Adão-Kolesár-Morales) allows.

The fix is clean but requires reframing the outcome. Change the dependent variable from "rate of entry of young workers into occupation o in CZ c" to "share of young workers employed in high-exposure occupations in CZ c." This keeps the outcome at the CZ level, which the shift-share design can identify, while preserving the substantive question. Your correct methodological template is **Acemoglu & Restrepo (2020)** on robots — same structure: generic occupational shares × technology-shock shifts → CZ-level outcome — not Mohnen (2023/2025) which is an *exogenous-shares* design and doesn't fit your setup. With Bonfiglioli et al. (2024/2025) as the AI-specific precedent, the reduced-form intent-to-treat estimand becomes coherent.

The second most important finding is that your proposal's cleanest narrative — signal erosion — is both a strength and a liability. The Spence (1973) → Galdin-Silbert (2025) theoretical chain is tight and real. But H3 as written is not a testable hypothesis; it is a story. If you want it to survive peer review, either commit to testing it directly (with job-posting microdata, outside the shift-share design), or demote it to an organizing interpretation for H1-H2 and admit that your empirical setup cannot distinguish it from task displacement. Both supervisors flagged this, and they're right — you can't claim to test the signal-erosion mechanism with a shift-share that only identifies aggregate labor-demand contractions. What follows below is the full diagnostic walk-through.

---

## 1. What the proposal is actually arguing, in one page

Your claim, stripped of citations, is:

1. **Aggregate unemployment isn't the first thing to move** after a GenAI shock. Adjustment happens on other margins first — the "allocation margin" from the Jaimovich-Cortes automation literature.
2. **The specific margin that moves first is the entry channel for young workers.** Hires get scarcer before anyone gets laid off. Young workers bear the brunt because they lack the alternative screening inputs (work history, networks) that incumbents possess.
3. **A plausible reason for this age-specific sensitivity is signal erosion.** Young workers rely on demonstrable outputs — writing samples, coding tests, case studies — to signal ability. LLMs reduce the informativeness of these signals by making them cheap to produce. Employers respond by tightening junior hiring rather than firing incumbents.
4. **You test this with a shift-share design** that exploits the fact that different CZs had different pre-GenAI occupational mixes, so even with uniform national GenAI diffusion, some CZs have larger "potential shocks" than others.
5. **A licensing-buffer heterogeneity test** (H4) serves as an indirect check on the signal-erosion mechanism: occupations where entry depends on formal credentials should be less affected than those where it depends on demonstrable writing/analytical output.

This framing is intellectually serious. The sequencing claim (#1-2) puts you in conversation with the right literature. The signal-erosion claim (#3) is novel among GenAI-labor papers — most others treat displacement as a pure task/demand story. H4 is a genuinely clever indirect test. And your instinct that CZ-level pre-GenAI variation is the cleanest available identifying variation (compared to using ChatGPT's release as a natural experiment, which is contaminated by COVID recovery, tech layoffs, and monetary tightening) is correct.

The problem is that when you sit down to actually estimate the effect, the pieces don't quite fit together.

---

## 2. The supervisor's key concern, decoded

iPad wrote, on H1:
> "exposure is calculated based on occupation composition in a location, isn't it? As such, the variation is at the location level, not the occupation level. So why occupation composition affects the entry specifically to high-exposure occupations? The theoretical link is not obvious. This is probably my key concern with regard to the design."

Here is what this means technically. Your shift-share index is

$$Z_c = \sum_o s_{o,c,2019} \cdot g_o$$

This is a single number per commuting zone. It doesn't vary across occupations within a CZ. It varies only across CZs. So when you regress

$$\text{entry}_{c,o,t,a} = \alpha + \beta \cdot Z_c \cdot \text{Post}_t \cdot \text{Young}_a + \ldots$$

with entry rate into *specific* occupations as the left-hand side, the cross-CZ variation in $Z_c$ is what identifies $\beta$. But that variation tells you about aggregate CZ-level shocks, not about which occupations inside the CZ are differentially affected. The instrument doesn't provide occupation-specific variation.

There is also a mechanical composition problem. CZs with high $Z_c$ have high $Z_c$ *because* they have many high-exposure jobs to begin with. So they mechanically have more scope for young workers' entry into those occupations to fall — if entry rates move proportionally with employment stocks, you get a spurious correlation even without any causal effect of AI.

The canonical shift-share literature is unambiguous on this point. Borusyak-Hull-Jaravel's (2025 JEP) practical guide includes a Table 1 cataloging roughly a dozen canonical applications. Every single one uses an outcome at the same level as the instrument: CZ instrument → CZ outcome. This isn't convention; it's what the exclusion restriction requires. Goldsmith-Pinkham et al. (2020) decompose SSIV as a weighted average of share-specific instruments — for the exclusion restriction to hold, each share must affect the outcome *only* through the treatment. An occupation share affecting an occupation-specific outcome violates this trivially via composition.

**Verdict: the supervisor is right. This is the single biggest structural issue in your proposal.**

## 3. The fix (and why it isn't Mohnen)

There are three ways out.

**Option 1 (recommended): change the outcome to a CZ-level aggregate.** Make the dependent variable the *share of young workers in CZ c who are employed in high-exposure occupations*, computed at the CZ level. Your substantive question is preserved: "do young workers in more GenAI-exposed CZs see a lower share of themselves in high-exposure occupations?" is essentially what you wanted to ask all along. But now the outcome level matches the instrument level, and the specification is coherent.

**Option 2: build a CZ × occupation panel with occupation-varying instruments.** This would let you keep the occupation dimension, but it requires a different instrument structure and articulating distinct identifying variation. This is beyond MSc scope and faces near-mechanical first-stage problems (your shift $g_o$ is static, so $Z_{c,o} = s_{o,c} \cdot g_o$ ends up very close to the treatment itself).

**Option 3: abandon the shift-share entirely and run occupation-level DiDs** — like Massenkoff & McCrory (2026) or Brynjolfsson et al. (2025). This is cleaner but gives up the geographic identifying variation that distinguishes your paper.

Option 1 is the move. Do it.

**But beware: your supervisor presumably knows Mohnen (2023/2025) "The Impact of the Retirement Slowdown on the U.S. Youth Labor Market," which uses young workers' CZ-level outcomes with a CZ-level instrument. It looks like the same template. It isn't.**

Mohnen's instrument is the age composition of the 45+ population, with shifts being national retirement rates at each age. This is what Borusyak-Hull-Jaravel classify as an *exogenous-shares* design. The shares are tailored: they capture only age composition, not generic occupational exposure. They are pre-determined by birth-cohort patterns from 20-40 years earlier, which no labor market shock could plausibly contaminate. This is why Mohnen's shares can bear the identification burden.

Your occupational shares are *generic* in BHJ's taxonomy: they capture exposure to *any* occupation-level shock, not just GenAI. (If an industry trade shock had arrived in 2020, your $Z_c$ would also predict its effects.) This means your design is an *exogenous-shifts* case — identification must come from the claim that the Eloundou scores $g_o$ are quasi-randomly assigned across occupations conditional on observables.

The correct template for your design is **Acemoglu & Restrepo (2020) "Robots and Jobs"** (*JPE*). Same structure: generic industry/occupation shares × technology-shock shifts → CZ-level outcomes. **Bonfiglioli, Crinò, Gancia, Papadakis (2024/2025) "Artificial Intelligence and Jobs: Evidence from US Commuting Zones"** (*Economic Policy*) is the AI-specific precedent — they implement exactly the Acemoglu-Restrepo framework on AI and CZs. This is the paper you should cite as your structural template.

(Mohnen can still appear in your proposal, but narrowly, as a precedent for using CZ-level young-worker outcomes. The identification logic is someone else's.)

## 4. The pre-trend problem — real but not fatal

There is a separate identification threat that deserves explicit handling: the *pre-trend* problem. Morgan Frank, Javadian Sabet, Simon, Bana & Yu (2026, arXiv:2601.02554) use three independent data sources (UI records, LinkedIn profiles, university syllabi) to show that AI-exposed occupations began deteriorating in *early 2022*, before ChatGPT's November release. If this is right, your 2019-vs-2023/24 comparison will conflate (a) a GenAI-specific effect, (b) a broader pre-GenAI automation wave, (c) the post-COVID tech-sector contraction (mass layoffs in AI-exposed roles began late 2022), and (d) macro tightening from 2022 rate hikes.

This is real, but two things limit its severity for you. First, Acemoglu & Restrepo's pre-trend test is explicit and easy to replicate: regress 2015-2019 CZ outcome trends on $Z_c$ and show the coefficient is indistinguishable from zero. If it is, your 2019 baseline is defensible. If it isn't, you have a problem that needs disclosing regardless.

Second, the most severe version of the critique applies to the tech-heavy subset of AI-exposed occupations. Restrict to non-tech AI-exposed occupations (customer service, writing, legal, analyst roles) as a robustness check and the pre-trend concern shrinks considerably.

Note also that the Brynjolfsson-Chandar-Chen Canaries authors have *themselves* conceded, in a February 2026 follow-up blog post, that with firm-time fixed effects — their most stringent specification — the effect becomes significant only in 2024, not 2022. This is the honest reading: GenAI displacement effects on young workers become *cleanly* detectable from 2024 onward, once the tech-contraction noise clears. Your post-period of 2023-2024 is well-positioned for this, but be aware that the Canaries 16% headline is a 2022-start number; the 2024-start number is what genuinely replicates across designs.

(A small but consequential correction: one of the agents in this review initially believed the Canaries authors' Feb 2026 post was a response to a "Frank et al. 2026 pre-trend critique of Canaries." No such critique paper exists. Frank et al.'s 2026 paper studies pre-ChatGPT unemployment trends using 2010-2020 data and is *not* a targeted Canaries critique. The Canaries timing concession is self-generated, not polemic. Don't cite a debate that didn't happen.)

## 5. What's actually in the empirical landscape

Here is the current state of play, corrected from your proposal's citations:

| Paper | What it actually shows | Your citation |
|---|---|---|
| Brynjolfsson, Chandar, Chen (2025) "Canaries in the Coal Mine" | 16% relative employment decline for 22-25-year-olds in AI-exposed occupations (ADP payroll data, ~25M workers). The effect is 2022-start in the headline figure but 2024-start in the firm-time FE specification. | **Missing from your proposal — add it. This is the single most important paper for your thesis.** |
| Galdin & Silbert (2025) "Making Talk Cheap" arXiv:2511.08785 | Freelancer.com data, pre/post ChatGPT. Wage premium for tailored applications collapsed to zero post-LLM. Structural model: top-quintile hired 19% less often, bottom-quintile 14% more often under no-signaling equilibrium. | **Missing — add it. This is the closest published quantification of the signal-erosion mechanism.** |
| Lodefalk et al. (2026) "Same Storm, Different Boats" | Swedish register data. 5.5% employment gap for 22-25-year-olds in AI-exposed occupations by early 2025; +1.3% for 50+. Uses Riksbank-vs-ChatGPT timing gap to separate monetary tightening from AI. | **Missing — add it. The monetary-policy identification move is a conceptual template.** |
| Frank, Javadian Sabet, Simon, Bana, Yu (2026) "AI-exposed jobs deteriorated before ChatGPT" | Pre-trends in AI-exposed occupations begin early 2022. | You mention it as a brief hedge. It's the most serious identification threat you face — treat it with a dedicated robustness section. |
| Humlum & Vestergaard (2025a) "Still Waters, Rapid Currents" | Precise null effects on earnings and hours in Denmark, including for *early-career* jobs. | You cite this accurately. Note explicitly that this is the strongest *null* result in the literature and represents genuine uncertainty. |
| Humlum & Vestergaard (2025b) PNAS | The paper's *main* finding is that higher-earning, male workers are the disproportionate ChatGPT users, *exacerbating* existing inequalities. The young-workers-adopt-faster fact is a side result. | **Your citation is misleading — you use a secondary fact from a paper whose central message cuts against a naive "young workers benefit" reading.** |
| Chen et al. (2025) | Unemployment unchanged, **earnings rose** for exposed workers. | You cite only the unemployment null. Omitting the positive earnings result is a selective read. |
| Tamkin & McCrory (2025) and Massenkoff & McCrory (2026) | Anthropic research notes, *not* peer-reviewed. The young-worker hiring result in Massenkoff-McCrory is described by the authors themselves as "just barely statistically significant." Figure 7 (the key young-worker chart) had a labeling error that required correction three days after publication. | Cite with caveats. Do not treat as equivalent to peer-reviewed evidence. |
| Jaimovich et al. 2021 JME (NBER WP 27122) | Long-run stock claim: "unemployment rates remained roughly unchanged." *Not* a temporal sequencing claim. Young workers appear only in a secondary NLSY robustness check. | Distinguish this from Jaimovich & Siu (2020 ReStat) "Job Polarization and Jobless Recoveries," which explicitly shows routine employment loss is *cyclical* — unemployment *does* respond in the short run. Your proposal blurs these two papers. |
| Cortes, Jaimovich, Nekarda, Siu (2020) | Reduced inflows dominate over increased outflows. **For all workers.** The Swiss replication (Gschwendt 2022) finds middle-aged workers most affected, not young workers. | The young-worker specificity is not in Cortes et al. Don't lean on it for that. |
| Dauth et al. (2021) | "Loss of manufacturing jobs is solely driven by fewer new jobs for young labor market entrants." | Accurately cited, but note: German manufacturing with strong employment protection — the institutional extrapolation to US services/white-collar isn't automatic. |

## 6. Addressing each supervisor comment, directly

Here is my synthesis of how to respond to each of the ten substantive comments. Think of these as what you should prepare for your next supervisor meeting.

### (1) iPad: CZ-level exposure cannot identify occupation-specific entry

Concede, and fix. Adopt Option 1: change the outcome to "share of young workers in high-exposure occupations in CZ c," computed as a CZ-level aggregate. Cite Acemoglu-Restrepo (2020) and Bonfiglioli et al. (2024/2025) as the template. Your substantive question — whether young workers in more exposed CZs are moving out of (or failing to enter) exposed occupational segments — is preserved.

### (2) itays: Can the empirical approach distinguish signal erosion from task displacement?

Honestly, no — not with the shift-share alone. Both channels predict the same sign on your headline estimand (fewer young workers in high-exposure occupations). You have two options.

**Option A (honest and MSc-feasible)**: Demote signal erosion from a tested mechanism to an *organizing interpretation*. Say explicitly in the mechanism section: "This paper cannot cleanly distinguish signal erosion from task displacement empirically. Both predict entry contraction. We interpret our results as consistent with either (or both) channels, and rely on H4 (the licensing-buffer heterogeneity test) as an indirect mechanism check." This is intellectually clean. It acknowledges the limit without abandoning the framing.

**Option B (more ambitious)**: Run an auxiliary occupation-level DiD on job-posting microdata (Lightcast/Burning Glass, available through most university data centers). Test whether *screening requirements* — credential intensity, years-of-experience requirements, referral dependence — rose differentially in writing-reliant occupations after ChatGPT, relative to verifiable-output occupations. This is a separate identification strategy but fits in a complementary chapter. Galdin-Silbert provide the theoretical frame; your contribution would be the formal-labor-market replication of their platform-based result.

I'd go with A for the MSc and flag B as future work.

### (3) iPad: H3 signal erosion is not a testable hypothesis

True, as written. A testable formulation would look something like: *"After November 2022, entry-level job postings in writing-reliant knowledge-economy occupations (high O\*NET Writing Importance) show a larger increase in formal credential requirements and a larger increase in referral-hiring premia than occupations where employer assessment does not rely on self-produced written signals (e.g., healthcare, skilled trades)."* This is falsifiable with Lightcast data. If you can't run it, drop the claim to test it and use it as an interpretive frame (Option A above).

### (4) iPad: Entry-before-exits is overclaimed from Jaimovich et al.

Also true. Jaimovich et al. (2021 JME) is a *long-run stock* claim ("unemployment rates remained roughly unchanged"), not a temporal sequencing claim. Jaimovich & Siu's 2020 ReStat paper — which you don't cite separately — actually shows that routine employment loss is cyclical. So "unemployment doesn't respond in the short run" is not what either paper says.

Reframe H2 as a claim about *relative intensity*: "In the short-to-medium run, the entry margin contracts more sharply than unemployment rises." This is a compositional claim about where adjustment concentrates, not a temporal sequencing claim. It's testable against your data (you'll measure both margins). And it survives the "but unemployment could respond too" critique — yes, it could, but the claim is that entry moves *more*.

On "flows should change for all workers, not just young" — iPad is right; Cortes et al.'s inflow-decline finding is about all workers, not young workers specifically. The young-worker specificity comes from Dauth et al. (2021, German manufacturing robots) and from the newer GenAI evidence (Brynjolfsson Canaries, Lodefalk). Be explicit: your young-worker focus is motivated by the GenAI-specific evidence, with Dauth et al. providing the automation-era analogue. Don't overclaim what Jaimovich/Cortes say about age.

### (5) iPad: How will you interpret the magnitude of β?

This is a methodological standard you must meet. **Standardize $Z_c$ to mean 0, SD 1 across CZs before estimation.** Then report β in three framings, following Bonfiglioli et al.:

1. *Raw SD effect*: "A one-standard-deviation increase in CZ GenAI exposure is associated with a β percentage-point change in the share of young workers employed in high-exposure occupations in the post-period."
2. *IQR effect* (ADH template): "Moving from the 25th to the 75th percentile of CZ GenAI exposure implies a β × (IQR/SD) percentage-point differential."
3. *Relative to baseline*: "This represents a β/Ȳ × 100% change relative to the pre-period mean of Ȳ."

Anchoring against the literature: a plausible range for β on standardized $Z_c$ is −0.01 to −0.05 percentage points, which would imply a 3-17% relative decline in young-worker high-exposure-occupation share against a pre-period baseline of ~25-30%. The Brynjolfsson 16% and Lodefalk 5.5% give you the order of magnitude. A β outside −0.10 to +0.03 should prompt a specification check.

**Include in your summary statistics table: the pre-period mean and SD of $Z_c$ (in raw units), and the pre-period mean of the outcome. Without these anchors, no one can tell if your effect is large or small.**

### (6) itays: AI may directly replace entry-level skills (alternative channel)

This is just a different framing of itays's point about distinguishing signal erosion from task displacement. See (2) above. Acknowledge the task-displacement channel explicitly in the mechanism section. Your paper can claim to establish the *reduced-form result* (entry contraction) and to be consistent with either (or both) mechanisms, without having to pick one empirically.

### (7) itays: Describe shift-share before the data section

Structural fix. Reorder: move the Empirical Identification section (§5) before the Data section (§3), so the reader sees the design logic first and then how the data implements it. This is a small change with meaningful clarity payoff.

### (8) itays: Why aggregate occupations into high/med/low exposure groups?

The honest answer is *sample-size pragmatism* — ACS cells at the CZ × specific-occupation × age-group level are thin, and aggregation to exposure tertiles reduces variance. State this plainly. Under Option 1 (CZ-level aggregate outcome), this concern partly dissolves: you're computing the *share* of young workers in "high-exposure occupations" at the CZ level, so the aggregation is just defining what "high-exposure" means. Use a median-or-higher cutoff on the Eloundou score to define the high-exposure set. Robustness: repeat with top-quartile, top-decile cutoffs.

### (9) iPad: Report DD results by age group alongside DDD

Do this. Olden & Møen (2022, *Econometrics Journal*) formally decompose DDD = DD_young − DD_old. Report three columns in your main table:
- Column 1: DD_young (young-only sample, Z × Post)
- Column 2: DD_old (older-only sample, Z × Post)
- Column 3: DDD (full sample, Z × Post × Young)

This reveals the structure. If DD_old ≈ 0, the result is driven entirely by the young-worker response — the cleanest case for your theory. If DD_old is significantly negative, older workers are also affected, DDD is conservative relative to DD_young, and you have a richer story about non-age-specific displacement. If DD_old is significantly *positive* (older workers doing better in high-$Z$ CZs), you have the ideal displacement-vs-complementarity pattern: AI displaces young workers *and* complements experienced ones. Any of these stories can be published; what matters is you see and explain which one your data tells.

Include event-study plots for each column to show pre-trends.

### (10) iPad: Detail on licensing and O\*NET proxies

**O\*NET signal-reliance index (minimum viable)**: Average of z-scored Writing Importance (element `2.A.1.c`) and z-scored Critical Thinking Importance (`2.A.2.a`), both from `Skills.xlsx` with Scale ID = "IM." Direct methodological precedent: Deming (2017 QJE).

**Stronger version**: Add Work Context items for written correspondence — Written Letters and Memos (`4.C.1.a.2.j`) and Electronic Mail (`4.C.1.a.2.h`), both Scale ID = "CX" from `Work Context.xlsx`. Multiply the final z-scored average by (1 − Job Zone/5) to penalize occupations where non-text entry barriers (degrees, licensure) already dominate screening.

**Peer-review-grade**: Follow Felten, Raj, Seamans' AIOE architecture — weight O\*NET Abilities (Written Expression `1.A.1.a.4`, Originality `1.A.1.b.2`) by their published MTurk language-modeling relatedness scores.

Database version: O\*NET 30.2 (as of March 2026). Direct download: `https://www.onetcenter.org/database.html`.

**Licensing data**: Use the CPS Certifications and Licenses Supplement (available annually since January 2015), accessed via IPUMS CPS (`https://cps.ipums.org`). The key individual-level variable distinguishes government-required licenses from voluntary certifications. Aggregate to the Census OCC code as "share of employed workers in occupation o who report holding a government-required license." This gives you coverage of *all* occupations in the ACS/CPS — unlike the NCSL or KRRC/Kleiner databases, which cover only 48-77 occupations mostly in sub-baccalaureate trades.

The Census Bureau's `2018-occupation-code-list-and-crosswalk.xlsx` handles the O\*NET-SOC → Census OCC bridge. Use IPUMS harmonized OCC codes throughout. Employment-weight the O\*NET aggregations using OEWS 2022/2023 employment counts (most recent without COVID distortion).

**The hard truth about H4**: the overlap between high-AI-exposure occupations and licensed occupations is narrower than your proposal implies. The cleanest within-high-exposure contrast is: **Accountants and Auditors (high Eloundou ζ exposure, CPA licensure required for audit sign-off)** versus **Writers/Programmers/Analysts (high exposure, essentially unlicensed)**. Paralegals, teachers, and financial advisors are second-tier cases. Most of the tech/writing/analyst bulk of your high-exposure sample is unlicensed. This means H4 should be labeled as *exploratory* with limited power, not as a primary confirmatory test. Framed that way, it's still a valuable intellectual addition — an institutional texture check. Under Option 1 (CZ-level aggregate outcomes), H4 can be rescued by splitting the outcome: compute *share of young workers in licensed high-exposure occupations* and *share of young workers in unlicensed high-exposure occupations* separately, and test whether Z × Post has a differentially less negative effect on the former.

## 7. What this looks like, rewritten

Here is the backbone of the dissertation as I'd now lay it out, reflecting all of the above.

**Chapter 1. Introduction.** Motivating facts: Canaries 16%, Galdin-Silbert signal collapse, Lodefalk 5.5%. The research question becomes: *do young workers in more ex-ante GenAI-exposed U.S. local labor markets see a relative contraction in their entry into exposed occupations, and does this contraction arrive earlier than aggregate unemployment responses?*

**Chapter 2. Literature and positioning.** The three pillars: (a) allocation-margin automation literature (Jaimovich-Siu 2020 ReStat, Jaimovich et al. 2021 JME, Cortes et al. 2020, Dauth et al. 2021 — handled with proper age-specificity disclaimers); (b) GenAI exposure and adoption (Eloundou, Handa, Bick-Blandin-Deming, Humlum-Vestergaard); (c) direct GenAI-young-worker evidence (Brynjolfsson Canaries, Lodefalk, Massenkoff-McCrory). The mechanism section explicitly names two candidate channels — task displacement and signal erosion — and declares the paper a *reduced-form* test that cannot cleanly separate them. Galdin-Silbert cited as the closest existing quantification of the signal-erosion mechanism.

**Chapter 3. Identification and empirical strategy.** (Moved earlier, per itays.) The shift-share index is constructed as in Acemoglu-Restrepo / Bonfiglioli. Identification rests on *exogenous shifts* — the Eloundou scores are uncorrelated with CZ-level outcome trends conditional on controls. Pre-trend test (2015-2019) and placebo test presented. Shock-level balance tests. $Z_c$ is standardized to mean 0, SD 1.

**Chapter 4. Data.** ACS 2019 for pre-period shares, ACS 2023-2024 for post-period outcomes. (2020-2022 excluded.) CPS for wages and robustness. O\*NET 30.2 for signal-reliance proxies (specific elements as above). CPS Certifications and Licenses supplement (via IPUMS) for licensing. The primary outcome is defined at the CZ level: *share of young workers in high-exposure occupations in CZ c at time t.*

**Chapter 5. Main results.** DDD specification with $Z_c \times \text{Post}_t \times \text{Young}_a$. Three-column reporting: DD_young, DD_old, DDD. Event-study plots. Effect size framed per 1 SD of $Z_c$, per IQR, and relative to baseline. Robustness: alternative age cutoffs, alternative exposure aggregation cutoffs, alternative pre/post windows, non-tech subsample to address pre-trends.

**Chapter 6. Mechanism and heterogeneity.** H2 (entry vs. unemployment) — compare the DDD magnitudes across outcomes. H4 (licensing buffer) — split-outcome approach with licensed-vs-unlicensed high-exposure occupation groups, labeled exploratory. Signal erosion interpreted, not tested directly; Galdin-Silbert cited as the closest direct evidence. If time permits: an occupation-level DiD on job-posting data (Lightcast) as supplementary evidence for H3.

**Chapter 7. Conclusion.** The reduced-form result (whatever it is). Explicit acknowledgment that the paper identifies *consequences*, not the mechanism, and that signal erosion vs. task displacement would require a different design (job-posting screening composition, referral premia) to separate.

This gets you a coherent dissertation that can actually be defended.

## 8. A candid diagnostic

Let me say what I really think, since you asked for my own interpretation.

**The thesis is strong.** "Young-worker entry is the first margin to move" is genuinely the right question to ask in April 2026. Canaries confirms the phenomenon empirically; Galdin-Silbert provides a sharp theoretical mechanism; Lodefalk independently replicates in Swedish data. The question is correct, timely, and gettable at MSc scale if you stay disciplined.

**The shift-share was ambitious but mis-aimed.** Your instinct — that using CZ variation in pre-GenAI exposure is cleaner than using ChatGPT as a treatment — is *right*. The 2022-2023 period is contaminated by tech layoffs, rate hikes, and COVID recovery, all of which correlate with AI exposure. An SSIV design should help. But the specific implementation you chose (CZ instrument, occupation-specific outcome) violates what the method can do. The fix is not to abandon SSIV; it's to take the outcome up to the instrument's level of aggregation.

**The signal-erosion story is your most distinctive intellectual move, and also your riskiest.** No other GenAI-labor paper commits to it this explicitly. If you can pull off even a weak version of the test (H4 as the indirect check; optionally the Lightcast job-posting auxiliary analysis), you have a distinctive contribution. If you can't, demote it to interpretive framing and lean harder on the design. Either works. What doesn't work is claiming to test signal erosion while running an SSIV that only identifies aggregate contractions.

**H4 is clever but thin on power.** The licensing-buffer heterogeneity test is a legitimate mechanism-indirect check. But the cleanest high-exposure/licensed group (accountants, CPAs, lawyers, financial advisors, teachers) is small relative to the high-exposure/unlicensed bulk (programmers, writers, analysts). Label H4 exploratory. A null on H4 should not be interpreted as rejecting signal erosion — only as "our power was inadequate to detect it."

**The citation hygiene needs work.** Your current bibliography omits Canaries (the single most important paper for your thesis), Galdin-Silbert (the cleanest quantification of your mechanism), Lodefalk (a directly comparable design in Swedish data), and treats Humlum-Vestergaard (2025b) PNAS as saying something it doesn't really say. The Anthropic papers are cited as if peer-reviewed. Do one pass with these corrections and your literature section goes from adequate to current.

**Your supervisors are being honest with you.** These are substantive, well-calibrated comments. iPad's "key concern" about identification is load-bearing — if unaddressed, it sinks the paper. itays's point about signal-erosion-vs-task-displacement is the hardest to answer but the most intellectually interesting. Both reviewers are helping. Treat the revision as serious substantive work, not cosmetic response.

---

## 9. Sources

1. Acemoglu, D., & Restrepo, P. (2020). "Robots and Jobs: Evidence from US Labor Markets." *Journal of Political Economy*, 128(6), 2188-2244. https://doi.org/10.1086/705716
2. Adão, R., Kolesár, M., & Morales, E. (2019). "Shift-Share Designs: Theory and Inference." *Quarterly Journal of Economics*, 134(4), 1949-2010. https://doi.org/10.1093/qje/qjz025
3. Autor, D. H., Dorn, D., & Hanson, G. H. (2013). "The China Syndrome: Local Labor Market Effects of Import Competition in the United States." *American Economic Review*, 103(6), 2121-2168. https://doi.org/10.1257/aer.103.6.2121
4. Autor, D. H., Levy, F., & Murnane, R. J. (2003). "The Skill Content of Recent Technological Change: An Empirical Exploration." *Quarterly Journal of Economics*, 118(4), 1279-1333.
5. Bonfiglioli, A., Crinò, R., Gancia, G., & Papadakis, I. (2025). "Artificial Intelligence and Jobs: Evidence from US Commuting Zones." *Economic Policy*, 40(121), 145-194. VoxEU summary: https://cepr.org/voxeu/columns/effect-ai-adoption-jobs-evidence-us-commuting-zones
6. Borusyak, K., Hull, P., & Jaravel, X. (2022). "Quasi-Experimental Shift-Share Research Designs." *Review of Economic Studies*, 89(1), 181-213. https://doi.org/10.1093/restud/rdab030
7. Borusyak, K., Hull, P., & Jaravel, X. (2025). "A Practical Guide to Shift-Share Instruments." *Journal of Economic Perspectives*, 39(1), 181-204. https://doi.org/10.1257/jep.20231370
8. Brynjolfsson, E., Chandar, B., & Chen, R. (2025). "Canaries in the Coal Mine? Six Facts about the Recent Employment Effects of Artificial Intelligence." Stanford Digital Economy Lab. https://digitaleconomy.stanford.edu/publications/canaries-in-the-coal-mine/
9. Brynjolfsson, E., Chandar, B., & Chen, R. (2026, February 9). "Canaries, Interest Rates, and Timing: More on the Recent Drivers of Employment Changes for Young Workers." Stanford Digital Economy Lab blog.
10. Chen, D., Kane, C., Kozlowski, A., Kunievsky, N., & Evans, J. (2025). "The (Short-Term) Effects of Large Language Models on Unemployment and Earnings." arXiv:2509.15510. https://arxiv.org/abs/2509.15510
11. Cortes, G. M., Jaimovich, N., Nekarda, C. J., & Siu, H. E. (2020). "The Dynamics of Disappearing Routine Jobs: A Flows Approach." *Labour Economics*, 65, 101823. https://doi.org/10.1016/j.labeco.2020.101823
12. Dauth, W., Findeisen, S., Südekum, J., & Wößner, N. (2021). "The Adjustment of Labor Markets to Robots." *Journal of the European Economic Association*, 19(6), 3104-3153. https://doi.org/10.1093/jeea/jvab012
13. Deming, D. J. (2017). "The Growing Importance of Social Skills in the Labor Market." *Quarterly Journal of Economics*, 132(4), 1593-1640. https://doi.org/10.1093/qje/qjx022
14. Eloundou, T., Manning, S., Mishkin, P., & Rock, D. (2023). "GPTs are GPTs: An Early Look at the Labor Market Impact Potential of Large Language Models." arXiv:2303.10130. https://arxiv.org/abs/2303.10130
15. Felten, E., Raj, M., & Seamans, R. (2018). "A Method to Link Advances in Artificial Intelligence to Occupational Abilities." *AEA Papers and Proceedings*, 108, 54-57.
16. Frank, M. R., Javadian Sabet, A., Simon, L., Bana, S. H., & Yu, R. (2026). "AI-exposed jobs deteriorated before ChatGPT." arXiv:2601.02554.
17. Galdin, A., & Silbert, J. (2025). "Making Talk Cheap: Generative AI and Labor Market Signaling." arXiv:2511.08785. https://arxiv.org/abs/2511.08785
18. Goldsmith-Pinkham, P., Sorkin, I., & Swift, H. (2020). "Bartik Instruments: What, When, Why, and How." *American Economic Review*, 110(8), 2586-2624. https://doi.org/10.1257/aer.20181047
19. Gschwendt, C. (2022). "Routine Job Dynamics in the Swiss Labor Market." *Swiss Journal of Economics and Statistics*, 158, 1-21. https://doi.org/10.1186/s41937-022-00103-6
20. Handa, K., Tamkin, A., McCain, M., et al. (2025). "Which Economic Tasks are Performed with AI? Evidence from Millions of Claude Conversations." arXiv:2503.04761.
21. Hampole, M., Papanikolaou, D., Schmidt, L., & Seegmiller, B. (2025). "Artificial Intelligence and the Labor Market." NBER WP 33509.
22. Humlum, A., & Vestergaard, E. (2025a). "Large Language Models, Small Labor Market Effects." NBER WP 33777. Revised title: "Still Waters, Rapid Currents: Early Labor Market Transformation under Generative AI." https://www.nber.org/papers/w33777
23. Humlum, A., & Vestergaard, E. (2025b). "The Unequal Adoption of ChatGPT Exacerbates Existing Inequalities Among Workers." *PNAS*, 122(1), e2414972121. https://doi.org/10.1073/pnas.2414972121
24. Jaimovich, N., & Siu, H. E. (2020). "Job Polarization and Jobless Recoveries." *Review of Economics and Statistics*, 102(1), 129-147. https://doi.org/10.1162/rest_a_00875
25. Jaimovich, N., Saporta-Eksten, I., Siu, H. E., & Yedid-Levi, Y. (2021). "The Macroeconomics of Automation: Data, Theory, and Policy Analysis." *Journal of Monetary Economics*, 122, 1-16. NBER WP 27122.
26. Kleiner, M. M., & Krueger, A. B. (2013). "Analyzing the Extent and Influence of Occupational Licensing on the Labor Market." *Journal of Labor Economics*, 31(S1), S173-S202.
27. Lodefalk, M., Löthman, S., Koch, A., & Engberg, E. (2026). "Same Storm, Different Boats: Generative AI and the Age Gradient in Hiring." Örebro University School of Business Working Paper 2026:2. https://www.oru.se/globalassets/oru-sv/institutioner/hh/workingpapers/workingpapers2026/wp-2-2026.pdf
28. Massenkoff, M., & McCrory, P. (2026). "Labor Market Impacts of AI: A New Measure and Early Evidence." Anthropic Research. https://www.anthropic.com/research/labor-market-impacts
29. Mohnen, P. (2023). "The Impact of the Retirement Slowdown on the U.S. Youth Labor Market." *Journal of Labor Economics*, 41(3). https://doi.org/10.1086/725874
30. Olden, A., & Møen, J. (2022). "The Triple Difference Estimator." *The Econometrics Journal*, 25(3), 531-553. https://doi.org/10.1093/ectj/utac010
31. Spence, M. (1973). "Job Market Signaling." *Quarterly Journal of Economics*, 87(3), 355-374.
32. Tamkin, A., & McCrory, P. (2025). "Estimating AI Productivity Gains from Claude Conversations." Anthropic Research. https://www.anthropic.com/research/estimating-productivity-gains

---

## 10. Open questions for future research tasks

These are questions that fell outside the scope of this review but would be genuinely useful to investigate next.

1. **Does Lightcast/Burning Glass data at your institution support the H3 screening-composition test?** Specifically: can you construct, from their job-posting microdata, a DiD on (credential-requirements × post-ChatGPT × writing-reliant) with sufficient power? This is the one way to directly test signal erosion, separate from your main SSIV. Check with your department's data officer.

2. **What does the Acemoglu-Restrepo pre-trend test actually show on your data for 2015-2019?** The 2015-2019 outcome trends on $Z_c$ is the single most important robustness check you will run. Its result determines whether your 2019 baseline is defensible at all. Run this first before any main result.

3. **Does the Brynjolfsson-Chandar-Chen firm-time-FE specification replicate in ACS/CPS?** Their headline 16% is a 2022-start number; their firm-time FE number is 2024-start. Your 2019 vs. 2023/24 window captures both. Could you replicate their firm-time analogue using ACS CZ-time fixed effects? This would be a serious robustness contribution.

4. **Is there a U.S. analogue to Lodefalk et al.'s Riksbank-vs-ChatGPT timing gap?** Sweden had 7 months between monetary tightening and ChatGPT; the U.S. didn't. Can you construct a cross-state analogue using state-level variation in post-2022 macro conditions? Likely no (the U.S. is one monetary area), but worth a think.

5. **Does the Galdin-Silbert (2025) design replicate on Upwork or Fiverr?** Their Freelancer.com result is clean but platform-specific. A same-design replication on a different platform would strengthen the signal-erosion evidence base — worth checking whether any authors are working on this, and whether it could be part of a post-MSc project.

6. **What is the correct U.S. equivalent of the 2024-onward window?** If the Canaries authors' own most rigorous spec places the AI-onset effect in 2024, how does this update the correct pre/post cutoff for U.S. analyses? Specifically: should the post-period be ACS 2024 only (rather than pooled 2023-2024), to avoid the 2023-tech-contraction contamination?
