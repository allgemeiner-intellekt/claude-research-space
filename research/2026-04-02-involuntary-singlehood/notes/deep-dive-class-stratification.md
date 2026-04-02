# Deep Dive: The Class Stratification of the Matching Crisis

## Question

What exactly happened to produce the class stratification of marriage in the US? Specifically: (1) What does Chambers, Goldman & Winkelmann (2025) find about male joblessness and marriage gaps across metro areas, including their exact measure and identification strategy? (2) What are the precise magnitudes of Autor, Dorn & Hanson's (2019) trade shock effects on marriage — and is there recovery? (3) How has Wilson's (1987) "marriageability" concept been operationalized, and is the effect threshold-based or continuous? (4) Does the class marriage gap narrow in countries with stronger safety nets (Scandinavia, Germany)? (5) Is "marrying down" educationally actually happening at scale, or is it aspirational?

---

## Investigation

### 1. Chambers, Goldman & Winkelmann (November 2025)

**Paper**: "Scarcity of college men and the decline in marriage among non-college Americans." Clara Chambers (Yale), Benjamin Goldman (Cornell/Opportunity Insights), Joseph Winkelmann (Harvard). November 2025 working paper. Published version cited as *Nature Human Behaviour* forthcoming.

**Data**: Current Population Survey (CPS), American Community Survey (ACS), and linked Census/tax records from the Opportunity Atlas (Chetty et al. 2018). For the cohort analysis, they use birth cohorts 1930–1980, measuring marriage at age 45. For the cross-area analysis, they use ACS data from 2017–2021 focused on individuals aged 40–49, across 2,351 PUMAs (Public Use Microdata Areas) each with an average population of ~140,000.

**The core finding on marriage rates by cohort (from the paper directly):**
- College women born 1930: 77.7% married at age 45
- College women born 1980: 71.0% married at age 45 (only a 6.7pp decline)
- Non-college women born 1930: 78.7% married at age 45
- Non-college women born 1980: 52.4% married at age 45 (a 26.3pp collapse)
- The education gap in marriage went from essentially zero (~1pp) to nearly 19pp across 50 years.

**The "male joblessness" measure and the 50% finding:**

The cross-area analysis does NOT use a "male joblessness" measure per se — the survey note's framing of "50%+ smaller marriage gaps" slightly mischaracterizes the paper's result. The actual measure is the **employment-to-population ratio (EPOP) for non-college men** ages 40–49 across PUMAs. The paper residualizes EPOP on fixed effects for 50 quantiles of women's college attendance rates, so comparisons are within groups of areas with similar female college attendance but differing male employment.

**Exact quantitative result (from page 9 of the paper):**
- "A 1 SD decline (7.6pp) in the EPOP for non-college men is associated with a 4.2pp (7.3%) decline in marriage rates for non-college women."
- In areas with the *lowest* employment rates for non-college men (bottom 2.5% of PUMA distribution): marriage rate for non-college women = **44.5%**
- In areas with the *highest* employment rates for non-college men (top 2.5%): marriage rate for non-college women = **66.0%**
- For college women the effect is much weaker: 1 SD decline in non-college male EPOP → only 2.4pp decline in college women's marriage rates
- The education gap in marriage between college and non-college women is **17.9pp** in areas with the *lowest* non-college male employment — but **decreases by 9.2pp (51.4%)** in communities with the *highest* male employment rates.

So the "50%" figure in the survey notes refers specifically to the gap *narrowing* from 17.9pp to about 8.7pp (51.4% reduction) when going from worst to best male employment areas. This is a descriptive cross-sectional correlation, not a causal estimate. The paper acknowledges the endogeneity concern — couples may sort into better labor markets — and addresses it using Opportunity Atlas data linking adult outcomes to childhood commuting zones (origin, not destination), finding similar results.

**The "pool depletion" finding (the most striking number in the paper):**
The paper's core argument is about a two-pronged depletion of the partner pool for non-college women:
1. Non-college men's real earnings fell: average real earnings at age 45 declined from $56,400 (1930 cohort) to $50,000 (1980 cohort).
2. College women increasingly "poached" high-earning non-college men: marriages in which the wife has a college degree and husband does not **quadrupled** (from 2.3% to 9.6% of all marriages).
3. Combined result: the share of non-college men who both (a) earn above the national median within their birth cohort AND (b) are not married to a college woman **fell from 72.9% to 35.3%** — a decline of more than 50%.

