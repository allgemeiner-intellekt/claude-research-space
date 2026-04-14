# Deep Dive: Magnitude of Beta, DD vs DDD, and H4 Under the Option 1 Fix

## Question

Three supervisor questions that no survey addressed: (a) how to interpret the magnitude of β in the DDD specification; (b) the case for reporting DD alongside DDD; (c) whether H4 (licensing buffer) survives the recommended fix of switching to CZ-level aggregate outcomes.

---

## Investigation

### Q3a — Magnitude of β

#### How the canonical papers construct and report their instruments

**Autor, Dorn, Hanson (2013, AER) — the reference case.** ADH measure import exposure per worker in dollars (thousands of dollars per worker per decade). Their instrument is Σ_j [L_{cj}/L_c] × ΔM^{other}_j where ΔM^{other}_j is change in Chinese imports to other high-income countries. They do not standardize Z_c — they leave it in natural units ($000 per worker). The key magnitude statement: "a $1,000 per worker increase in import exposure over a decade reduces manufacturing employment per working-age population by 0.596 percentage points." They then contextualize by reporting how much of the total observed decline their effects explain: "rising exposure to Chinese import competition explains 33 percent of the US manufacturing employment decline between 1990 and 2000." The IQR translation: "Noting that the interquartile range in CZ-level import exposure growth in the time interval 2000 through 2007 was approximately $1,000 per worker, the column 2 point estimate implies that the share of manufacturing employees in the working-age population of a CZ at the 75th percentile of import exposure declined by −0.65 percentage points more than a CZ at the 25th percentile." This is ADH's primary interpretive move: the IQR (not 1 SD) as the scaling device. They always anchor the absolute number against the baseline rate (employment-to-population ratio ~0.29 for manufacturing).

**Acemoglu and Restrepo (2020, JPE).** Exposure variable is "change in robots per thousand workers" in a CZ (the IFR-based shift-share). They report the headline coefficient in raw units: "one more robot per thousand workers reduces the employment to population ratio by about 0.2 percentage points and wages by 0.42%." They clarify: "as a result of the US increase in robots adoption (approximately one more robot per thousand workers between 1993 and 2007), a commuting zone with a value of exposure to robots equal to the average for the United States experienced 0.37 percentage points lower employment to population ratio." The instrument is constructed in raw physical units (robots per thousand workers) and they translate back to those units for interpretation. Critical: they report effects as absolute percentage point changes in employment-to-population ratio, always against the baseline E/P ratio of approximately 0.294 (1990 mean). So a 0.37 pp effect is roughly 0.37/29.4 ≈ 1.3% relative decline. They do not use SD normalization; they use physical units and then relate to observed mean.

**Bonfiglioli et al. (2023/2024, Economic Policy).** Their AI adoption measure is the change in the employment share of AI-related occupations in a CZ (a decimal, i.e. 0.004 = 0.4pp). Their headline statement from their preferred specification: "a 1 standard deviation (s.d.) higher AIadocdt causes a reduction in Δ(L/P) by 1 percentage point (p.p.), roughly 0.56% of a s.d." They then give the counterfactual: "if the CZ with average AI adoption over the sample period (0.004) had hypothetically had no AI adoption at all, its employment-to-population ratio would have grown by 0.6 p.p. more, i.e., 20% faster than observed growth." Note that Bonfiglioli et al. use the 1 SD normalization for the headline — unlike ADH which uses the IQR. This is because their treatment variable (AI adoption share) is a unitless rate that doesn't have an obvious physical interpretation per unit. The SD normalization (β × SD_treatment → pp change in outcome) makes it comparable across specifications. For robustness, they also use the IQR: "a change in AIexpcdt by one interquartile range has a direct effect on Δ(L/P)cdt equal to a change in AIadocdt by x interquartile ranges."

