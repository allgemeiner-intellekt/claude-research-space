# Survey: Can signal erosion be empirically separated from task displacement, and what would a testable version of H3 look like?

## Summary

The core theoretical mechanism in H3 — that LLMs erode the informativeness of writing-based hiring signals — is now well-grounded in academic literature, most directly in Galdin & Silbert (2025). The theoretical link from Spence (1973) to pooling equilibria under reduced signal cost is formalised in Wang (2025) and fits cleanly: when LLMs make writing cheap for everyone, high- and low-ability workers pool on the same (LLM-assisted) signal, destroying the separating equilibrium. The supervisor's complaint is not that H3 is wrong but that it is not written as a *testable hypothesis* — it lacks a specific, falsifiable prediction. The key insight for making H3 testable is the **differential prediction between signal erosion and task displacement**: task displacement hits quantity (fewer jobs, lower wages, fewer postings) while signal erosion hits the *screening channel* (longer funnels, more credential and experience requirements, more referral reliance, higher returns to verifiable signals). These observable implications are distinct and in principle separable — but the empirical evidence on whether either signature has actually appeared post-ChatGPT is mixed and contested, as detailed below.

## Searches conducted

1. Semantic Scholar: "Spence signaling model job market education signal cost"
2. Exa: "AI generated cover letters ChatGPT job applications employer screening detection"
3. Semantic Scholar: "job posting requirements credential inflation experience AI labor market"
4. Exa: "hiring standards credential requirements change post ChatGPT GPT AI entry level jobs 2023 2024"
5. ArXiv content retrieval: arxiv.org/abs/2511.08785 (Galdin & Silbert 2025)
6. Exa content: Fortune "experience creep" article (April 2026); FastCompany Craig article (May 2023)
7. Semantic Scholar: "occupational licensing labor market entry returns wages Kleiner"
8. Semantic Scholar: "task displacement automation versus signaling hiring empirical identification"
9. Exa content: Rezi.ai "Crisis of Entry-Level Labor" report; Indeed Hiring Lab tenure requirements data
10. Semantic Scholar: "referral hiring social networks screening uncertainty employer information asymmetry"

---

## Key Sources

### Galdin & Silbert (2025) — "Making Talk Cheap: Generative AI and Labor Market Signaling"
- **Link**: https://arxiv.org/abs/2511.08785 (arXiv:2511.08785)
- **Key content**: This is the most directly relevant academic paper to H3. Uses Freelancer.com data to show that before LLMs, employers paid a significant wage premium for job applications that were more customised/tailored (measured by a novel LLM-based tailoring metric). After LLMs, this premium collapsed — the signal was destroyed. They build a structural model of the signaling market, simulate counterfactual equilibria, and find that without costly written signals, the market becomes "significantly less meritocratic": top quintile workers are hired 19% *less* often, bottom quintile workers 14% *more* often. This directly operationalises signal erosion with a pre/post design (ChatGPT launch as natural experiment) and a continuous occupation-level treatment intensity measure. The DV they use is not job quantities but hiring *sorting quality* — exactly the screening channel, not the demand channel.
- **Assessment**: Very high quality. Working paper from Nov 2025, not yet peer-reviewed but methodologically serious. Uses structural estimation, not just reduced form. Directly answers the theoretical question in H3. The key move — measuring tailoring degree and its wage returns before/after LLM availability — is exactly the kind of design H3 should invoke. Limitation: covers Freelancer.com (a gig labor platform), which may not generalise to salaried entry-level hiring. Freelancer.com has a global, relatively unskilled workforce; the proposal is about OECD formal labor markets.

### Wang (2025) — "Perfect Bayesian Equilibrium in Signaling Games: The Case of Credential Inflation"
- **Link**: DOI 10.54254/2754-1169/2025.gl25939; Semantic Scholar ID 71e41a6869ae81bea740331b36c83cc13cd1258f
- **Key content**: Formalises the standard Spence model and shows rigorously that when signal production cost becomes *less sensitive to ability* (i.e. cost curve flattens), pooling equilibria emerge and education loses signaling power, producing credential inflation. The critical formal result: separating equilibrium requires that the signal cost differential between high- and low-ability types be large enough. If AI makes writing easy for everyone (flattening the cost function), the separating condition fails. The paper then argues that employer responses (ratcheting up credential requirements) is the rational downstream effect.
- **Assessment**: Published in a minor open-access journal ("Advances in Economics, Management and Political Sciences") — not top-tier. But the theoretical point is standard and uncontroversial; the formal derivation is the contribution. Treat as a useful formalism that shows the mechanism, not as an empirical result.