The paper also provides a policy-relevant observation: "In present-day communities where non-college men are stably employed and not involved with the criminal justice system, marriage rates for non-college women remain above 60% — levels last observed nationally for non-college women born in the mid-1950s." This is the strongest evidence for reversibility through labor market intervention.

**Identification**: The paper is primarily descriptive and decomposition-based (using a "reduced form" version of the Choo-Siow 2006 marriage market framework). The authors explicitly do NOT claim to causally identify the effect of male economic decline on marriage — they note this complements work like Autor, Dorn and Hanson (2019) which does provide causal identification. The cross-area estimates are associational, though the use of childhood commuting zones from the OA data provides some protection against selection-on-migration.

---

### 2. Autor, Dorn & Hanson (2019): "When Work Disappears: Manufacturing Decline and the Falling Marriage Market Value of Young Men"

**Published**: *American Economic Review: Insights*, 1(2): 161–178, 2019. Circulating since 2014/2018.

**Data**: Census IPUMS 1990 and 2000, pooled ACS 2013–2015. 722 commuting zones (CZs) covering the US mainland. Outcomes measured for young adults ages 18–39. Outcome data also uses US Vital Statistics death certificates through 2015 (for mortality).

**Identification strategy**: The paper uses a shift-share instrumental variables approach (the "China Shock" design from Autor, Dorn & Hanson 2013). The instrument exploits:
1. Pre-existing industry composition across CZs (based on 1990 employment shares)
2. Changes in Chinese import penetration in other high-income countries (Australia, Denmark, Finland, Germany, Japan, New Zealand, Spain, Switzerland) as the exogenous supply-driven component

Crucially, the paper constructs **gender-specific trade shocks** (ΔIP^m and ΔIP^f) that separately capture import competition in male-dominated versus female-dominated industries. This allows them to test whether effects on marriage/fertility run through male employment losses specifically (the Wilson hypothesis) versus general economic decline. This is the key innovation over prior work.

**Employment and earnings effects (Table 1):**
- A one-unit overall trade shock (roughly equal to the average decade-level CZ rise in exposure 1990–2014) depresses manufacturing employment among young adults by 1.06 percentage points (t = −6.3)
- For young men: −0.99 pp (t = −5.8); for young women: −1.09 pp (t = −5.5)
- But for *overall employment* (including non-manufacturing), trade shocks significantly depress the male-to-female employment differential: a unit trade shock reduces male relative employment by 0.65 points (t = −2.5) — because men lose non-manufacturing jobs too while women partly replace lost manufacturing jobs with school enrollment
- On the *earnings distribution*: a one-unit trade shock reduces male relative to female earnings by $672 at the 25th percentile (t = −3.5), $445 at the median (t = −2.3), and $847 at the 75th percentile (t = −2.5)
- The *proportional* impact is largest at the bottom: trade shocks compress the male-female wage gap by 2 points at the median, 4 points at p35, and 6 points at p20

**Male idleness (neither employed nor in school):**
- A unit shock to male-intensive industries raises male idleness by 2.6 percentage points (t = 4.3) — the key vector through which manufacturing decline reaches marriage markets
- Shocks to female-intensive industries reduce female idleness (−1.6 pp, t = −2.8)

**Marriage effects (Table 3, Panel A — the main marriage results):**
- A one-unit overall trade shock reduces the fraction of young women currently married by **0.95 percentage points** (t = −3.1)
- It also reduces the fraction previously married (widowed/divorced/separated) by 0.21 pp (t = −2.0)
- And raises the fraction never-married by 1.16 pp (t = 3.5)
- Gender-specific results: a unit shock to **male-intensive industries** reduces the fraction of women ever married by **4.2 percentage points** (t = 6.6, a 12% rise on a 1990 base of 34.8%) and reduces currently married by 3.6 pp (t = −5.8)
- A shock to **female-intensive industries** has the opposite sign and roughly two-thirds the magnitude

