# Deep Dive: Mohnen (2025) as a Template for the GenAI Shift-Share Design

## Question

Does Mohnen (2025) — "The Impact of the Retirement Slowdown on the U.S. Youth Labor Market," Journal of Labor Economics — work as a template for the proposal's GenAI shift-share instrument Z_c = Σ_o s_{o,c,2019} × g_o, where shares are 2019 CZ-level occupation employment and shocks are Eloundou et al. (2023) GenAI exposure scores? Specifically: does Mohnen's instrument structure actually map onto the proposal's setup, or does it belong to a fundamentally different identification strategy?

## Investigation

### Step 1: What Mohnen actually does

Mohnen (JoLE 2023, cited as 2025 in Borusyak et al. JEP because of publication timing) studies how the retirement slowdown among older Americans affected youth labor market outcomes, analyzed at the commuting zone (CZ) level. The full citation is: Paul Mohnen, "The Impact of the Retirement Slowdown on the U.S. Youth Labor Market," *Journal of Labor Economics* 41(3), July 2023. DOI: 10.1086/725874.

**Outcome variable.** Ten-year changes in youth (ages 22–30) labor market outcomes at the CZ level: the share employed in high-skill vs. low-skill jobs, wages, share overeducated for their job, job mobility, unemployment rate. This is a CZ-level aggregate outcome — not occupation-specific entry rates.

**Treatment variable.** The ten-year retirement rate (change in 55+ employment rate) in the CZ.

**Instrument structure.** Mohnen constructs a Bartik-style instrument by interacting:
- Shares: s_{k,c} = (population aged k in CZ c) / (total population aged 45–80 in CZ c), for each age group k from 45 to 80. Shares sum to one within each CZ.
- Shifts: g_k = national ten-year retirement rate at age k.

So: Z_c = Σ_k s_{k,c} × g_k

The identifying variation comes from cross-CZ differences in the **age composition of the older population**. Because Americans retire at specific ages (concentrated in their 60s), CZs with a larger share of the older population currently in their late 50s will experience more retirement outflows over the next decade. The instrument is shown to be pre-determined: a substantial fraction of variation in age composition at the start of a period is explained by historical birth cohort patterns from decades earlier.

**Time dimension.** The analysis uses a panel of CZ-by-decade observations from 1980 to 2017 (four 10-year periods). Importantly, the shares s_{k,c} are **time-varying**: they are updated at the start of each decade because age composition evolves across periods. The shifts g_k are also implicitly time-varying in that national retirement rates by age vary somewhat across decades, though the identifying content comes primarily from cross-CZ variation in age composition within each decade. Borusyak et al. (JEP 2025) note that the time dimension is suppressed in their Table 1 summary "except where it is central to the design."

**Identification logic.** This is an **exogenous shares** design. Borusyak, Hull, and Jaravel (2025, JEP 39(1): 181–204) explicitly classify it under their "Exogenous Shares in Practice" section (pp. 201–202), and use it as one of two extended case studies illustrating the exogenous-shares framework. The identification assumption is that the age shares s_{k,c} are all valid instruments, conditional on controls. The shares are "tailored" to the treatment: they measure only the CZ's age composition, not generic industry mix, so they cannot plausibly capture other labor demand shocks the way industry employment shares can.

The key robustness tools in Mohnen: Rotemberg weights (showing which age-group shares drive the estimate), overidentification tests across individual age-share instruments, and an alternative single instrument using only the share of 52–59 year-olds. All converge on the same estimate.

### Step 2: How the proposal's design differs structurally

The proposal constructs: Z_c = Σ_o s_{o,c,2019} × g_o

where s_{o,c,2019} is the 2019 share of CZ c's employment in occupation o, and g_o is Eloundou et al.'s (2023) static GenAI exposure score for occupation o.

**Number of shifts (K).** Eloundou et al. score ~1,000 detailed O*NET occupations. This gives K ≈ 1,000 shifts — many enough to satisfy the "many shifts" requirement for the exogenous-shifts approach (if that approach is used). Mohnen has K ≈ 35 age groups (45 to 80), which is more modest but sufficient under the exogenous-shares framework since the identifying content is in the shares, not the number of shifts.

**Nature of shifts.** Mohnen's shifts g_k are empirical national retirement rates by age — they have genuine time variation across decades and natural predictive power from demographic regularities. Eloundou's g_o are **static cross-sectional scores** constructed from GPT-4 task analysis at a single point in time (2023), with no time dimension. They are not "shocks" in the usual sense; they do not vary over time. They are an ex ante prediction of GenAI exposure, not a realized shock.