### Spence (1973/1978) — "Job Market Signaling"
- **Link**: Semantic Scholar ID 69fe5f501704543d137de1d47647ce310622259f; original QJE paper
- **Key content**: The canonical model. Signal (education) works as a separator precisely because it is *differentially costly* — cheaper for high-ability types. If AI uniformly reduces the cost of producing the signal (cover letter, coding test, writing sample), the differential collapses and the separating equilibrium unravels into a pooling equilibrium. In the pooling equilibrium, employers cannot distinguish types and offer a pooled (average-ability) wage. High-ability workers are harmed most — they can no longer credibly distinguish themselves.
- **Assessment**: Foundational. Every part of H3 ultimately depends on this mechanism. The Spence model is the right framework; the question is only what observable implications follow at the macro empirical level.

### Kleiner & Krueger (2013) — "Analyzing the Extent and Influence of Occupational Licensing"
- **Link**: NBER Working Paper 14979; Journal of Labor Economics 2013; Semantic Scholar ID c98bf61f15d126cb3eb79cd5c2b3bf15287d9b56
- **Key content**: Estimates that ~29% of US workers hold government-issued occupational licenses, associated with ~18% higher wages. Licensing is a *verifiable* signal (the government certifies it; an LLM cannot generate it), in contrast to writing-based signals (cover letters, portfolio essays) that LLMs can now cheaply produce. Kleiner & Xu (2020) show licensing reduces occupational mobility by ~24%. Han & Kleiner (2021) find positive nonlinear wage effects for licensing duration and that grandfather clauses raise wages for incumbents while raising entry costs for new entrants.
- **Assessment**: High-quality empirical work from leading researchers. Relevant to H3 as follows: if signal erosion is occurring, we should expect a *relative* expansion in demand for verifiable signals (licenses, certifications, degrees) vs. non-verifiable signals (portfolio work, writing samples). The Kleiner literature provides baseline evidence on licensing's wage effects and entry barriers. A testable implication: after 2022, do employers substitute toward licensed occupations or increase license requirements in previously non-licensed knowledge-economy roles? This is currently untested.

### Indeed Hiring Lab (2024) — "Experience the Difference: Why Employers Are Relaxing Some Tenure Requirements"
- **Link**: https://www.hiringlab.org/2024/05/23/tenure-requirements/
- **Key content**: Critical counterevidence. Indeed's job posting data (April 2022 to April 2024) shows that mentions of specific years-of-experience requirements *fell* from ~40% to ~30% of postings. The decline was sharpest in high-education, high-wage sectors (from 66% to 44%). The paper attributes this to a shift toward "skills-first hiring." This finding appears to directly contradict the signal erosion prediction (that credential/experience requirements should *rise*). However: (a) the period is partly pre-ChatGPT scale adoption; (b) the drop may reflect employers removing years-experience as a filter while keeping other screens (take-home tests, portfolio tasks); (c) some of the effect may be a tight labor market forcing employers to loosen requirements. The data is descriptive, not causal.
- **Assessment**: This is the most important empirical challenge to the signal erosion story. The proposal must engage with it. Either the signal erosion hypothesis is wrong, or the transmission channel goes not through experience-requirement inflation but through *other* screening changes (longer funnels, more test stages, more referrals). The Indeed data extends only to mid-2024; the full post-ChatGPT period may tell a different story.

### Rezi.ai (2026) — "The Crisis of Entry-Level Labor in the Age of AI (2024–2026)"
- **Link**: https://www.rezi.ai/posts/entry-level-jobs-and-ai-2026-report
- **Key content**: Industry report synthesising 2024–2025 data. Key empirical claims (with sources cited, mostly third-party): (1) 35% of "entry-level" postings now require prior relevant experience; in software/IT, >60% require 3+ years. (2) Entry-level tech postings fell ~67% in US between 2023–2024; UK tech graduate roles fell 46% in 2024. (3) Entry-level finance positions down 24pp. (4) Gen Z workers now average 1.1 years tenure (38% less than Millennials at same stage). (5) Junior software developer salaries stagnating or declining while senior salaries rise. (6) Healthcare and trades entry-level roles *bucked* the trend, rising 13pp — precisely the sectors where output is verifiable and LLMs cannot fake ability.
- **Assessment**: Industry report, not peer-reviewed. Sources vary in quality. However, the sectoral divergence finding is analytically important: tech/finance (writing-signal-heavy) is contracting entry-level, while healthcare/trades (verifiable-output-heavy) is expanding. This is *consistent with* signal erosion *in combination with* task displacement — but cannot separate the two mechanisms without further controls.

