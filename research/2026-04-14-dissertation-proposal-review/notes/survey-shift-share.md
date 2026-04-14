# Survey: Shift-Share Identification — What the Literature Requires and Whether This Proposal's Design Is Coherent

## Summary

The supervisor's concern is well-founded and points to a genuine structural problem in the proposal as described. The canonical shift-share literature treats the CZ as the unit of observation and requires that *both* the outcome and the treatment be measured at the same level as the instrument — namely the CZ level. The proposal's instrument Z_c is CZ-level, but the primary outcome is occupation-specific entry rates *within* CZs. This mismatch is not just a presentation issue; it creates an identification problem because there is no clean mechanism linking a CZ's aggregate AI exposure to changes in occupation-specific hiring within that CZ independently of composition effects.

There is, however, a coherent design available. The literature offers two fixable paths: (1) change the outcome to a CZ-level aggregate (e.g., the young employment rate, or the share of young workers in high-exposure occupations); or (2) build a two-dimensional panel (CZ × occupation group) with occupation × time fixed effects and a CZ-varying instrument, which requires articulating a distinct theoretical channel.

## Key Sources

### Borusyak, Hull, and Jaravel (2022/2025), "Quasi-Experimental Shift-Share Research Designs" (ReStud) and "A Practical Guide to Shift-Share Instruments" (JEP)

- **Link**: https://doi.org/10.1093/restud/rdab030 (ReStud); https://doi.org/10.1257/jep.20231370 (JEP 2025 practical guide)
- **Key content**: The core framework. BHJ show that validity of SSIV can come from *exogenous shocks* (the shifts gk are quasi-randomly assigned) even when exposure shares are endogenous. The instrument Z_i = Σ_k s_{ik} g_k is valid if and only if shocks are uncorrelated with a shock-level unobservable — the exposure-share-weighted average of the regional residuals. The equivalence result: SSIV can be re-expressed as an IV regression estimated at the shock level, where the outcome and treatment are both aggregated to the shock level using exposure shares as weights. Crucially, BHJ note this equivalence "only relies on the structure of the shift-share instrument and thus applies to outcomes and treatments that are not typically computed at the level of shocks" — but this applies to aggregation *upward* to the shock level, not to *disaggregating* the outcome *below* the instrument level.

  The JEP practical guide (2025) includes Table 1 listing ~12 canonical SS applications. In every single one, the unit of observation i is the same as the unit at which the outcome y_i is measured: regions/CZs when the outcome is a regional variable, workers when the outcome is individual wages, firms when the outcome is firm employment. The table shows Bartik (1991): region → Δlocal wage; ADH (2013): region → Δlocal manufacturing employment; Acemoglu-Restrepo (2020 via the robots literature): region → Δemployment-to-population ratio; Mohnen (2025): region → Δyoung labor market outcome. No case in the table features a sub-unit outcome (e.g., occupation-level) with a unit-level (CZ-level) instrument.

- **Assessment**: The most authoritative methodological source. Peer-reviewed, 834 citations (ReStud), 65 citations (practical guide since 2024). BHJ explicitly note that pre-period shares must be chosen carefully and the identifying variation must match the variation in the instrument.

### Goldsmith-Pinkham, Sorkin, and Swift (2020), "Bartik Instruments: What, When, Why, and How" (AER)

- **Link**: https://doi.org/10.1257/aer.20181047
- **Key content**: GSP show that a Bartik/SS instrument is equivalent to using each industry's initial share as a separate instrument and combining via GMM with growth-rate weights (Rotemberg weights). Under this "exogenous shares" view, the identifying assumption is that the pre-period employment shares are uncorrelated with the outcome's error term. The exclusion restriction is that shares affect the outcome *only through the treatment* — no direct effect. This framing makes clear why the outcome must be at the same level as the instrument: the instrument is a weighted average of shares, and the exclusion restriction must hold for the specific outcome being studied. If the outcome is occupation-specific entry within a CZ, then the exclusion restriction would require that a CZ's pre-2019 occupation mix affects young-worker entry into high-exposure occupations *only through* whatever treatment the first stage is estimating (the aggregate AI shock). But that assumption is implausible because occupation composition mechanically predicts entry composition — a CZ that has many finance jobs will have more young workers entering finance, regardless of AI.

- **Assessment**: 1,766 citations. Peer-reviewed in AER. The GSP framework particularly clarifies why the mismatch matters: when the outcome is occupation-specific but the instrument is CZ-level, the Rotemberg-weighted exclusion restrictions become very difficult to defend.

### Adão, Kolesár, and Morales (2019), "Shift-Share Designs: Theory and Inference" (QJE)