**Fertility and family structure:**
- A one-unit trade shock reduces births by 1.5 per 1,000 women (t = −4.2)
- A unit shock to male-intensive industries raises the share of mothers who are unmarried by 3.3 pp (t = 4.5)
- Raises the share of children living in poverty by 2.1 pp (t = 3.0)
- Reduces the fraction of women living with a married partner by 0.81 pp (t = −2.2) — and the declining marriage rate is NOT compensated by rising cohabitation (cohabitation falls too, by 0.22 pp)

**Scaling to aggregate magnitudes:**
From the conclusions section: "Scaling the observed rise in China import penetration between 1990 and 2014 by the estimates above, we would infer that rising trade pressure reduced the employment to population rate of young adult males by 3.9 percentage points as compared to an observed decline of 7.2 points; reduced the prevalence of marriage among young adult women by 2.4 percentage points as compared to an observed decline of 16.7 points; and increased the fraction of children living in poor households by 1.6 percentage points as compared to an observed increase of 4.0 points."

So the China trade shock alone accounts for: ~54% of the observed male employment decline, ~14% of the observed marriage decline, and ~40% of the rise in child poverty. Trade shocks are a real and substantial cause — but they are not the whole story for marriage.

**Recovery question**: The paper covers 1990–2014. It explicitly notes: "A key question unanswered by our work is whether reversing these adverse currents in blue-collar employment would undo their effects on marriage, fertility, and childhood poverty, or whether — as in Kearney and Wilson (2017) — some of these consequences would persist even where opportunities for blue-collar men improve."

**Kearney & Wilson (2018) is the key recovery evidence**: Using the fracking boom as a positive labor market shock to non-college men (2000s), they find that fracking production increases wages and jobs for non-college men, and raises both marital AND nonmarital birth rates — but **marriage rates do not increase** (Review of Economics and Statistics, 100(4): 678–690). This is a remarkable asymmetry: negative shocks reduce marriage, but positive shocks do not symmetrically restore it. The explanation they offer is consistent with positive income effects on fertility but not marriage formation. This is the strongest evidence that the marriage response to labor market shocks is not fully reversible through employment recovery alone — norms and expectations may have shifted.

---

### 3. The "Marriageability" Concept: Wilson (1987) and Its Operationalization

**Wilson's original formulation (The Truly Disadvantaged, 1987)**: Wilson argued that the dramatic decline in Black marriage rates from the 1960s to the 1980s resulted from a shortage of "marriageable men" — men who were employed, had stable income, and were not incarcerated. Wilson and Neckerman (1986) formalized this as the **Male Marriageability Pool Index (MMPI)**: the number of employed men in a marriage market per 100 unmarried women. They showed MMPI ratios fell sharply for Black men in their 20s and 30s in the 1970s and early 1980s, tracking the decline in Black marriage rates.

**The key methodological issue (from Ruggles 2022)**: The standard approach in the 1990s–2010s literature was to use *spatially defined* MMPI measures — counting employed unmarried Black men in a labor market area or metropolitan area and comparing to unmarried women. These studies (Lichter et al. 1992, Lloyd and South 1992, Fossett and Kiecolt 1992, Wood 1995, etc.) consistently found that male marriageability availability had a *significant* but *quantitatively small* effect on women's marriage rates — explaining only a fraction of the race gap. The literature consensus became "something more than class status is at play."

**Ruggles' (2022) critique**: Steven Ruggles (Demographic Research, 2022) argues the small effects in these studies reflect measurement error: spatially defined MMPI measures are noisy proxies because the actual pool of potential partners for a given woman depends on her social network, not geographic area. His solution: analyze marriage rates *from the perspective of men* — directly measuring individual men's economic characteristics and their own marriage rates, without needing spatial proxies.

**Ruggles' operationalization of marriageability**:
He uses three composite economic factors, treated as a continuum (not a threshold):
1. **Income decile** within the birth cohort (10 income categories)
2. **Occupational group** (professional/managerial/skilled; clerical/sales/operative; service/labor; no occupation)
3. **Employment/institutionalization status** (currently employed; not employed but worked in past year; no work in past year; institutionalized/incarcerated)