**Dauth et al. (2021, JEEA).** Germany. Exposure is "change in predicted robot exposure per 1000 workers between 1994 and 2014." Like Acemoglu-Restrepo, physical units. Their main effect statement uses the 25th-to-75th percentile move: "comparing a local labor market at the 75th percentile of predicted robot exposure to a local labor market at the 25th percentile, the magnitudes imply that the highly exposed market experiences 0.155 percentage points ([4.540 − 1.438] × 0.05 = 0.155) higher employment growth, which translates into roughly 100 additional (full-time equivalent) jobs for an average region." For young workers specifically, Dauth et al. do not report a separate percentage-point effect for entrants — they report a decomposition showing that young workers who had not entered the labor market in 1994 bear the largest share of manufacturing displacement (coefficient -0.247, vs -0.249 for incumbent workers in other firms, against total -0.466). The key point: young entrants bear about 53% of the total manufacturing displacement effect. They translate the regional effect into head counts (the −1.7 workers per newly installed robot figure).

**Mohnen (2025, JoLE) — the model the proposal is asked to follow.** From the abstract: "In commuting zones where fewer older workers retire due to the initial age structure, the share of younger workers in high-skill jobs declines while the share of younger workers in low-skill jobs rises. Fewer retirements also lead to a rise in the share of younger workers who have higher educational attainment than their job typically requires, declining youth wages, and lower job mobility. Together, the results suggest that the retirement slowdown has contributed to stagnant early career outcomes in recent decades, explaining 30 percent of the rise in the share of younger workers in low-skill jobs between 1980 and 2017." Mohnen's outcome variable is the **share of younger workers in high-skill vs. low-skill jobs** at the CZ level — exactly the CZ-level aggregate outcome the shift-share survey recommended. His shift-share is based on age composition of the older population driving predicted retirement rates — a time-varying shift. For the proposal's GenAI context, Mohnen is the right template on the outcome side (CZ-level share of young workers in high-exposure occupations), but the shift source is static (Eloundou scores don't vary over time in the proposal).

#### What units does β have in the DDD specification?

The proposal's outcome: Y_{c,t,a} = entry rate of age group a workers into high-exposure occupations in CZ c at time t. The exposure variable Z_c is a weighted-average Eloundou exposure score for CZ c (ranging roughly 0–1 or normalized to some scale). β is the coefficient on Z_c × Post_t × Young_a.

**Unit interpretation:** If Z_c is measured as a raw score between 0 and 1 (the unweighted mean of Eloundou occupation exposure scores, weighted by CZ employment shares), then β has units of (change in entry rate per 1-unit change in Z_c, conditional on post period and young group). Since a 1-unit change in Z_c means moving from a CZ with 0% of its workers in AI-exposed occupations to one with 100% — an implausibly large jump — β in raw form is not interpretable. This is the core issue.

If Z_c is standardized to mean 0, SD 1 across CZs, then β has units of "percentage point change in entry rate per 1 SD increase in CZ-level GenAI exposure, conditional on the post period and for young workers relative to older workers." This is the most interpretable form.

#### What would a "meaningful" effect look like?

Anchoring against baseline: From ACS data, roughly 25–35% of young workers (ages 22–27) are employed in occupations that Eloundou et al. would classify as "high AI exposure" (above the median exposure score). Call this baseline entry rate Y_bar ≈ 0.30 (30%). A plausible β (one SD increase in Z_c, young × post DDD coefficient) of −0.03 to −0.05 percentage points of entry rate would represent a 10–17% relative decline in entry — consistent with the Brynjolfsson et al. (2025) 16% figure and the Lodefalk et al. (2026) 5.5% figure. A β of −0.01 would be substantively small (a 3% relative decline) but potentially statistically significant given sample size. A β of −0.10 would be unrealistically large and should prompt a specification check.

**The concrete prescription for the user:**

1. **Normalize Z_c to have mean 0 and SD 1 across CZs before estimation.** This makes β directly interpretable as "one SD increase in GenAI exposure is associated with β percentage point change in the entry rate."

2. **Report the SD of Z_c in raw units** in a summary statistics table. For a weighted Eloundou score, the SD is probably around 0.08–0.15 (if raw) or 1.0 (if already standardized). State explicitly what the SD corresponds to in substantive terms (e.g., "one SD corresponds to moving from the median-exposure CZ, comparable to Indianapolis, to a CZ at the 84th percentile of exposure, comparable to San Jose").

3. **Report β using three framings:**
   - Raw coefficient: "A one-standard-deviation increase in Z_c is associated with a β percentage point change in the young-worker entry rate into high-exposure occupations in the post-ChatGPT period, controlling for the differential change for older workers."
   - IQR framing (following ADH): "Moving from the 25th to the 75th percentile of Z_c is associated with a β × IQR/SD percentage point differential change."
   - Relative-to-baseline framing (following Bonfiglioli): "This represents a X% change relative to the mean young-worker entry rate of Y% in the pre-period."

4. **The comparable anchors from the literature:**
   - ADH: 0.65 pp decline in manufacturing employment share for a CZ at the 75th vs. 25th percentile of Chinese import exposure, against a baseline of ~29% employment-to-population ratio (~2.2% relative decline).
   - Acemoglu-Restrepo: 0.37 pp decline in E/P for the average US increase (1 robot per 1000 workers), against a 29.4% baseline (~1.3% relative).
   - Bonfiglioli: 1 pp decline per 1 SD of AI adoption, against a ~62% employment-to-population ratio (about 1.6% relative decline).
   - Brynjolfsson et al. (2025) Canaries: 16% relative decline in employment for 22–25-year-olds in highly exposed occupations. No shift-share — DiD design — but this gives the right order of magnitude to benchmark against.

The implication: if the user's β on a standardized Z_c implies a relative decline in entry of 5–20%, this is substantively plausible and in line with the literature. Effects much larger than 20% should be treated with suspicion (possibly a composition effect or misspecified instrument).

---

### Q3b — DD alongside DDD

#### What Olden and Møen (2022) establish about the DDD estimator

The Olden-Møen (2022, Econometrics Journal) paper gives the cleanest treatment. Their core result: DDD does NOT require two parallel trend assumptions. It only requires the **differential trend between the treatment group (young) and comparison group (old) to be the same in high-exposure CZs as in low-exposure CZs, in the absence of treatment.**

Formally: (E[Y_0|high-Z, young, post] - E[Y_0|high-Z, young, pre]) - (E[Y_0|high-Z, old, post] - E[Y_0|high-Z, old, pre]) = (E[Y_0|low-Z, young, post] - E[Y_0|low-Z, young, pre]) - (E[Y_0|low-Z, old, post] - E[Y_0|low-Z, old, pre])

This is a **single** parallel trend assumption — it's a parallel trend on the **differential** between young and old, not two separate parallel trends for young and old separately.

DDD can be decomposed as the difference between:
- DD_young (effect for young workers: Z_c × Post): the "simple" pre-post change in entry for young workers, comparing high vs. low Z_c CZs
- DD_old (effect for old workers: Z_c × Post): the same pre-post change for older workers

DDD = DD_young - DD_old.

#### What each estimator identifies

**DD for young workers only (Z_c × Post, restricted to young worker sample):**
- Identifies the total effect of being in a high-exposure CZ in the post period, for young workers
- This absorbs: (a) any uniform effect of ChatGPT on all workers in the CZ; (b) any CZ-specific shock that affects all age groups equally; (c) the differential GenAI-young effect
- Assumes: parallel trend in young-worker outcomes across high vs. low Z_c CZs absent ChatGPT

**DDD (Z_c × Post × Young):**
- Identifies the effect specifically operating **through the young-old differential**
- Uses older workers as an "internal control group" to difference out uniform CZ-level shocks
- Assumes: the young-old gap in entry rates would have trended the same in high vs. low Z_c CZs, absent ChatGPT
- What it strips out: anything that affects all age groups proportionally in high-Z CZs (e.g., if GenAI reduces total employment in high-exposure CZs for everyone, this gets differenced out)

#### The key practical implication for this proposal

The proposal's theoretical argument is that GenAI **disproportionately** affects young workers relative to older workers because: (a) young workers are more concentrated in entry-level tasks that AI can substitute; (b) the signal erosion effect hits young workers harder (they rely more on credentials/writing samples to signal ability). If this theory is right, then DDD is the correct estimator — it targets the differential effect.

But there is a risk: if older workers in high-exposure CZs ALSO reduce their entry into these occupations (e.g., experienced workers also getting displaced), DDD will understate the true effect on young workers by subtracting out what is actually a real treatment effect. In that case, DD_young > DDD because older workers show a negative DD_old that gets subtracted.

Conversely: if there are pre-existing trends making young workers in high-exposure CZs underperform anyway (perhaps high-Z CZs are coastal tech hubs where young workers were already substituting out of these roles), the DD_young might be contaminated. DDD strips that out if the older-worker trend is equally contaminated.

#### The case for reporting both

The user should report both, for four reasons:

1. **Falsification logic.** If DDD is significant and DD_old is near zero, this is strong evidence that the effect is specific to young workers, consistent with the theory. If DDD is significant but DD_old is also large and significant in the same direction, this raises questions about whether there's a uniform effect — and the supervisor will want to see DD_old explicitly to judge.

2. **Sign diagnostic.** If DD_old is positive (older workers doing better in high-Z CZs post) and DD_young is negative (young workers doing worse), the DDD will be substantially more negative than either DD alone. This pattern is actually the most theoretically appealing: GenAI displaces young workers but complements experienced workers. Showing both DDs explicitly makes this story vivid.

3. **Olden-Møen's point on spillovers.** They note that "the triple difference will provide an estimate of spillover effects, i.e., β_5 [the effect on the non-treated in the treatment state], which is the effect on older workers in high-Z CZs. This information is lost in the difference-in-differences estimator." Reporting γ_1 (the Z_c × Post coefficient) from the DDD regression — which represents the effect on older workers — gives this spillover estimate. This is interpretively rich, not just a robustness check.

4. **Parallel trend test.** The pre-period analog of DD_young serves as a parallel trend test. Present event-study plots for DD_young (year-by-year) alongside the DDD event study to show the trends in both.

**Practical reporting suggestion:** Present three columns in the main table:
- Column 1: DD for young workers only (Z_c × Post, young-only sample)
- Column 2: DD for older workers only (Z_c × Post, older-only sample)
- Column 3: DDD (full sample with Z_c × Post × Young)

The ratio β_DDD / β_DD_young tells the reader "of the total effect on young workers, how much is specifically differentially larger than the effect on older workers?" If this ratio is close to 1, the DDD and DD tell the same story. If it's much less than 1, older workers were also affected, and the DDD is more conservative. This is valuable information and a supervisor will expect to see it.

---

### Q3c — H4 Under the Option 1 Fix

#### What the Option 1 fix does to H4's design space

H4 (licensing buffer) claims: within the set of high-AI-exposure occupations, those requiring an occupational license see less entry disruption than unlicensed high-exposure occupations. The heterogeneity dimension is occupation-level licensing intensity.

Under the original design (Y_{c,t,a} as entry rate into occupation o), H4 is operationalizable: interact Z_c × Post × Young × License_o, where License_o is a binary (or share) for whether occupation o is licensed.

Under Option 1 (Y_{c,t} = share of young workers in high-exposure occupations in CZ c), the occupation dimension is collapsed into the outcome. You can no longer interact on occupation-level licensing because the occupation is no longer in the regression. H4, as stated, **does not directly survive the Option 1 fix in its original form.**

#### Three approaches to rescue H4 under Option 1

**Approach A: Split the outcome into licensed and unlicensed high-exposure occupations (best approach).**

Instead of a single outcome "share of young workers in high-exposure occupations," define two outcomes:
- Y_licensed_{c,t} = share of young workers in high-exposure, licensed occupations in CZ c at time t
- Y_unlicensed_{c,t} = share of young workers in high-exposure, unlicensed occupations in CZ c at time t

Run two regressions (or a stacked regression with a licensing-group indicator):
Y_{c,t,g} = α_c + λ_t + δ_g + β(Z_c × Post_t) + β_L(Z_c × Post_t × Licensed_g) + ...

β gives the effect on unlicensed high-exposure occupations. β + β_L gives the effect on licensed high-exposure occupations. The test of H4 is β_L > 0 (licensed occupations are more buffered, i.e., show a less negative effect).

This preserves the CZ-level outcome structure (valid under BHJ/GSP) while introducing a cross-group comparison at the outcome level. It is essentially a DDD-within-DDD: the three differences are now (CZ exposure) × (post-period) × (licensed vs. unlicensed).

**Approach B: CZ-level licensing intensity as a moderator.**

Construct a CZ-level licensing intensity variable: L_c = weighted share of high-exposure occupations in CZ c that are licensed (weighted by CZ employment shares in those occupations). Then interact:

Y_{c,t} = α_c + λ_t + β(Z_c × Post_t) + β_L(Z_c × Post_t × L_c) + ...

β_L tests: do CZs where high-exposure occupations are more heavily licensed see a smaller negative effect of Z_c in the post period?

The problem with Approach B: L_c is endogenous. CZs with more licensed high-exposure workers are likely to have different occupational composition, different regulatory environments, and different pre-existing trends. The exclusion restriction becomes very hard to defend. Additionally, if Z_c and L_c are highly correlated (both are weighted averages using the same occupation mix), there's a multicollinearity problem. Approach B is NOT recommended as the primary test.

**Approach C: Abandon the CZ-level fix for H4 specifically, use a complementary occupation-level DiD.**

Run the CZ-level DDD (Options 1 fix) as the main specification for H1–H3. For H4 specifically, run a separate occupation-level DiD that is not a shift-share:
Y_{o,t} = α_o + λ_t + β(Exposure_o × Post_t) + β_L(Exposure_o × Post_t × License_o) + ε_{o,t}

where the unit is occupation × year, Exposure_o is the Eloundou score for occupation o, and License_o is a binary for licensed occupations (from BLS CPS licensing data or from Kleiner's CPS-based measure). This is structurally similar to how Massenkoff & McCrory (2026) and the Brynjolfsson et al. design operate — at the occupation level, using occupation-level variation in AI exposure. It does not require a shift-share instrument. The identifying assumption is that licensed and unlicensed high-exposure occupations had parallel trends in young-worker entry absent ChatGPT.

**This approach is the most defensible path for H4.** It separates H4 from the main CZ-level specification, labels it as a complementary analysis, and avoids the endogeneity problem of Approach B. The cost is that the supervisor may view it as a different paper's contribution.

#### The critical empirical question: does the occupation-level licensing × exposure overlap exist?

This is the fundamental feasibility question for H4. If all high-AI-exposure occupations are unlicensed and all licensed occupations are low-exposure, H4 tests nothing.

**From the Eloundou et al. (2023) highest-exposure occupations:**
- Fully exposed (ζ measure): Accountants and Auditors, News Analysts/Reporters/Journalists, Legal Secretaries/Administrative Assistants, Clinical Data Managers, Climate Change Policy Analysts
- High exposure (β measure): Mathematicians, Blockchain Engineers, Court Reporters/Simultaneous Captioners, Proofreaders/Copy Markers
- High exposure (α measure): Interpreters and Translators, Survey Researchers, Writers and Authors, Public Relations Specialists

**From BLS CPS Table 53 (2025 annual averages) — licensing rates by broad occupation group:**
- Legal occupations: 62.2% have a license (the highest among non-healthcare groups)
- Healthcare practitioners: 75.1% have a license
- Computer and mathematical occupations: 13.3% have a license
- Arts, design, entertainment, sports, and media: 12.2% have a license
- Business and financial operations: 21.3% have a license
- Community and social services: 40.4% have a license
- Education, training, and library: 49.8% have a license

**The intersection analysis:**

High-exposure, high-licensing: Legal secretaries and administrative assistants (high ζ exposure, part of "Legal occupations" group with 62% licensing). Accountants and Auditors (high ζ exposure, part of "Business and financial operations" with 21% licensing — but CPA licensure is specifically required for auditors). Clinical Data Managers (high exposure, related to healthcare — some licensing). Interpreters and Translators (state licensing varies, some jurisdictions require court interpreter licenses).

High-exposure, low-licensing: News analysts/Reporters (~12% for arts/media group), Blockchain Engineers (~13% for computer/math), Writers and Authors (~12%), Survey Researchers, Proofreaders.

The picture: there IS meaningful overlap, but it is concentrated in a few occupational categories:
1. **Accountants and Auditors**: very high AI exposure AND a significant licensed share (CPA license is state-mandated for audit work). This is the cleanest case.
2. **Legal occupations**: some legal secretaries are AI-exposed AND some legal roles require licensing (paralegals may require certification in some states; lawyers require bar admission). However, lawyers themselves have lower AI exposure in the Eloundou α/β measures, appearing in the "fully exposed" category only under the more expansive ζ measure (legal software tools).
3. **Healthcare practitioners**: high licensing but lower AI exposure per Eloundou (tasks are physical, not written). Clinical data managers are exposed but not practitioners.
4. **Teachers**: moderate-high licensing (49.8% in education/training) and moderate AI exposure for writing-heavy prep tasks — possibly the cleanest overlap group outside accounting.

**Key finding for H4:** The hypothesis is testable but requires **narrow operationalization**. Defining "high-exposure, licensed" as accountants/auditors (especially CPAs) vs. "high-exposure, unlicensed" as writers/analysts/programmers gives meaningful within-high-exposure variation. The sample will be thin — roughly 4–5 licensing-heterogeneous occupation groups — so power will be limited. H4 should be framed as **exploratory/suggestive** rather than a primary confirmatory test.

The claim that "licensed occupations protect against AI displacement" should also grapple with the mechanism: is it licensing per se, or is it that licensed occupations require demonstrating verifiable competence (audits require sign-off, court interpreters must be certified accurate), making the AI-complementarity dynamic different? This is the theoretical distinction worth making explicit.

---

## Key Findings

**Q3a — Magnitude of β:**

1. **None of the canonical papers (ADH, Acemoglu-Restrepo, Bonfiglioli, Dauth) leave Z_c unnormalized when reporting headline effects.** ADH and Dauth use IQR-normalized effects (25th-to-75th percentile). Bonfiglioli and Acemoglu-Restrepo report "1 SD increase" or "1 unit in physical terms" with explicit unit definition. Strong evidence: the field norm is to translate β into an interpretable unit before presenting results. [Confidence: strong]

2. **Bonfiglioli's template is the closest to the proposal's setup and uses 1 SD normalization.** Their headline: "1 SD higher AI adoption → 1 pp decline in employment-to-population ratio, roughly 20% faster than observed growth." This is the three-step template: (i) state β in terms of 1 SD; (ii) give the absolute pp change; (iii) relate it to the mean baseline. [Confidence: strong, directly from the paper]

3. **The plausible range for β for the proposal:** Given Brynjolfsson et al.'s 16% relative decline and Lodefalk et al.'s 5.5%, and assuming baseline young-worker entry rate into high-exposure occupations of roughly 25–30%, a plausible β (standardized Z_c) is in the range of −0.01 to −0.05 entry rate percentage points per 1 SD of Z_c. Anything outside −0.10 to +0.03 would require a careful explanation. [Confidence: moderate — inference from comparable papers, not a direct calculation on the proposal's data]

4. **The baseline entry rate is the critical anchor.** The user must report the pre-period mean entry rate for young workers by CZ in summary statistics. Without this, no supervisor can evaluate whether β is "large" or "small." [Confidence: strong — this is methodological standard practice]

**Q3b — DD vs DDD:**

5. **Olden-Møen (2022) is clear: DDD requires ONE parallel trend assumption, not two.** The assumption is that the young-old differential trends the same across high and low Z_c CZs in the absence of treatment. This is weaker than requiring each age group to have a parallel trend separately. [Confidence: strong, directly from the paper]

6. **DD_young and DDD give different answers whenever older workers are also affected.** If older workers show a significant Z_c × Post effect (positive or negative), DDD will differ from DD_young. Whether this difference is desirable depends on the theory: if the proposal claims young workers are specifically more affected (not just more affected), DDD is the right estimator. If the claim is merely that young workers are affected (regardless of whether old workers are too), DD_young suffices. [Confidence: strong — this is the logical structure of the estimator]

7. **Reporting both is standard practice and is what the supervisor is asking for.** Olden-Møen note that "the triple difference will provide an estimate of spillover effects [on non-treated groups] which is lost in the difference-in-differences." Presenting γ_1 (the Z_c × Post coefficient for older workers, implicit in the DDD regression) separately in the table makes the logic visible. [Confidence: strong]

8. **The most informative reporting structure is three columns: DD_young, DD_old, DDD.** This shows: (i) total effect on young; (ii) effect on comparison group (falsification); (iii) differentially young-specific effect. If β_DDD ≈ β_DD_young and β_DD_old ≈ 0, the story is clean. If β_DD_old is substantial, the DDD is a more conservative estimate than the simple young-worker comparison, which is actually conservative in a way that strengthens credibility. [Confidence: strong — this follows from Olden-Møen's decomposition]

**Q3c — H4 under Option 1 fix:**

9. **H4 does not survive Option 1 as originally stated.** Collapsing to CZ-level outcomes removes the occupation dimension through which licensing varies. But H4 can be rescued via Approach A (split outcomes into licensed/unlicensed high-exposure groups). [Confidence: strong]

10. **Approach A (split outcomes) is methodologically sound.** Define Y_licensed_{c,t} and Y_unlicensed_{c,t} as separate outcomes. This is analogous to Bonfiglioli's age-group heterogeneity analysis (where they run Table 8 with separate outcomes for each age group) and is fully consistent with BHJ's framework — the CZ remains the unit of observation with a CZ-level instrument. [Confidence: strong]

11. **The licensing-AI exposure overlap exists but is limited.** The cleanest cases are: Accountants and Auditors (high AI exposure under all Eloundou measures, CPA licensure required for audit sign-off); certain legal occupations (legal secretaries/assistants have high ζ exposure and partial licensing); teachers (moderate exposure, ~50% licensed). Writers, analysts, programmers — the most AI-exposed occupations — are largely unlicensed. [Confidence: strong — from Eloundou (2023) occupation scores and BLS CPS Table 53]

12. **H4 is testable but must be labeled exploratory.** There are enough licensed/unlicensed pairs within the high-exposure group to construct the test, but statistical power will be limited (4–6 occupation groups, thin ACS cells). The proposal should frame H4 as suggestive evidence, not a primary confirmatory test. [Confidence: moderate]

---

## Assessment

**On Q3a (magnitude):** The field has a clear norm the user can follow. Standardize Z_c to mean 0, SD 1. Report β in three ways: (i) pp change per 1 SD of Z_c; (ii) 25th-to-75th percentile equivalent (multiply β by IQR/SD); (iii) relative to pre-period mean entry rate. The specific sentence template to use, directly following Bonfiglioli: "A one-standard-deviation increase in commuting zone GenAI exposure is associated with a β percentage point change in the share of young workers entering high-exposure occupations in the post-ChatGPT period, relative to older workers, controlling for time and CZ fixed effects. This represents a [β/Y_bar × 100]% change relative to the mean pre-period entry rate of Y_bar%." The benchmark range for a substantively meaningful and plausible effect is −0.01 to −0.05 pp per 1 SD (representing 3–17% relative decline). If β falls outside this range, the user needs to investigate whether the instrument construction or sample selection is driving the result.

**On Q3b (DD alongside DDD):** The supervisor's request is well-grounded. The user should run three regressions as a table (DD_young, DD_old, DDD) and use the relationships among them to tell a story. If DD_old is near zero, the DDD result is fully driven by the young-specific response — this is the ideal case for the theory. If DD_old is substantially negative (older workers also reduce entry in high-exposure CZs), the DDD is a lower bound on the total effect but a clean test of differential youth vulnerability. Either scenario is publishable; what matters is that the user can explain it.

**On Q3c (H4 under Option 1):** H4 can be rescued, but it requires two modifications: (1) adopting Approach A (split outcomes rather than a single aggregate), which requires defining "licensed high-exposure" and "unlicensed high-exposure" occupation groups; (2) labeling H4 as a supplementary/exploratory analysis in the proposal. The accounting and auditing occupation group is the strongest case because it combines high AI exposure with meaningful (if partial) licensing requirements, enabling a within-sector comparison. The user should not claim H4 as a primary identification result — it doesn't have sufficient statistical power at MSc scale. But it is intellectually defensible and adds theoretical richness.

The deepest challenge for H4: the mechanism story needs refinement. "Licensing protects against displacement" is only plausible if the protection comes from licensing per se (legal barriers to entry for AI substitutes) rather than from the nature of the licensed occupation's tasks. CPAs sign audits — a legal requirement AI cannot yet fulfill — but this is about audit liability, not licensing per se. The user should acknowledge this in the proposal. The more defensible version of H4: "the certification/audit-sign-off requirement associated with licensed occupations creates an institutional buffer against full AI task substitution, slowing occupational entry disruption."

---

## Sources

- Autor, Dorn, Hanson (2013), "The China Syndrome," AER 103(6). Accessed via ddorn.net PDF.
- Acemoglu and Restrepo (2020), "Robots and Jobs," JPE 128(6). Accessed via NBER WP 23285.
- Bonfiglioli, Crinò, Gancia, Papadakis (2023/2024), "Artificial Intelligence and Jobs: Evidence from US Commuting Zones," Economic Policy. Accessed via economic-policy.org PDF and CEPR VoxEU column.
- Dauth, Findeisen, Suedekum, Woessner (2021), "The Adjustment of Labor Markets to Robots," JEEA 19(6). Accessed via sebastian-findeisen.com PDF.
- Mohnen (2025), "The Impact of the Retirement Slowdown on the U.S. Youth Labor Market," Journal of Labor Economics. DOI: 10.1086/725874. Abstract and design from Semantic Scholar.
- Olden and Møen (2022), "The Triple Difference Estimator," Econometrics Journal 25(3): 531–553. DOI: 10.1093/ectj/utac010. Accessed via Oxford Academic.
- Eloundou et al. (2023), "GPTs are GPTs: An Early Look at the Labor Market Impact Potential of Large Language Models," arXiv:2303.10130. Occupation exposure lists accessed via arXiv PDF.
- BLS, "Certification and licensing status of the employed by occupation," CPS Table 53, 2025 annual averages. https://www.bls.gov/cps/cpsaat53.htm
- BLS, "FAQs about data on certifications and licenses (CPS)." https://www.bls.gov/cps/certifications-and-licenses-faqs.htm