- **Link**: https://doi.org/10.1093/qje/qjz025
- **Key content**: Adão et al. focus on inference rather than identification, but their framing is revealing. They study "inference in shift-share regression designs, such as when a regional outcome is regressed on a weighted average of sectoral shocks, using regional sector shares as weights." The problem they identify — standard errors that massively underreject because residuals are correlated across regions with similar sectoral shares — is defined at the *regional outcome* level. Their model explicitly has Yi as a regional outcome. A CZ × occupation outcome would require a distinct inferential framework. Their placebo exercise uses "2000–2007 changes in employment rates and average wages for 722 Commuting Zones" — again CZ-level outcomes. They derive inference methods for the case where units i are at the same level as the instrument; their Stata/R packages (ssaggregate) also operate at the unit × shock level.

- **Assessment**: 515 citations. QJE. Extremely important for standard errors — and the proposal would need to think carefully about clustering in any case. But the mismatch problem pre-empts the inference question.

### Autor, Dorn, and Hanson (2013), "The China Syndrome" (AER)

- **Link**: https://doi.org/10.1257/aer.103.6.2121
- **Key content**: The paper that established the modern use of SS instruments in trade-labor research. The instrument is CZ-level (Σ_j [L_{cj}/L_c] × ΔM^{other}_j), and the *main outcomes are CZ-level*: change in manufacturing employment-to-population ratio, change in log hourly wages, change in labor force participation — all measured at the CZ level. ADH do report some results by demographic groups (gender, education), but always as *within-CZ heterogeneity* after the CZ is the unit of observation, not as separate outcomes at the occupation level. Their supplementary analyses (e.g., the 2016 election paper) continue to use CZ-level outcomes (county-level vote shares aggregated to CZ). The occupation composition of a CZ is used as a *control* or a *covariate*, never as the outcome dimension.

- **Assessment**: 1,351 citations. This is the paper the supervisor is likely thinking of as the reference case. It establishes exactly the standard the proposal should be held to: Z_c → outcome_c.

### Acemoglu and Restrepo (2020), "Robots and Jobs" (Journal of Political Economy)

- **Link**: https://doi.org/10.1086/705716
- **Key content**: Uses a shift-share instrument (industry-level robot adoption × CZ industry shares) to estimate the effect of automation on CZ-level employment. Main outcomes: (1) employment-to-population ratio at the CZ level; (2) log hourly wages at the CZ level (with some estimates at the demographic cell × CZ level for wages). They do break results by demographic groups — gender, age, education — but always by regressing the *same CZ-level exposure* on *CZ-level outcomes computed for each subgroup*. For example, they look at the employment-to-population ratio among manufacturing workers in each CZ. They never use occupation-specific entry rates as the dependent variable; the CZ remains the unit of analysis throughout. The paper also explicitly discusses why the shift-share gives identifying variation *at the CZ level*: "Greater use of robots in a commuting zone generates benefits for..." — all the economic channels operate at the geographic level.

- **Assessment**: 3,466 citations. This paper confirms the standard: CZ instrument → CZ-level outcomes (potentially disaggregated by subgroup but still aggregated to CZ).

### Dauth, Findeisen, Suedekum, Woessner (2021), "The Adjustment of Labor Markets to Robots" (JEEA)

- **Link**: https://doi.org/10.1093/jeea/jvab012
- **Key content**: Uses a shift-share instrument for robot exposure at the regional level (German labor markets) to study *heterogeneous* effects. Their key finding relevant to the proposal: "The incidence mostly falls on young workers just entering the labor force." But crucially, they still use regional-level outcomes: employment by age group, wages, manufacturing employment. They break down the effect *by worker type* (young vs. incumbent), but their regression is still at the region level. Their finding that young *entrants* are most affected is exactly the motivation for the proposal — but Dauth et al. achieve this by computing outcome variables at the region level for each subgroup separately, not by using occupation-specific entry rates as the left-hand side.

  The companion 2018 working paper reports results using individual-level panel data matched to regions — a different level of analysis entirely. Neither version uses occupation-group-specific entry rates as outcomes while using a CZ-level instrument.

- **Assessment**: 388 citations. JEEA. This paper is methodologically closest to what the proposal wants to do and demonstrates the correct way to study young-worker effects: keep the instrument at the CZ level, disaggregate the outcome by demographic/age group but still aggregate it to the CZ.

### Bonfiglioli, Crinò, Gancia, Papadakis (2023), "Artificial Intelligence and Jobs: Evidence from US Commuting Zones" (CESifo WP 10685)

