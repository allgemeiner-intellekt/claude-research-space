# Survey: Empirical Evidence on GenAI and Labor Markets — Verifying Proposal Citations

## Summary

The proposal's citations are mostly accurate but contain several meaningful omissions and at least one significant mischaracterization. The empirical landscape is genuinely mixed and contested, which creates both threats and opportunities for the proposal. The biggest threat is the Frank et al. (2026) pre-trends problem: the deterioration in AI-exposed occupations predates ChatGPT, which directly undermines any identification strategy that treats ChatGPT's release as a clean shock. The biggest opportunity is that the literature on entry-level and younger workers specifically is more favorable to the proposal's core claims than the aggregate results — and that literature is newer and less reviewed in the proposal.

---

## Key Sources: Verified Citations

### Chen et al. (2025) — "The (Short-Term) Effects of Large Language Models on Unemployment and Earnings"
- **Link**: arXiv:2509.15510 (September 2025); Da Chen, C. Kane, Austin Kozlowski, Nadav Kunievsky, James Evans
- **Key content**: Uses Synthetic DiD to compare earnings and unemployment across occupations with differing LLM exposure. Finds workers in highly exposed occupations experienced **earnings increases** following ChatGPT's introduction, while unemployment rates remained **unchanged**. Argues initial labor market adjustment operated primarily through earnings rather than worker reallocation.
- **Proposal characterization**: "suggest that high-exposure occupations have not yet exhibited a systematic short-run rise in unemployment." This is **accurate but critically incomplete**: the paper also finds earnings *rose* for exposed workers — a productivity gain finding that actually cuts against the proposal's displacement framing. The proposal selects only the null unemployment result, omitting the positive earnings result.
- **Assessment**: Working paper, arXiv, 1 citation as of April 2026. Not yet peer-reviewed. Credible design (SDiD), but the partial citation is misleading.

### Tamkin and McCrory (2025) — "Estimating AI productivity gains from Claude conversations"
- **Link**: https://www.anthropic.com/research/estimating-productivity-gains (November 5, 2025)
- **Key content**: Not a peer-reviewed paper. An Anthropic research report/blog post. Analyzes 100,000 Claude.ai conversations using privacy-preserving methods. Estimates tasks would take ~90 minutes without AI; Claude speeds up tasks by ~80%. Extrapolates to a potential 1.8% annual US labor productivity growth increase over 10 years if AI were universally adopted. The paper is authored by Tamkin and McCrory at Anthropic. Key methodological problem: Claude is asked to estimate how long tasks would take, so the productivity figures are Claude's self-assessment. Authors acknowledge this cannot account for time humans spend outside the conversation window or quality-checking.
- **Proposal characterization**: "estimates productivity gains from Claude conversations." Technically accurate but undersells both what the paper claims and its limitations. It also does not flag that this is an Anthropic house report, not peer-reviewed research.
- **Assessment**: Non-peer-reviewed Anthropic research note. High conflict-of-interest (Anthropic measuring its own productivity). Methodological problems (circular self-assessment). Represents interesting measurement approach but extremely tentative evidence. The proposal should note these limitations.

### Massenkoff and McCrory (2026) — "Labor market impacts of AI: A new measure and early evidence"
- **Link**: https://www.anthropic.com/research/labor-market-impacts (March 5, 2026; updated March 8, 2026)
- **Key content**: Anthropic working paper (not peer-reviewed). Introduces "observed exposure" measure combining Eloundou et al.'s theoretical LLM capability scores with actual Anthropic usage data from the Economic Index. Key findings: (1) no systematic increase in unemployment for highly exposed workers since late 2022; (2) suggestive but barely statistically significant evidence that hiring of 22–25-year-olds into exposed occupations has slowed — a ~14% drop in job-finding rate in the post-ChatGPT era vs. 2022; (3) jobs with higher observed exposure are projected by BLS to grow less through 2034. Workers in most exposed occupations are more likely to be older, female, more educated, and higher-paid. There was a labeling error in Figure 7 that required correction on March 8.
- **Proposal characterization**: "suggest more muted aggregate unemployment responses in broader markets, with potential softening at hiring and entry margins." This is **mostly accurate** but soft-pedals how tentative the young worker finding is. The paper itself says the young worker result is "just barely statistically significant" and offers multiple alternative interpretations (staying in existing jobs, different roles, returning to school). The proposal's language "potential softening" appropriately flags this uncertainty.
- **Assessment**: Anthropic working paper, non-peer-reviewed. Conflict-of-interest concern (same as Tamkin-McCrory). The young worker hiring result is real but fragile — p-value is barely significant, and the March correction of Figure 7 (reversed labels on the key chart) raises further concern about the robustness of what is already the most important empirical result for the proposal.