### Fast Company / Ryan Craig (2023) — "How ChatGPT will raise the bar for millions of entry-level jobs"
- **Link**: https://www.fastcompany.com/90889327/how-chatgpt-will-raise-the-bar-for-millions-of-entry-level-jobs
- **Key content**: Journalistic prediction from May 2023 (prescient). Distinguishes the "skills gap" (task displacement) from the "experience gap" (signal erosion by another name): AI may close skill gaps but widen experience gaps, because employers need to verify *judgment*, not just technical output. Uses cybersecurity as a case study: tier-I analyst tasks (detection, response) were automated, so "junior" positions are now de facto tier-II roles requiring 4+ years of experience and CISSP certification. This is an early empirical illustration of the verifiability logic: coding/writing tasks can be LLM-assisted, but accumulated judgment and certification cannot.
- **Assessment**: Journalistic opinion piece, not empirical research. But the cybersecurity example is well-observed and consistent with the theoretical prediction. Useful for illustrative motivation of H3.

### Dariel, Riedl & Siegenthaler (2019) — "Hiring Through Referrals in a Labor Market with Adverse Selection"
- **Link**: SSRN/Maastricht working paper; Semantic Scholar ID ad76da131b202d95a9b9b6b4efadb8e7df119df6
- **Key content**: Experimental evidence that firms shift to referral hiring under information asymmetry/adverse selection, and that referrals improve hiring efficiency. Firms use referrals more when market signals are noisy. This is directly relevant: if LLMs make market signals (writing samples, cover letters) noisier, we would predict increased reliance on referral hiring. Referrals are a signal-independent screening channel — you trust your incumbent employee's endorsement rather than the applicant's self-produced materials.
- **Assessment**: Experimental paper (lab); clean causal evidence but external validity questions. Provides the theoretical and experimental basis for predicting a shift toward referral hiring as a testable consequence of signal erosion. The empirical question — has referral hiring actually increased post-ChatGPT in signal-reliant occupations? — is currently unanswered in the literature.

### Wang (2025) — "Credential Inflation in Signaling Games" (PBE model)
(Already covered above; see main citation.)

---

## Landscape Assessment

### State of knowledge

The theoretical case for signal erosion is clean and well-established via the Spence framework. Galdin & Silbert (2025) provide the first direct econometric evidence that signal erosion from LLMs is real, measurable, and substantial, at least in the gig labor market. The theoretical prediction that credential inflation follows from reduced signal cost is formalised in Wang (2025). The industry data (Rezi.ai) shows sectoral patterns consistent with both task displacement and signal erosion, but the dominant interpretation in public discourse conflates the two.

What is almost entirely absent from the literature is *empirical separation* of the two channels. No paper, to my knowledge, has cleanly identified signal erosion effects separately from demand-side task displacement effects.

### Agreements across sources

- LLMs have materially reduced the cost of producing writing-based job application materials (consensus).
- Entry-level hiring in tech and finance is contracting substantially post-2022 (consensus across industry data).
- Healthcare and trades (verifiable output sectors) are not contracting — possibly expanding (multiple sources agree).
- The theoretical mechanism from Spence to pooling equilibria under reduced signal cost is standard and uncontroversial.
- High-ability workers are the ones harmed most by signal erosion (Galdin & Silbert structural estimate; Spence theory).

### Conflicts and tensions

1. **Indeed Hiring Lab finding vs. signal erosion prediction**: Indeed's data shows experience requirements *fell* in 2022–2024. The signal erosion hypothesis predicts they should *rise*. This tension is not resolved. Possible reconciliations: (a) the labor market was tight in 2022–2023, suppressing experience inflation; (b) employers removed years-experience requirements but added other screens (portfolio tests, coding challenges, multi-stage interviews) — the wrong variable is being measured; (c) the full effect may not yet be visible in the 2024 data.

2. **Task displacement vs. signal erosion — observationally similar in aggregate**: Both mechanisms predict fewer junior jobs and lower wages for young workers. Separating them requires differential predictions, which exist at the *occupational* level but are hard to verify without detailed cross-occupation panel data on screening practices.

3. **Sectoral bifurcation narrative**: Healthcare rising while tech contracts is consistent with signal erosion (healthcare has verifiable output: clinical outcomes, certifications) *and* with task displacement (tech tasks are more automatable). The pattern is consistent with both stories.

### The key identification problem (itays's comment)

The supervisor (itays) asks whether the empirical approach can distinguish the two channels. Here is the identification logic:

**Task displacement** predicts:
- Fewer job postings (demand-side)
- Lower wages at entry level (demand-side)
- Effect uniform across occupations where the task is automatable, regardless of whether output is verifiable