- **Link**: https://www.ifo.de/DocDL/cesifo1_wp10685.pdf
- **Key content**: Directly relevant benchmark. Studies AI's effect on employment using a shift-share instrument that combines industry-level AI adoption with CZ industry shares — structurally identical to the proposal's Z_c. Their outcomes are all CZ-level: "We estimate robust negative effects of AI exposure on employment across commuting zones." They examine heterogeneity by skill group, wage quintile, and gender — but always as CZ-level subgroup employment aggregates, never as occupation-specific entry rates. They note that AI affects employment "through services more than manufacturing" and that "employment effect is especially negative for low-skill and production workers, while it turns positive for workers at the top of the wage distribution." This is a direct model for how the proposal should be structured.

- **Assessment**: Working paper (CESifo, 2023). Methodologically careful, follows the canonical template exactly. This is the most direct methodological precedent for the proposal.

### Brynjolfsson, Chandar, and Chen (2025), "Canaries in the Coal Mine?" (Stanford Digital Economy Lab)

- **Link**: https://digitaleconomy.stanford.edu/publications/canaries-in-the-coal-mine/
- **Key content**: Uses ADP payroll microdata to study employment effects of AI on young workers. Documents a 16% relative employment decline for workers aged 22-25 in AI-exposed occupations, with experienced workers stable. Their design is *not* a shift-share; it's a difference-in-differences at the worker/firm-occupation level, controlling for firm-time effects. Key finding: "Adjustments occur primarily via employment rather than compensation" and "results are robust to excluding technology firms and occupations that are remotable." The paper confirms empirically that young workers in high-AI-exposure occupations are the most affected group — substantiating the motivation for the proposal's question. But they use individual-level or firm-occupation-level variation, not a CZ instrument.

  Their firm-time fixed effects design is instructive: by holding firm constant and comparing workers in different occupation cells within firms, they can identify occupation-specific effects cleanly. This is the kind of design that could support occupation-specific outcomes.

- **Assessment**: Not yet peer-reviewed (working paper). High quality — ADP data is rare. Provides strong substantive motivation for the proposal but uses a different identification strategy.

### Anthropic Economic Index (Massenkoff and McCrory, 2026), "Labor Market Impacts of AI: A New Measure and Early Evidence"

- **Link**: https://www.anthropic.com/research/labor-market-impacts
- **Key content**: Studies unemployment and hiring rates by occupation-level AI exposure using CPS data. Key relevant finding: "We find that the unemployment rate for young workers in the exposed occupations is flat. But slowed hiring may not necessarily manifest as increased unemployment..." They measure the *job finding rate* (entering a new job in a more vs. less exposed occupation) for young workers — which is exactly the "occupational entry" outcome the proposal wants. Critically, this is done at the occupation level, with workers as the unit of observation, not at the CZ level. There is no CZ-level variation used. They find "a 14% drop in the job finding rate compared to that in 2022 in the exposed occupations" (barely significant). Their design is a DiD comparing across occupation exposure groups over time.

- **Assessment**: Anthropic research report (not peer-reviewed). Directly studies occupational entry for young workers and finds weak effects, using occupation-level exposure as variation. Different design from what the proposal attempts but directly targets the same outcome.

### Borusyak, Hull, and Jaravel (2025), Practical Guide, Table 1 — Mohnen (2025) example