### Frank et al. (2026) — "AI-exposed jobs deteriorated before ChatGPT"
- **Link**: arXiv:2601.02554 (January 5, 2026); Morgan Frank, A. Javadian Sabet, L. Simon, S.H. Bana, R. Yu (Pittsburgh/Stanford/Revelio Labs/Columbia)
- **Key content**: Uses monthly U.S. unemployment insurance records, millions of LinkedIn profiles, and millions of university syllabi. Finds: (1) unemployment risk rose in AI-exposed occupations beginning in **early 2022**, months before ChatGPT; (2) graduate cohorts from 2021 onward entered AI-exposed jobs at lower rates than earlier cohorts, with gaps opening before late 2022; (3) graduates with more AI-exposed curricula had higher first-job pay and shorter job searches **after** ChatGPT. Together these results point to pre-GenAI forces (automation wave, post-COVID tech cooling) rather than ChatGPT specifically.
- **Proposal characterization**: "suggest that deterioration in high-exposure occupations may predate the ChatGPT launch." Accurately described, but the proposal uses this acknowledgment as a brief hedge rather than confronting its full implications. The paper is a direct challenge to using ChatGPT's release as a treatment date.
- **Assessment**: arXiv preprint. Authors are highly credible (Stanford Digital Economy Lab affiliation for Bana, Revelio Labs for Simon which provides excellent labor market data). Three independent data sources pointing to the same pre-trend. This is the most methodologically serious threat to the proposal's identification.

### Humlum and Vestergaard (2025a) — "Large Language Models, Small Labor Market Effects" / "Still Waters, Rapid Currents"
- **Link**: NBER Working Paper 33777 (May 2025); the paper's title was later updated to "Still Waters, Rapid Currents: Early Labor Market Transformation under Generative AI"
- **Key content**: Links large-scale representative adoption surveys to administrative labor records in Denmark. Using DiD, estimates **precise null effects** on earnings and recorded hours at both worker and workplace levels, ruling out effects larger than 2% two years after ChatGPT introduction. These null results hold across intensive users, early adopters, workplaces with investments, workers reporting large gains, flexible-pay occupations, and **early-career jobs**. However, adoption is linked to occupational switching and task restructuring, suggesting transformation without aggregate disruption yet.
- **Proposal characterization**: "find limited aggregate employment and wage effects of LLMs in Danish data." Accurate. But the proposal should note that the null result for early-career jobs within firms is particularly relevant — it's one of the few papers explicitly testing this and finding nothing.
- **Assessment**: NBER Working Paper, not yet peer-reviewed but NBER stamp is strong quality signal. High-quality administrative data from Denmark. Strong design. This is one of the most credible null-effects papers in the literature.