**Nature of shares.** Mohnen's shares are age composition within the 45+ population — "tailored" to the specific mechanism (retirement through aging). The proposal's shares are industry-by-occupation employment composition, which are "generic" in the Borusyak et al. taxonomy: they capture exposure to any occupation-level shock, not just GenAI. Borusyak et al. explicitly contrast tailored shares (like Card's migrant-origin shares, like Mohnen's age shares) against generic industry shares (like ADH 2013 or Acemoglu-Restrepo 2020). The proposal's occupation shares fall into the generic category.

**Identification path.** Mohnen: exogenous shares → the age shares are pre-determined and tailored. Proposal: cannot credibly claim exogenous shares (occupation employment shares in 2019 reflect a decade of prior demand shocks). Cannot credibly claim exogenous shifts either (g_o is a single cross-section, not a quasi-random assignment of shocks across occupations). The proposal is in the same structural position as Acemoglu-Restrepo (2020) robots: generic industry/occupation shares, single cross-sectional shock measure, identification resting on the claim that the shock measure is itself exogenous to CZ-level trends.

**Outcome level.** Mohnen's outcome (young workers' job quality in CZ c) is at the same geographic level as the instrument. The proposal also targets CZ-level outcomes — so on this dimension there is alignment. However, the survey characterized Mohnen as recommending "CZ-level aggregate outcomes rather than occupation-specific entry." This is accurate (Mohnen uses CZ aggregates), but the reason to use CZ aggregates in the proposal is not because Mohnen does — it is because with a CZ-level instrument, occupationally-disaggregated outcomes would generate a measurement-level mismatch and require controlling for selection into occupations separately.

### Step 3: What Borusyak, Hull, and Jaravel (2025) actually say

The paper is published as: Kirill Borusyak, Peter Hull, and Xavier Jaravel, "A Practical Guide to Shift-Share Instruments," *Journal of Economic Perspectives* 39(1), Winter 2025, pp. 181–204. DOI: 10.1257/jep.20231370. There is also an NBER working paper version (NBER WP 33236, December 2024). The LSE repository copy confirms the JEP publication.

Table 1 (p. 184–185) lists Mohnen (2025) as one of ~12 historical examples of shift-share instruments, with the entry:
- Unit (i): Region
- Outcome (y_i): Δ Young labor market outcome
- Treatment (x_i): Retirement rate
- Level of shift variation (k): Age group (within 45+)
- Share (s_{ik}): Population_{ik} / Population 45+_i
- Shift (g_k): National retirement rate at age k

This is factually correct. Borusyak et al. then use Mohnen as one of only two extended case studies illustrating the **exogenous shares** approach (the other is Card 2009 / Goldsmith-Pinkham et al. 2020 on immigration). The Mohnen case study occupies roughly the final two pages (pp. 201–202) of the exogenous-shares practicum section.

So: the survey's claim that "Borusyak et al. endorse Mohnen as an exemplar" is **technically correct** — Mohnen is one of two extended examples — but the framing is misleading for the proposal, because Mohnen exemplifies the *exogenous-shares* path, not the *exogenous-shifts* path. The proposal's design, with generic occupation shares, cannot cleanly use either path as implemented in Mohnen.

### Step 4: What the right template is

The proposal's structural setup — industry/occupation employment shares interacted with a technology-shock measure — is the **exogenous shifts** family, not exogenous shares. The exact templates are:

**Primary template: Acemoglu and Restrepo (2020), "Robots and Jobs: Evidence from US Labor Markets," JPE 128(6): 2188–2244.**
- Instrument: Z_c = Σ_i s_{i,c,pre} × robot_exposure_i (industry employment shares × European robot adoption by industry)
- Outcome: change in CZ employment-to-population ratio and wages
- Identification: exogenous shifts. European robots are used as the shift because they are driven by supply-side automation decisions in European industries, uncorrelated with US labor demand shocks. The shares (US industry employment) are generic and acknowledged as such; identification rests entirely on shift exogeneity.
- Key diagnostic: pre-trend test (no differential employment trends 1970–1990 in areas later exposed to robots), shift-level balance on industry characteristics.
- **Direct structural analogue to the proposal.** Replace industry shares with occupation shares, replace robot exposure with Eloundou GenAI scores.