Ruggles explicitly states: "I treat marriageability as a continuum rather than a dichotomy. As Wood (1995) noted, marriage is more sensitive to income level than to employment, so studies that focus exclusively on the availability of employed men for marriage may understate the impact of economic circumstances on marriage. Moreover, combinations of socioeconomic characteristics — such as income, job type, employment, and incarceration — have greater explanatory power than any single characteristic."

**The data (Table 3 in Ruggles)**: First marriages per 1,000 never-married population, Black and White men, by income decile:
- Men in the top income decile married between **five and ten times more frequently** than men in the bottom income decile
- This holds across all census years (1960, 1970, 1980, 2008–2010, 2017–2019)
- The relationship is strongly monotonic — there is NO evidence of a threshold below which men become suddenly unmarriageable. The relationship is continuous across the income distribution.

**Is there a threshold?** The evidence from Ruggles strongly suggests NO discrete threshold. The gradient from bottom to top decile is steep and continuous. However, the Chambers/Goldman/Winkelmann evidence on the *pool* that non-college women draw from is instructive: the relevant threshold operationally is "earns above the national median AND is not married to a college woman." That's not a minimum viability threshold but a market-clearing concept — the men who are both economically viable AND available to non-college women.

**Ruggles' key finding about Wilson's hypothesis**: In the mid-to-late 20th century, race differences in economic composition were "sufficiently large to account for most race differences in first marriage rates." But "the size of the economic component declined dramatically over time." By 2017–2019, economic composition still explains a substantial share but less than in 1960–1980. Ruggles interprets this as: "With the decline of male-breadwinner families since the late 20th century, the role of male economic circumstances for race differences in marriage rates has diminished, but it remains substantial." This directly updates Wilson's original argument — valid in its era, still partially operative today.

---

### 4. Cross-National Comparison: Kalmijn (2013) on 25 European Countries

**Paper**: "The Educational Gradient in Marriage: A Comparison of 25 European Countries." Matthijs Kalmijn, *Demography*, 50(4): 1499–1520, 2013.

**Data**: Five waves of the European Social Survey (ESS), 2002–2010. N = 33,062 individuals ages 40–49 across 25 countries.

**Key finding on the direction of the gradient**:
Kalmijn finds the educational gradient in marriage (whether being better-educated predicts being in a union during midlife) **varies dramatically by country type**:

For **men**: A positive overall effect across Europe (b = 0.59 in log-odds; a 17% increase in odds per SD of education). BUT this effect is significantly weaker in countries with more egalitarian gender roles and significantly stronger in countries with more educational inequality (wider socioeconomic gaps between education groups).

For **women**: A negative overall effect (b = −0.37; a 9% decrease in odds per SD of education — better-educated women are slightly less likely to be in a union). But this reverses in the most gender-egalitarian countries.

**The Scandinavia finding** (this is the critical cross-national result):
- In the **most gender-egalitarian country** (Sweden, Denmark near the top), the implied effect of men's education on marriage is **+1.15** (strongly positive — better-educated men much more likely to be married)
- In the **least egalitarian country** (Italy, Greece, Portugal), the implied effect for men is **−0.01** (essentially zero)
- For **women**: in the most-egalitarian country, the implied effect is **+0.59** (positive — better-educated women more likely to be married); in the least-egalitarian country, the implied effect is **−1.49** (strongly negative)

**The crucial implication for the US comparison**: In Scandinavian-type countries, education functions very differently for marriage. For men, *egalitarianism strengthens* the educational gradient, meaning less-educated men face relatively MORE disadvantage in the marriage market in Scandinavia, not less. For women, egalitarianism reverses the gradient from negative to positive — educated women become *more* marriageable rather than less.

But Kalmijn's measure is education-based, not income/class-based. The mechanism he identifies: in egalitarian societies, men's economic prospects become less important (women work too), but men's cultural capital and egalitarian attitudes become MORE important for attracting a partner. Better-educated men in egalitarian settings are more attractive because they share household labor, have liberal values, and participate in childcare — not primarily because they earn more.

**The direct answer to "does the class marriage gap narrow with stronger safety nets"?**