### Humlum and Vestergaard (2025b) — "The Unequal Adoption of ChatGPT Exacerbates Existing Inequalities Among Workers"
- **Link**: PNAS, Vol. 122, No. 1 (January 2025); DOI: 10.1073/pnas.2414972121
- **Key content**: Survey of ~18,000 Danish workers in 11 exposed occupations, linked to administrative register data. Finds: (1) younger and less experienced workers are more likely to use ChatGPT (every year of age/experience associated with ~0.6–0.7 pp lower adoption likelihood); (2) but workers who use ChatGPT earned slightly **more** before its arrival; (3) women are 16 pp less likely to use ChatGPT than men in the same occupation; (4) employer restrictions and perceived training needs are primary adoption barriers.
- **Proposal characterization**: "show that younger and less experienced workers adopt ChatGPT faster." This is **partially accurate but misses the nuance**: the paper shows younger workers adopt faster *conditional on occupational exposure*, but the paper's main argument is about the **exacerbation of inequalities** — higher-earning, male workers are disproportionately using the tool, creating a "less able workers getting left behind" dynamic that cuts against a simple "young workers benefit" story. The proposal is using this paper to support its claim that young workers are more deeply enmeshed with AI tools, which is valid, but misses the productivity inequality dimension.
- **Assessment**: Peer-reviewed, published in PNAS. High credibility. Clean survey methodology with admin data verification.

### Hui, Reshef, and Zhou (2023/2024) — "The Short-Term Effects of Generative AI on Employment: Evidence from an Online Labor Market"
- **Link**: Organization Science (2024), Vol. 35(6): 1977–1989; DOI: 10.2139/ssrn.4527336; CESifo WP 10601 (open access)
- **Key content**: Studies the effect of ChatGPT, DALL-E 2, and Midjourney releases on freelancers on a large online platform (Upwork). Finds freelancers in highly affected occupations experience **reductions in both employment and earnings**. Notably, top freelancers (high past performance) are **disproportionately affected** by AI, not protected. Generative AI appears to transform human capital's role and reduce overall demand for workers.
- **Proposal characterization**: "find negative employment and earnings effects in online labour markets." Accurate.
- **Assessment**: Peer-reviewed, published in Organization Science. 134 citations. Strong credibility. Important caveat: online freelance labor market (Upwork) is a specialized setting with different competition dynamics than typical employment. Effects may be larger/faster in platform markets than in standard employment, so external validity to the main labor market is uncertain.

### Handa et al. (2025) — "Which Economic Tasks are Performed with AI? Evidence from Millions of Claude Conversations"
- **Link**: arXiv:2503.04761 (February 11, 2025); Kunal Handa, Alex Tamkin, Miles McCain et al. (Anthropic)
- **Key content**: Analyzes 4+ million Claude.ai conversations through O*NET tasks/occupations lens. Finds AI usage concentrates in software development and writing (~half of all usage). ~36% of occupations use AI for at least a quarter of their tasks. 57% of usage is augmentative; 43% is automative. This is the foundational Anthropic Economic Index paper establishing the methodology for subsequent papers.
- **Proposal characterization**: "measuring observed AI exposure from real user interactions." Accurate description of what the paper does.
- **Assessment**: arXiv preprint. Anthropic-affiliated authors. Methodologically important contribution — using actual usage data rather than theoretical exposure. But represents only Claude users, who skew toward technical workers, and uses a sampling method that may not represent all AI usage. The Budget Lab Yale explicitly flagged that Claude usage data may not be representative of broader AI tool usage (ChatGPT, Gemini, Copilot all have different user bases).

### Bick, Blandin, and Deming (2024) — "The Rapid Adoption of Generative AI"
- **Link**: SSRN/Management Science (accepted); DOI: 10.20955/wp.2024.027
- **Key content**: Series of nationally representative U.S. surveys. As of late 2024: 45% of US population age 18–64 uses genAI; 27% of employed respondents used it for work at least once/previous week. Adoption faster than PC, faster than internet adoption. Between 1–7% of all work hours assisted by genAI; time savings equivalent to 1.4% of total work hours. Firm climate and policies play major role in adoption.
- **Proposal characterization**: "rapid adoption of GenAI by U.S. workers but limited share of working hours affected." Accurate.
- **Assessment**: Management Science (accepted). 142 citations. High credibility. The 1–7% range for work hours is wide and reflects methodological variation across their survey waves — the proposal citing this as supporting "limited" penetration is defensible but cherry-picks the lower end.