**Close second: Autor, Dorn, and Hanson (2013), "The China Syndrome," AER 103(6): 2121–2168.**
- Same generic-shares, exogenous-shifts structure. Shift instrument: growth in Chinese imports to other high-income countries (not the US). Outcome: CZ manufacturing employment and wages.
- The proposal's key challenge — there is no clean "non-US" GenAI exposure measure available — means this template's approach of instrumenting the shift itself may not transfer directly.

**GenAI-specific template: Bonfiglioli, Crinò, Gancia, and Papadakis (2024/2025), "Artificial Intelligence and Jobs: Evidence from US Commuting Zones," Economic Policy 40(121): 145–194.**
- Instrument: shift-share combining industry-level AI adoption (nationally) with pre-adoption CZ industry employment shares
- The "shifts" are industry-level growth in AI-related occupations nationally — time-varying over 2000–2010 and 2010–2020 (panel)
- Outcome: CZ employment-to-population rate (level and change)
- This is the closest existing template: CZ outcomes, AI exposure measure, Acemoglu-Restrepo framework applied to AI
- Critical difference from the proposal: Bonfiglioli et al. have panel data (two decades) and construct time-varying shifts from actual realized AI adoption; the proposal has static Eloundou scores at a single cross-section.

**Mann and Püttmann (2018), "Benign Effects of Automation: New Evidence from Patent Texts," Review of Economics and Statistics.**
- Automation patent exposure by CZ, using foreign patent grants as instrument for domestic adoption
- Outcome: CZ employment growth
- Useful template for how to argue that a technology-shock measure is exogenous

### Step 5: The specific identification challenge the proposal must address

With Eloundou et al. as the shifts g_o, the proposal faces an identification problem that Mohnen does not. Eloundou scores are constructed by GPT-4 evaluating how much GenAI could assist with each O*NET task — they are not a realized shock but a predicted potential. There is no "natural experiment" in their construction. The identification assumption is: after conditioning on CZ-level controls, Z_c = Σ_o s_{o,c,2019} × g_o is uncorrelated with the error in the CZ-level outcome regression. This requires:
1. The shares s_{o,c,2019} (occupation employment composition in 2019) were not themselves determined by anticipation of GenAI.
2. The scores g_o do not proxy for other occupation-level characteristics that predict CZ outcome trends.

Concern (1) is mild: 2019 is pre-ChatGPT (November 2022), so CZs had not yet reorganized employment toward or away from exposed occupations.

Concern (2) is more serious: GenAI exposure scores correlate with skill, routine-ness, cognitive task content, and wage level. CZs with high Z_c are likely already different on pre-trends in wages, education, and employment composition. The proposal needs a pre-trend test: show that CZ outcome trends in 2015–2019 (or across 2010–2019) are uncorrelated with Z_c conditional on controls. Acemoglu and Restrepo (2020) show this explicitly for robots (no trend pre-1990 in later-exposed CZs).

Mohnen doesn't face this problem because the age composition instrument has a clean pre-determination story (driven by birth cohorts from 20–40 years earlier, before any GenAI or retirement policy shock could have contaminated it). The proposal must work harder to tell a comparable pre-determination story.

## Key Findings

- **Mohnen (2023/2025) is real and correctly identified.** Full title: "The Impact of the Retirement Slowdown on the U.S. Youth Labor Market," JoLE, July 2023. DOI: 10.1086/725874. (Strong evidence — abstract confirmed via Semantic Scholar and conference paper.)

- **Mohnen's instrument uses age-group shares within the 45+ population, not occupation shares.** Shifts are national retirement rates by age group; shares are CZ age composition among the 45–80 population. This is a time-varying panel design (1980–2017). (Strong evidence — read from conference paper PDF and Borusyak et al. case study.)

- **Mohnen is an exogenous-shares exemplar, not an exogenous-shifts exemplar.** Borusyak et al. (JEP 2025) place it explicitly in their "Exogenous Shares in Practice" section, using it as one of two extended case studies for that path. (Strong evidence — confirmed by reading the Borusyak guide PDF.)

- **The proposal's design is structurally an exogenous-shifts design, not exogenous-shares.** Its occupation employment shares are "generic" in the Borusyak taxonomy (they capture exposure to any occupation-level shock), and identification must rest on the claim that Eloundou shifts g_o are exogenous. (Strong evidence — direct application of Borusyak et al.'s taxonomy.)

- **Acemoglu and Restrepo (2020) is the correct primary template.** Borusyak et al. explicitly classify it under the exogenous-shifts path (with generic industry shares), and it has the same logical structure as the proposal. (Strong evidence.)