Kalmijn's evidence is ambiguous on this. For *men*, the gradient becomes *more positive* (not less) in egalitarian/welfare-state countries — worse for less-educated men, not better. However, this is driven partly by cultural/attitude mechanisms, and the baseline rate of being in any union is similar (77% across Europe). The key distinction is that in egalitarian countries, *marriage* specifically shows larger education gradients, but cohabitation is more common among all groups and helps offset some of the gap.

**What Kalmijn does NOT address**: Whether the *absolute* marriage rate for less-educated men is lower in Scandinavia than in the US. He only examines relative gradients, not absolute rates. The high-cohabitation rates in Scandinavia mean that partnership rates (marriage + cohabitation combined) may show smaller gradients. When Chambers/Goldman look at "married and cohabiting partners" for the US cross-area comparison, they find "gaps in partnership rates between college and non-college women are 64.2% smaller in communities with the highest employment rates for non-college men" — a larger reduction than for marriage alone (51.4%).

**Bottom line on the Scandinavia question**: The welfare-state floor does not appear to reduce the marriage/partnership gap for less-educated men — in fact, evidence suggests educational gradients in partnership are at least as strong in egalitarian welfare states, just through different mechanisms (cultural/attitudinal rather than purely economic). Non-college men face disadvantage in partnership markets even where their economic floor is higher, because the criteria for attractiveness have shifted toward cultural and domestic traits correlated with education.

---

### 5. Educational Assortative Mating: Is "Marrying Down" Happening at Scale?

**Paper**: Hirschl, Schwartz & Boschetti (2024). "Eight Decades of Educational Assortative Mating: A Research Note." *Demography*, 61(5): 1293–1307.

**Data**: US decennial censuses 1940–2000 and American Community Survey, extending to 2020. Large nationally representative samples. Builds on and extends Schwartz and Mare (2005).

**What was expected**: Prior literature found rising educational homogamy through roughly 1990 (Schwartz and Mare 2005) — people increasingly marrying within educational group, the college degree becoming a sharper boundary. The expectation was that this would continue given rising inequality.

**What actually happened (confirmed finding)**: Educational homogamy stopped rising around 1990 and **reversed in the 2000s**. By 2020, there is a measurable and statistically significant **increase in hypogamy** (women marrying men with lower education).

**Key numbers from the Chambers/Goldman/Winkelmann paper** (which cites Hirschl et al. and provides additional data):
- In the 1930 birth cohort: 20.8% of marriages were of a college woman with a non-college man — but the model predicted 27.7% based on group sizes and 1930 surplus values, meaning college women were actually *less* likely than expected to marry non-college men
- In the 1980 birth cohort: 20.8% of marriages were of a college woman with a non-college man — the absolute share appears stable, but given the massive increase in college-educated women relative to college-educated men, this represents a **49.6% higher share than predicted** by supply effects alone (6.9pp above prediction)
- The share of women who are college-educated and married to a non-college man **quadrupled** — from 2.3% of all women in the 1930 cohort to 9.6% in the 1980 cohort — exceeding expectations based on 1930 surplus values by 3.2pp (50%)

**What this means**: The "marrying down" trend IS real and large, but it is partly compositional. More women are college-educated, so more absolute college women × non-college men marriages exist. The question is whether the *preference-adjusted* tendency (controlling for group sizes) has increased. Hirschl et al. and Chambers/Goldman/Winkelmann both say yes: the rise in college women × non-college men marriages exceeds what supply changes alone would predict.

**The selection of which non-college men college women marry**: This is critical. From Chambers/Goldman/Winkelmann (page 8): "As marriages between college women and non-college men have become more common, college women have increasingly married higher-earning non-college men. Real earnings for non-college men who marry college women have risen over time, from $61,400 for the 1930 cohort to $68,400 for the 1980 cohort. In contrast, average earnings for all other non-college men have declined even more sharply than the aggregate figures suggest, falling from $56,400 to $46,100."

This selection effect is devastating for non-college women's marriage prospects. The non-college men who become attractive to college women are the top earners among that group — the very men who historically formed the reliable core of the marriage market for non-college women.