---

## Additional Papers the Proposal Should Consider

### Brynjolfsson, Chandar, and Chen (2025) — "Canaries in the Coal Mine? Six Facts about the Recent Employment Effects of AI"
- **Link**: Stanford Digital Economy Lab Working Paper (November 2025); https://digitaleconomy.stanford.edu/publications/canaries-in-the-coal-mine/
- **Key content**: Uses high-frequency administrative payroll data from the largest US payroll provider. Finds early-career workers (ages 22–25) in the most AI-exposed occupations have experienced a **16% relative decline in employment** since widespread GenAI adoption, even controlling for firm-level shocks. More experienced workers in same occupations unaffected. Adjustments occur through employment, not compensation. Effects concentrated in occupations where AI is more likely to automate (not augment) human labor. Results robust to excluding tech firms and remote-work-amenable occupations.
- **Relevance**: This is the single most directly relevant new paper to the proposal — it provides the largest-scale empirical support for exactly the proposal's central claim (young worker displacement). The proposal must cite it. Massenkoff & McCrory explicitly cite it and their young worker result echoes it. Notably, Brynjolfsson et al. have a subsequent blog post (February 2026) addressing confounds including interest rates and timing — suggesting the result is defensible against macro alternatives.
- **Assessment**: Working paper from Stanford Digital Economy Lab. High-credibility authors (Brynjolfsson is one of the most cited labor economists). Administrative payroll data is better than survey-based CPS. Not yet peer-reviewed but circulated widely.

### Lodefalk, Löthman, Koch, and Engberg (2026) — "Same Storm, Different Boats: Generative AI and the Age Gradient in Hiring"
- **Link**: Örebro University Working Papers 2026:2 (March 2026); https://www.oru.se/globalassets/oru-sv/institutioner/hh/workingpapers/workingpapers2026/wp-2-2026.pdfLinks to an external site.
- **Key content**: Uses Swedish full-population employer–employee register data and 4.6 million job advertisements. Key empirical move: exploits Sweden's 7-month gap between the Riksbank's first rate hike and ChatGPT's launch as a timing test, arguing the broad decline in postings aligns with monetary tightening rather than AI. Then estimates employer-level DiD for employment composition: finds accelerating decline of 5.5% in employment of 22–25-year-olds in high-AI-exposure occupations by early 2025 relative to less exposed occupations within same employers, while employment of workers over 50 rose by 1.3%. Argues GenAI reshapes **hiring composition** rather than aggregate demand.
- **Relevance**: Directly relevant and very recent. Supports the proposal's thesis while partially addressing the timing problem via the Riksbank instrument. This paper is not cited in the proposal at all and should be.
- **Assessment**: Working paper, not peer-reviewed. But Swedish register data is extremely high quality (full-population employer–employee). The monetary policy timing test is a smart identification strategy.

### Hampole, Papanikolaou, Schmidt, and Seegmiller (2025) — "Artificial Intelligence and the Labor Market"
- **Link**: NBER Working Paper 33509 (February 2025); SSRN:5121025
- **Key content**: Constructs NLP-based measures of worker task exposure to AI over 2010–2023, varying across firms and time. Uses exogenous variation in measures from pre-existing hiring practices across firms. Finds muted *overall* employment effects because offsetting mechanisms cancel: highly-exposed occupations face lower demand but firm productivity gains create broader employment. Also finds workers reallocate effort from AI-exposed tasks to non-exposed tasks within occupations.
- **Relevance**: One of the stronger identification papers. Argues muted aggregate effects do not imply no effect on any subgroup.
- **Assessment**: NBER Working Paper. Credible IV strategy via pre-existing hiring networks. Notable for finding that firm-level analysis reveals mechanisms aggregate analysis obscures.