- **Bonfiglioli et al. (2024/2025) is the most direct AI-specific template.** They implement an Acemoglu-Restrepo framework applied to AI at the CZ level. However, they have panel data with time-varying shifts; the proposal has static cross-sectional exposure scores. (Moderate evidence — read from VoxEU summary; full paper paywalled.)

- **The proposal's single cross-sectional shock (Eloundou) creates an identification challenge Mohnen does not face.** Pre-trend testing is the key robustness requirement; the proposal has no "natural experiment" equivalent to Mohnen's birth-cohort pre-determination. (Strong evidence from application of econometric principles; speculative as to how severe the bias will be.)

- **Borusyak et al. do endorse Mohnen as an exemplar — but for the wrong framework for the proposal.** The survey's characterization is not false, but it is misleading: applying Mohnen as a template without noting that it is an exogenous-shares design would send the proposal down the wrong identification path. (Strong evidence.)

## Assessment

Mohnen (2025) does **not** work as a clean template for the proposal's GenAI shift-share design. The structural mismatch is fundamental, not superficial.

Mohnen uses tailored, pre-determined age-composition shares that identify the instrument under the exogenous-shares logic. The proposal uses generic occupation employment shares that, as Borusyak et al. explicitly note, cannot support an exogenous-shares argument because they capture exposure to any occupation-level shock. Mohnen is placed by Borusyak et al. in the exogenous-shares case study section; the proposal belongs in the exogenous-shifts section alongside Autor-Dorn-Hanson (2013) and Acemoglu-Restrepo (2020).

Two things in Mohnen do transfer: (a) using CZ-level aggregate outcomes rather than occupation-specific outcomes (this is the correct level for a CZ-level instrument regardless of what framework is used), and (b) the Rotemberg weights diagnostic and overidentification test are useful robustness tools that the proposal can adopt. But the core identification logic is different.

The right template is Acemoglu and Restrepo (2020) — same generic occupation/industry shares, same technology-shock shifts, same CZ-level outcome. The proposal should cite and justify its design primarily against that template, with Bonfiglioli et al. (2024/2025) as the AI-specific parallel. If the proposal wants to invoke Mohnen, it should do so narrowly for the level-of-analysis point (CZ aggregates), not for the identification strategy.

The key unresolved vulnerability: Eloundou scores are static and correlated with existing occupation characteristics (skill, routine task content, wage level). The proposal needs a pre-trend test — showing that CZ outcome trends in the pre-GenAI period are uncorrelated with Z_c — to be credible. Acemoglu and Restrepo provide the blueprint for this test.

---

**Sources**

- Paul Mohnen (2023). "The Impact of the Retirement Slowdown on the U.S. Youth Labor Market." *Journal of Labor Economics* 41(3). DOI: 10.1086/725874. Conference paper (2019): https://conference.nber.org/conf_papers/f128937.pdf
- Kirill Borusyak, Peter Hull, Xavier Jaravel (2025). "A Practical Guide to Shift-Share Instruments." *Journal of Economic Perspectives* 39(1): 181–204. DOI: 10.1257/jep.20231370. LSE preprint: https://eprints.lse.ac.uk/127403/1/borusyak-et-al-2025-a-practical-guide-to-shift-share-instruments.pdf
- Tyna Eloundou, Sam Manning, Pamela Mishkin, Daniel Rock (2023). "GPTs are GPTs: An Early Look at the Labor Market Impact Potential of Large Language Models." arXiv:2303.10130.
- Daron Acemoglu, Pascual Restrepo (2020). "Robots and Jobs: Evidence from US Labor Markets." *Journal of Political Economy* 128(6): 2188–2244. DOI: 10.1086/705716.
- Alessandra Bonfiglioli, Rosario Crinò, Gino Gancia, Ioannis Papadakis (2025). "Artificial Intelligence and Jobs: Evidence from US Commuting Zones." *Economic Policy* 40(121): 145–194. CEPR DP18495. VoxEU summary: https://cepr.org/voxeu/columns/effect-ai-adoption-jobs-evidence-us-commuting-zones
- David Autor, David Dorn, Gordon Hanson (2013). "The China Syndrome." *American Economic Review* 103(6): 2121–2168.
- Katja Mann, Lukas Püttmann (2018). "Benign Effects of Automation: New Evidence from Patent Texts." *Review of Economics and Statistics*.