**Does the college barrier remain?**: Hirschl et al. find that "a college degree remains the strongest dividing line to intermarriage" even as overall homogamy declines. Marriages crossing the college/no-college boundary are increasing, but marriages within the non-college group are also declining in quality (as the highest-earning non-college men depart upward into college-women marriages). The boundary is becoming more porous from the top (college women accepting non-college men) but the remaining men on the non-college side are increasingly those with poorer economic prospects.

---

## Key Findings

1. **Chambers/Goldman/Winkelmann (2025) actual finding**: The "male joblessness" measure is EPOP (employment-to-population ratio) for non-college men ages 40–49, residualized for local female college attendance rates, measured across 2,351 PUMAs. The education gap in women's marriage rates is **51.4% smaller** (from 17.9pp to 8.7pp) in areas with the highest vs. lowest non-college male employment. This is a descriptive cross-sectional association, not a causal estimate — but the authors cross-validate using childhood commuting zones (OA data) to address sorting concerns.
   - **Confidence: Strong evidence, though identification is associational rather than causal**

2. **Autor/Dorn/Hanson (2019) exact magnitudes**: A one-unit trade shock to male-intensive industries reduces ever-married rates by 4.2 pp (12% of base) and currently married rates by 3.6 pp. The China trade shock as a whole explains approximately 14% of the observed 1990–2014 decline in marriage prevalence. The effect works through male idleness (not just earnings) and manifests through both reduced marriage formation AND increased male mortality/absence.
   - **Confidence: Strong causal evidence via IV (shift-share design)**

3. **Recovery asymmetry (Kearney & Wilson 2018)**: Positive labor market shocks (fracking boom) raise fertility but do NOT increase marriage rates for non-college men. This is the strongest evidence that the marriage response to labor market deterioration is not straightforwardly reversible. Cultural adaptation or norm shifts appear to be irreversible on short timescales.
   - **Confidence: Strong evidence, but limited to a single episode in specific geography**

4. **Marriageability is continuous, not threshold-based**: Both Ruggles (2022) and the mainstream literature treat it as a smooth gradient. Men in the top income decile marry 5–10x more frequently than men in the bottom income decile — a steep monotonic function with no visible inflection point indicating a "minimum viable" threshold. The relevant policy concept is not a hard threshold but a relative pool: economically viable AND available (not already partnered upward with college-educated women).
   - **Confidence: Strong evidence from Ruggles' individual-level analysis**

5. **Kalmijn's cross-national finding (2013, 25 European countries)**: Egalitarian welfare states do NOT narrow the educational marriage gradient for men — they widen it. In Scandinavian-type countries (Sweden, Denmark, Norway), better-educated men have a *stronger* advantage in the marriage market, not weaker. The mechanism shifts from economic (income/employment) to cultural (egalitarian attitudes, domestic participation). This implies that the US marriage gap among non-college men would not narrow by simply raising their economic floor — partnership attractiveness in modern marriage markets is multidimensional.
   - **Confidence: Moderate — this is European data from 2002–2010, focused on education not class, and does not directly measure absolute partnership rates by economic class**

6. **Educational hypogamy is real and substantial**: Women marrying men with less education than themselves has genuinely increased since the 1990s, tracked by Hirschl et al. (2024) through 2020 across eight decades of census data. The share of college-educated women × non-college men marriages quadrupled as an absolute share of all women in the population (2.3% to 9.6%). But this is not rescuing non-college women's marriage prospects — it is making them worse, because the cream of non-college men is being selectively absorbed by college-educated women.
   - **Confidence: Strong evidence from 80 years of Census/ACS data**

---

## Assessment

The evidence chain here is unusually solid by social science standards, with multiple independent lines of evidence pointing to the same mechanism.

**What the evidence supports clearly**: The class stratification of the matching crisis is primarily a supply-side story about the economic deterioration of non-college men, not a story about changing female preferences or cultural shifts (though these play a secondary role). The Autor/Dorn/Hanson trade shock evidence provides genuine causal identification that labor market deterioration reduces marriage. The Chambers/Goldman/Winkelmann cross-area evidence shows the geographic variation in this pattern is exactly what we'd expect if male employment quality is the key variable. The magnitudes are substantial: a 21.5pp swing in non-college women's marriage rates across areas, depending on non-college men's employment rates.