### Gimbel, Kinder, Kendall, and Lee (2025) — "Evaluating the Impact of AI on the Labor Market: Current State of Affairs"
- **Link**: The Budget Lab at Yale (October 2025); https://budgetlab.yale.edu/research/evaluating-impact-ai-labor-market-current-state-affairs
- **Key content**: Broad review using CPS data and both OpenAI and Anthropic exposure measures. Finds the occupational mix is changing faster than historical tech transitions, but only slightly, and the acceleration **predates ChatGPT** (consistent with Frank et al.). No evidence of exposure-related unemployment changes. The paper explicitly notes that changes in the occupational mix for young workers (20–24 vs. 25–34) diverge slightly more since ChatGPT, which is "consistent with Brynjolfsson et al." but could also reflect a slowing macro labor market. Also flags that Claude usage data is dominated by technical workers and may not be representative of all AI usage.
- **Relevance**: Useful synthesis paper. Also directly relevant to the proposal's concern about pre-trends.
- **Assessment**: Think tank report (Budget Lab at Yale), not peer-reviewed, but methodologically transparent and high-quality.

---

## The Frank et al. (2026) Pre-Trends Problem

This is the most important identification threat for the proposal.

Frank et al. find using three independent data sources (UI records, LinkedIn profiles, university syllabi) that:
1. Unemployment risk in AI-exposed occupations rose in **early 2022**, not after ChatGPT's November 2022 release
2. Graduate cohorts from **2021 onward** entered AI-exposed jobs at lower rates, with the gap opening before late 2022
3. The Gimbel et al. Budget Lab paper finds the occupational mix divergence also predates ChatGPT

**What this means for a 2019 vs. 2023–24 comparison design**: If deterioration was already underway in 2021–2022, then a comparison of 2019 (pre-AI) vs. 2023–24 (post-ChatGPT) will conflate:
(a) any effects of ChatGPT/GenAI specifically
(b) broader AI/automation trends predating GenAI
(c) the post-COVID tech sector adjustment (mass layoffs in tech began late 2022, concentrated in AI-exposed roles like software engineering)
(d) macroeconomic tightening effects (rate hikes 2022–2023)

The Lodefalk et al. paper attempts to address (d) for Sweden; Frank et al. explicitly discuss (b) and (c); Gimbel et al. note (b). The proposal cannot simply dismiss this. If using 2019 as the baseline, the proposal needs to either argue that 2019–2022 trends are stable in its outcome of interest (occupational entry rather than unemployment), or adopt a sharper design that separates these waves.

**Partial mitigation**: Frank et al. also find that graduates with LLM-relevant education had **better** outcomes after ChatGPT (shorter job searches, higher pay), which suggests ChatGPT did change something, just not in the direction of across-the-board displacement. The pre-trend argument affects where the baseline is, not necessarily whether there's a differential post-2022 effect on some subgroups.

---

## The Anthropic Papers Problem

Tamkin & McCrory (2025) and Massenkoff & McCrory (2026) are **not peer-reviewed**. Both are Anthropic research reports/working papers published on Anthropic's website. The specific problems:

1. **Conflict of interest**: Anthropic researchers measuring Anthropic product benefits/impacts. The productivity gains paper (Tamkin/McCrory) uses Claude to estimate how much time Claude saves — circular methodology.

2. **Selection bias in data**: Both papers use Claude usage data, which skews heavily toward technical workers (Gimbel et al. explicitly flags this). Handa et al. acknowledge nearly half of Claude usage is software development and writing tasks. This is not representative of the full labor market.

3. **Massenkoff & McCrory (2026) figure error**: Figure 7 (the key young worker hiring chart) had reversed group labels and required correction on March 8, 2026, three days after publication. This is the most empirically important result in the paper for the proposal, and it had a labeling error.

4. **Barely significant result**: The Massenkoff/McCrory young worker hiring result has p-value described as "just barely statistically significant." This is the headline result the proposal rests on for the "entry margin" channel.

The proposal should cite these papers with caveats about their provenance, not treat them as equivalent to peer-reviewed academic work.