**Signal erosion** predicts:
- *Conditional on having a job*, more credential/experience/certification requirements
- Increased reliance on referral hiring (network-based screening to replace signal-based screening)
- Longer and more staged interview processes
- Higher returns to *verifiable* signals (licenses, degrees from elite institutions, prior employer reputation) vs. unverifiable signals (portfolio essays, cover letters, writing samples)
- The effect should be *larger* in occupations where pre-LLM hiring relied heavily on non-verifiable written signals
- Within the same occupation, experience requirements should rise *more* in signal-reliant sub-roles

The differentiating prediction for H3 is therefore: **conditional on entry-level job postings that survive** (i.e. controlling for the task displacement channel), the *composition* of screening requirements should shift toward verifiable credentials. If signal erosion is the operative mechanism, credential/experience inflation, referral intensity, and returns to verifiable credentials should all increase *more* in writing-heavy occupations after 2022.

### How to make H3 testable

The current H3 ("signal erosion makes it harder for young workers to enter") is descriptive and not falsifiable as written. The supervisor is correct.

A testable formulation requires: (1) a clear prior about *which* observable variable should change and (2) a comparison group where the mechanism does *not* apply.

**Proposed testable version of H3**:

*H3a (screening composition)*: After 2022, among surviving entry-level job postings in knowledge-economy occupations, the share requiring formal credentials (degrees, certifications, licenses) and/or prior verifiable work experience increased significantly more than in occupations where hiring signals were already primarily verifiable before 2022 (healthcare, skilled trades).

*H3b (referral premium)*: After 2022, the wage premium for new hires obtained through referrals (vs. open market applications) increased significantly in signal-reliant occupations, but not in verifiable-output occupations.

*H3c (returns to verifiable credentials)*: After 2022, the wage return to occupational licensing or elite-university credentials increased relatively more for entry-level workers in writing-reliant roles than in roles where employer can directly assess output.

*H3d (Galdin-Silbert replication for formal employment)*: The premium for customised/tailored applications (or for applications not detected as AI-generated) increased post-2022 — i.e., employers are now specifically rewarding the *rarity* of non-AI-generated materials, because the average application is cheap and informationless.

**Empirical approaches available to an MSc dissertation**:

1. **Job posting analysis**: Use Lightcast/Burning Glass or LinkedIn job posting data to track credential/experience requirements over time, split by "writing-reliant" vs. "verifiable-output" occupations. A DID design using ChatGPT launch (Nov 2022) as the shock and occupation-level pre-AI reliance on writing samples as treatment intensity would test H3a directly.

2. **Returns to credentials**: Use CPS or UK LFS data to estimate wage regressions for entry-level workers before and after 2022, interacting a verifiable-credential indicator with the post-ChatGPT period. A DiD on wages would test whether the credential premium rose.

3. **Referral hiring proxy**: Using LinkedIn data, compare the fraction of new hires in signal-reliant vs. verifiable-output occupations who have a first-degree connection at the hiring firm — a proxy for referral. Test whether this fraction rose post-2022 in writing-reliant occupations.

The main data constraint for an MSc dissertation is access to job posting microdata. Lightcast/Burning Glass data is available through many university economics departments. Alternatively, the Galdin & Silbert Freelancer.com design could potentially be replicated on upwork.com or similar platforms for an MSc dissertation scope.

### Gaps and under-explored areas

- **No paper has directly studied whether referral hiring increased post-ChatGPT** in signal-eroded occupations. This is an empirically tractable and novel question.
- **The "screening stage count" channel is unresearched**: If signal erosion leads employers to add more rounds (technical tests, case studies, in-person presentations), total hiring funnel length should increase. LinkedIn data on interview rounds could test this.
- **Wage data by application method (AI-assisted vs. not)** is completely absent from academic literature, though it is implied by Galdin & Silbert's tailoring measure.
- **The distinction between writing-as-signal and writing-as-task** is important but analytically underexplored: in law or consulting, writing may be both a screening signal *and* the actual work product. For these occupations, LLMs simultaneously erode the signal *and* reduce demand — making separating the channels harder. The cleanest tests would use occupations where writing is *only* a signal (e.g., customer service cover letters) not a task.

### Surprises

- The Indeed Hiring Lab data (April 2024) finding that experience requirements *fell* is the most surprising and potentially important counterevidence. This should not be brushed off — it suggests the signal erosion → credential inflation transmission may be slower or weaker than the theoretical prediction, or may require specific conditions (labour market slack, not tightness) to manifest.
- The sectoral divergence in entry-level hiring (healthcare up, tech down) is robust across multiple sources and is consistent with the verifiability logic, but it is *also* consistent with pure task displacement. This is not a free identification.
- The cybersecurity "tier promotion" case (Craig 2023, Rezi 2026) is one of the best natural illustrations of the mechanism: AI automated tier-I tasks, pushing the entry bar up to tier-II; this looks like task displacement but operates *through* a screening norm shift, blending the two mechanisms.