**The most under-appreciated finding**: The "double depletion" mechanism in Chambers/Goldman/Winkelmann is sharper than previously understood. Non-college women face not just one but two simultaneous losses: (a) the absolute economic decline of non-college men, and (b) the selective "poaching" of the highest-earning non-college men by college-educated women who are adapting to the scarcity of college-educated male partners. The pool of economically viable AND available non-college men shrank from 72.9% to 35.3% of the non-college male cohort. This is a market structure story, not just an income story.

**Where the evidence is weaker**: The recovery question is underresolved. Kearney & Wilson's fracking evidence suggests that improving male economic conditions may not restore marriage formation — but this is one episode, in specific communities, during a brief period. The long-run adaptation remains unclear. Similarly, the Kalmijn evidence on European welfare states is suggestive but does not directly answer whether a US-style safety net expansion would narrow the class marriage gap. The European evidence mostly measures the educational gradient, not the absolute partnership rate disadvantage of working-class men.

**The Kalmijn finding creates a genuine policy puzzle**: If egalitarian welfare states do not narrow (and may widen) the educational gradient in marriage, then simply improving non-college men's economic outcomes through redistribution may be insufficient. The marriage market in advanced societies seems to be shifting toward valuing cultural/domestic traits correlated with education, not just income. The women most likely to consider marrying non-college men are, increasingly, doing so selectively — choosing the highest earners from that group. This suggests that any policy approach focused purely on income floors will be incomplete.

**Speculative but supported by the evidence**: The "marrying down" trend documented by Hirschl et al. represents an important adaptive mechanism, but it is self-limiting. College women are increasingly willing to cross the educational boundary, but they are doing so with a strong income screen on the men they choose. The equilibrium being reached is not one where educational credentials are simply abandoned as a sorting criterion — it is one where credentials are being partially replaced by earnings as the primary screening variable, which continues to leave low-earning non-college men outside the viable partner pool.

---

## Sources

- Chambers, Clara, Benjamin Goldman, and Joseph Winkelmann. "Scarcity of college men and the decline in marriage among non-college Americans." November 2025 working paper. https://benjamindgoldman.s3.us-east-2.amazonaws.com/papers/education_marriage/education_marriage.pdf
- Autor, David, David Dorn, and Gordon Hanson. "When Work Disappears: Manufacturing Decline and the Falling Marriage Market Value of Young Men." *American Economic Review: Insights* 1(2): 161–178, 2019. https://economics.mit.edu/sites/default/files/publications/ADH-WWD-Forthcoming-Dec-2018.pdf
- Hirschl, Noah, Christine R. Schwartz, and Elia Boschetti. "Eight Decades of Educational Assortative Mating: A Research Note." *Demography* 61(5): 1293–1307, 2024. DOI: 10.1215/00703370-11558914
- Kalmijn, Matthijs. "The Educational Gradient in Marriage: A Comparison of 25 European Countries." *Demography* 50(4): 1499–1520, 2013. https://matthijskalmijn.nl/onewebmedia/Kalmijn%20-%20DEM%20-%20Gradient%20in%20marriage.pdf
- Ruggles, Steven. "Race, class, and marriage: Components of race differences in men's first marriage rates, United States, 1960–2019." *Demographic Research* 46(39): 1163–1186, 2022. https://www.demographic-research.org/volumes/vol46/39/46-39.pdf
- Kearney, Melissa S. and Riley Wilson. "Male Earnings, Marriageable Men, and Nonmarital Fertility: Evidence from the Fracking Boom." *Review of Economics and Statistics* 100(4): 678–690, 2018. DOI: 10.1162/rest_a_00739
- Wilson, William Julius. *The Truly Disadvantaged: The Inner City, the Underclass, and Public Policy*. Chicago: University of Chicago Press, 1987.
- Autor, David H., David Dorn, and Gordon H. Hanson. "The China Syndrome: Local Labor Market Effects of Import Competition in the United States." *American Economic Review* 103(6): 2121–2168, 2013.