---

## Landscape Assessment

### State of knowledge (April 2026)

The field has coalesced around a fairly consistent picture:

1. **Aggregate unemployment**: No major signal. Multiple papers (Humlum/Vestergaard 2025a, Massenkoff/McCrory 2026, Gimbel et al. 2025, Chen et al. 2025) find null aggregate unemployment effects. The Budget Lab's occupational mix analysis finds macro stability with modest acceleration.

2. **Platform/freelance labor markets**: Clear negative effect on employment and earnings for directly competing workers (Hui/Reshef/Zhou). This may be faster to adjust than standard employment because platform markets clear quickly.

3. **Young workers**: This is where the picture is most contested and most relevant. Brynjolfsson/Chandar/Chen find a 16% decline for 22–25-year-olds in AI-exposed roles. Massenkoff/McCrory find a ~14% decline in hiring but barely significant. Lodefalk et al. find 5.5% in Sweden. Humlum/Vestergaard (2025a) find null effects even for early-career jobs in Denmark. The Frank et al. paper complicates all of these by showing the deterioration predates ChatGPT.

4. **Identification**: No paper has clean identification. The cleanest designs (Hampole et al.'s hiring network IV; Lodefalk et al.'s Riksbank timing test) both find more limited effects than naive DiD designs. Frank et al.'s pre-trends finding undermines ChatGPT-release-based DiD strategies broadly.

5. **Earnings vs. employment**: Chen et al. (2025) find earnings *rose* for exposed workers. Humlum/Vestergaard (2025a) find null wage effects. Hui/Reshef/Zhou find negative earnings effects on platforms. The direction depends heavily on the outcome measure and context.

### Agreements across sources

- No large-scale aggregate unemployment shock has occurred (consistent across all mainstream studies)
- Young/entry-level workers in AI-exposed occupations are more at risk than experienced workers in the same occupations
- Adoption is faster than PCs or internet but working hours affected remain limited (1–7%)
- Platform/gig workers are more immediately vulnerable than standard employees
- Pre-ChatGPT trends complicate attribution

### Conflicts between sources

- The magnitude of the young worker effect varies enormously: 16% (Brynjolfsson), 14% (Massenkoff, barely sig), 5.5% (Lodefalk), 0% (Humlum/Vestergaard)
- Whether earnings in exposed occupations are rising or falling
- Whether the post-2022 deterioration in AI-exposed entry-level hiring is AI-caused or a continuation of earlier tech automation trends + macro tightening

### Gaps and under-explored areas

- Long-run occupational entry patterns (the proposal's key variable) are barely studied — most papers focus on short-run employment or unemployment, not on whether young people are entering a given occupation's career track
- Occupational transitions and career trajectories for young workers who are *not* hired into AI-exposed roles — where do they go?
- Non-US/non-Denmark settings (Sweden from Lodefalk is welcome but needed more broadly)
- Causal identification strategies that pre-register and address pre-trends explicitly

### Surprises

1. The Humlum/Vestergaard (2025b) PNAS paper — which the proposal uses to support "young workers adopt faster" — is actually primarily a paper about inequality in adoption, with the headline finding that **higher-earning workers and men** are using ChatGPT more, not lower-earning young workers. The proposal uses only one finding from a paper whose main message is more pessimistic about technology-exacerbated inequality.

2. The Tamkin/McCrory "productivity" paper gets cited as evidence, but it is methodologically circular (Claude scoring Claude's own productivity) and represents a massive extrapolation from task-level to economy-wide effects. It should be treated with significant caution in an academic dissertation.

3. The single most important paper for the proposal — Brynjolfsson et al.'s "Canaries in the Coal Mine" — is absent from the proposal's citation list. This is a significant omission given it directly evidences the proposal's central thesis with the best data quality.

4. The Frank et al. (2026) pre-trend result is more severe than the proposal acknowledges. The proposal presents it as a hedge when it is actually a direct identification threat.