- **Link**: cited in the practical guide (JEP 39(1), 2025), Mohnen (2025) published in Journal of Labor Economics
- **Key content**: The Mohnen (2025) study in the practical guide's Table 1 is a critical reference: it studies "Δ young labor market outcome" as the dependent variable, using a CZ-level shift-share instrument based on the age composition of the older population (predicting retirement rates). The outcome "unemployment rate, share working in high-skilled jobs" for young workers is still measured at the *CZ level* — it's Δ(young workers' outcomes aggregated to CZ), not young workers' occupation-specific entry rates. This is the clean model for what the proposal should do.

- **Assessment**: Peer-reviewed (JoLE), endorsed by BHJ in JEP 2025. Confirms that CZ-level outcome for a specific demographic group is valid when the instrument is CZ-level.

## Landscape Assessment

### State of Knowledge

The three canonical methodological papers (BHJ, GSP, AKM) establish a clear standard: the outcome must be measured at the same level as the instrument. The instrument Z_c is CZ-level. The entire literature — without exception — uses CZ-level outcomes when the instrument is CZ-level. This is not just convention; it reflects the logic of identification. The instrument creates quasi-random variation across CZs in aggregate AI exposure. This variation can be used to identify causal effects on *any CZ-level outcome*. It cannot directly identify causal effects on occupation-specific outcomes within CZs because there is no independent variation at that level from the instrument alone.

### Where Sources Agree

All sources agree that:
1. The canonical design requires outcome and instrument at the same level (CZ × CZ)
2. Young workers are the demographic group most affected by AI/automation (Dauth et al., Brynjolfsson et al., Anthropic)
3. The substantive question — do high-AI-exposure local markets see lower entry of young workers into exposed occupations — is interesting and real
4. Robustness checks often break out results by demographic group, but at the CZ level

### The Specific Problem the Supervisor Identifies

The supervisor's question is precise: "why occupation composition affects the entry specifically to high-exposure occupations?" Here is the structural diagnosis:

The proposal seems to want to run something like:
entry_{c,o,t} = α + β Z_c + γ_{o,t} + ε_{c,o,t}

where entry_{c,o,t} is the fraction of young workers entering occupation o in CZ c at time t, and Z_c is the CZ-level AI exposure. But Z_c does *not* vary across occupations within a CZ. So the identification would come from comparing, across CZs with different Z_c, entry rates into the same occupation o. The concern:

- A CZ with high Z_c (many AI-exposed jobs) might see lower young-worker entry into *all* occupations, not specifically into exposed ones, if the general labor market is depressed.
- The effect of Z_c on entry into high-exposure occupations vs. low-exposure occupations within the same CZ is not identified by cross-CZ variation in Z_c alone.
- To distinguish "young workers being blocked from entering exposed occupations" from "young workers in exposed CZs doing worse overall," you'd need occupation × CZ interaction variation — which the CZ-level instrument does not provide.

The composition effect point is also sharp: a CZ that has more AI-exposed jobs mechanically has more scope for "entry into high-exposure occupations" to decline, not because AI is causing anything, but because there were more high-exposure jobs to begin with. This would show up as a spurious positive reduced-form correlation.

### What Would Fix the Design

**Option 1 — Match the outcome to the instrument level.** Change the outcome to a CZ-level aggregate. Following Dauth et al. (2021) and Mohnen (2025), the outcome could be: employment-to-population ratio for young workers (ages 18-25) in CZ c; share of young workers employed in any occupation; or share of young workers employed in high-AI-exposure occupations (as a CZ-level share). This last one is interesting and close to the proposal's intent — but crucially, it aggregates to the CZ level. With this design, Z_c → share of young workers in high-exposure jobs in CZ c, which is coherent: a CZ more exposed to AI faces stronger automation pressure, which reduces demand for entry-level workers in those occupations, lowering the young workers' share in them.

**Option 2 — Run a CZ × occupation group panel with a double-interaction instrument.** If you want to retain the occupation-specific dimension, you need a different instrument structure. Following the heterogeneous-effects literature (e.g., ADH's analysis by demographic group), you could build a panel where the unit is (CZ × occupation group) and construct a *separate* instrument for each occupation group: Z_{c,o} = s_{c,o,pre} × g_o (which is essentially just the two-way fixed effects version of the treatment itself, raising an obvious first-stage problem). Or you could use a double-interaction Bartik where the shift is g_o (occupation-level AI exposure) and the share is s_{c,o,pre} (occupation's share in CZ c), with occupation × time and CZ × time fixed effects. But this requires articulating what exogenous variation drives g_o — and the Eloundou et al. measure is cross-sectional, not temporal. There's also a near-mechanical identification problem: the instrument Z_{c,o} is literally the product of the pre-period occupation share and the occupation-level exposure score, and the outcome (entry into occupation o in CZ c) is mechanically related to both.

**Option 3 — Abandon the shift-share instrument and use a different design.** Given the Brynjolfsson et al. and Anthropic findings are not CZ-based, a more natural design might be: occupation × time DiD, using ChatGPT's rollout as the shock and occupation-level AI exposure as the treatment, with the outcome being occupation-level entry rates nationally. This is conceptually cleaner and avoids the level mismatch.

### Gaps and Under-Explored Areas

- There are essentially no published papers that use a CZ-level SS instrument with occupation-specific entry rates as the outcome. The closest are the demographic-group breakouts in ADH (2013) and Dauth (2021), but these remain CZ-level.
- The GSP framework's Rotemberg weight diagnostic could in principle be applied to the mismatch case, but no published work does this.
- The question of whether AI reduces *occupational entry* specifically (vs. overall employment) is genuinely new and the proposal's substantive contribution is real — the design problem is methodological, not conceptual.

### Surprises

- The Anthropic Economic Index paper (2026) is directly measuring young-worker entry rates into high-vs-low AI-exposure occupations using CPS data, finding suggestive but weak effects. The proposal's outcome variable is essentially what Anthropic is measuring, but Anthropic uses occupation-level variation, not CZ-level.
- The Mohnen (2025) paper — cited approvingly in BHJ's own practical guide — provides a clean model: study young workers' *CZ-level outcomes* (unemployment, skill mix) using a CZ-level SS instrument. This is the paper the proposal should explicitly cite and follow structurally.
- The ifo paper (Bonfiglioli et al., 2023) is structurally the closest published precedent using AI (not robots) and CZ data. They use CZ-level employment aggregates throughout. The proposal should follow their template exactly.
