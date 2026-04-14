# Orchestrator Log — Dissertation Proposal Review

## Scoping

**Broad task**: The user wrote an MSc dissertation proposal on "Is Generative AI Tightening Occupational Entry for Young Workers?" using a shift-share design. Two supervisors (itays and iPad) left detailed comments. The user has been away from the proposal for a while and wants: (1) an accessible explanation of what the proposal is trying to do, (2) concrete improvements, (3) every supervisor comment addressed. The user is going to bed, so we run multiple survey→review→deep-dive cycles.

**Supervisor comments — the substantive concerns** (not just structural):

1. **The identification puzzle (iPad, p.5 — self-described "key concern")**: The shift-share exposure Z_c varies at the CZ level, but the outcome is entry into *high-exposure occupations* specifically. Why does location-level variation predict occupation-specific entry? The theoretical link is not obvious.

2. **Signal erosion vs. task displacement (itays, p.7)**: Both channels affect young workers. Can the empirical approach distinguish them?

3. **H3 is not testable (iPad, p.5)**: Signal erosion is stated as a narrative, not as a falsifiable hypothesis.

4. **Entry-before-exits is overclaimed (iPad, p.2)**: Jaimovich et al. (2020) doesn't mean unemployment *doesn't* respond short-run. And occupational flows should change for all workers, not just young.

5. **Magnitude of beta (iPad, p.6)**: How will you interpret the magnitude? Matters for H1 and for comparing across outcome variables.

6. **Alternative channel (itays, p.1)**: AI may simply be more effective at replacing entry-level skills directly — not just eroding signals.

7. **Structural: shift-share before data (itays, p.4)**: If shift-share variables appear in the data section, describe the design first.

8. **Aggregation question (itays, p.4)**: Why aggregate to high/medium/low exposure groups at occupation level when the shift-share aggregates to locality level?

9. **Report DD results too (iPad, p.6)**: Show DD by age group alongside the DDD.

10. **Construction of licensing/O*NET proxies (iPad, p.5)**: More detail needed on how these are built.

**Narrowed research questions** (what the survey agents will investigate):

**Q1 — The shift-share identification puzzle**: What does the shift-share literature (Borusyak-Hull-Jaravel 2022, Adão-Kolesár-Morales 2019, Goldsmith-Pinkham et al. 2020) actually require for valid identification? Is the proposal's setup — CZ-level exposure predicting occupation-specific entry — coherent? What would fix it if not?

**Q2 — Signal erosion testability**: What would a properly testable version of H3 look like? Can signal erosion be empirically separated from task displacement? What does the signaling/screening literature (Spence 1973 and descendants) suggest about testable implications?

**Q3 — The entry-before-exits claim**: Does the automation adjustment-margin literature (Jaimovich et al. 2020, Cortes et al. 2020, Dauth et al. 2021) actually support the specific claim that *young workers' entry* is the first margin to move? Or is the proposal reading this literature too selectively?

**Q4 — Current empirical landscape**: What do the key cited papers actually find? Are there newer results (post-March 2026)? Does the proposal characterize the evidence correctly?

These four questions are sharp enough that deep answers to any one of them would materially improve the proposal.

## Survey round 1 — key findings

**Q1 (shift-share)**: The supervisor's concern is structurally correct. No canonical shift-share application (ADH 2013, Acemoglu-Restrepo, Dauth et al., Bonfiglioli et al.) uses a CZ-level instrument with occupation-specific outcomes. Mohnen (2025) endorsed by BHJ is the closest template — uses CZ-level instrument with CZ-level outcomes including the *share* of young workers in specific occupation groups. Fix: change outcome to CZ-level aggregate (share of young workers in high-exposure occupations).

**Q2 (signal erosion)**: Theoretical foundation is solid (Spence 1973; Wang 2025 formalises pooling when signal cost becomes ability-insensitive). Galdin & Silbert (2025, arXiv) on Freelancer.com data is the quantified version of H3 — tailored-application wage premium collapsed to zero post-LLM. Key counterevidence: Indeed Hiring Lab (2024) shows experience requirements *fell* 2022-2024. Testable H3: job-posting microdata (Lightcast) to test whether credential/referral requirements rose more in writing-reliant occupations than in verifiable-output occupations.

**Q3 (entry-before-exits)**: Proposal is reading the literature selectively. Cortes et al. (2020) finds inflow decline for *all* workers, not young specifically (Swiss replication finds middle-aged most affected). Jaimovich et al. (2021 JME) ≠ Jaimovich-Siu (2020 ReStat); the latter explicitly documents cyclical unemployment response. Dauth et al. is the strongest support but is German manufacturing with strong employment protection. **The cleanest support is actually from papers the proposal doesn't cite**: Brynjolfsson, Chandar, Chen (2025) "Canaries in the Coal Mine" — 16% relative employment decline for 22-25-year-olds in AI-exposed occupations. Lodefalk et al. (2026) — 5.5% gap in Swedish register data.

**Q4 (empirical landscape)**: Two serious issues. (i) Frank et al. (2026) pre-trends begin in 2021-2022 — this directly undermines a 2019 vs 2023-24 comparison. (ii) Missing "Canaries in the Coal Mine" (Brynjolfsson et al. 2025) is a significant gap — it's the most directly relevant paper to the proposal's core thesis. Anthropic papers are not peer-reviewed and Massenkoff-McCrory young-worker result is described by authors as "just barely statistically significant."

## Review round 1 — CONTINUE, four deep dives assigned

1. Verify Mohnen (2025) template
2. Verify Galdin & Silbert and Canaries papers
3. Magnitude of β + DD vs DDD + H4 under fix
4. O*NET and licensing measurement

## Deep dive round 1 — key findings

**DD1 (Mohnen template) — MAJOR CORRECTION**: Mohnen (2023 JoLE, not 2025) is an *exogenous-shares* design (age-composition shares tailored to retirement mechanism). The proposal is an *exogenous-shifts* design (generic occupation shares, technology shock shifts). These are **structurally different** identification paths in the BHJ framework. The proper template is **Acemoglu-Restrepo (2020)** for generic shares + technology shifts, with **Bonfiglioli et al. (2024/2025)** as the AI-specific parallel. Mohnen can only be cited narrowly for the level-of-analysis point (CZ aggregates), not as the identification template.

**DD2 (Paper verification) — CORRECTIONS**:
- **Galdin & Silbert (2025)** confirmed real at arXiv:2511.08785. Freelancer.com data, Jan 2021–Jul 2024. Uses Freelancer's April 2023 AI proposal-writing tool rollout as treatment event. **Nuance**: the 19%/14% figures are counterfactual structural model predictions (model estimated on pre-LLM data), not direct DiD estimates. The reduced-form result is that the wage premium for tailored applications disappears post-LLM.
- **Brynjolfsson Canaries (2025)** confirmed real, Stanford Digital Economy Lab, ADP data. 16% relative decline for 22-25-year-olds in AI-exposed occupations. **Survey error corrected**: the February 2026 blog post does NOT respond to "Frank et al. (2026) pre-trend critique" — that critique doesn't exist. Frank, Ahn & Moro (2025 PNAS Nexus) uses 2010-2020 data, pre-ChatGPT, no engagement with Canaries. However, the Feb 2026 blog does contain the authors' own pre-trend concession: **firm-time FE specification only becomes significant from 2024, not 2022-2023**. This is important for the proposal's window.

**DD3 (Magnitude/DD/H4)**:
- **Magnitude**: standardize Z_c to mean 0, SD 1 (Bonfiglioli template). Report β in 3 framings: pp change per 1 SD; 25th→75th percentile equivalent; % relative to pre-period mean entry rate.
- **DD alongside DDD**: Olden & Møen (2022) formally decompose DDD = DD_young − DD_old. Report three columns (DD_young, DD_old, DDD) plus event-study plots.
- **H4 rescue**: does NOT survive Option 1 fix as originally stated. Rescue via split-outcome: two CZ-level outcomes — share of young workers in *licensed* vs. *unlicensed* high-exposure occupations. Cleanest natural contrast: Accountants/Auditors (high ζ, CPA licensure) vs. Writers/Programmers/Analysts (high ζ, unlicensed).

**DD4 (O*NET/licensing)**:
- **Minimal O*NET proxy**: Writing Importance (2.A.1.c) + Critical Thinking Importance (2.A.2.a), average after standardization. Deming (2017) precedent.
- **Stronger**: Add Work Context written correspondence (4.C.1.a.2.h Email, 4.C.1.a.2.j Memos) with inverse Job Zone weighting.
- **Peer-review grade**: Follow Felten et al.'s AIOE architecture.
- **Licensing**: Use CPS Certifications and Licenses supplement (since 2015, via IPUMS CPS).
- **Overlap problem is real**: clean high-exposure-AND-licensed group is CPAs/auditors, lawyers, financial advisors, teachers. Most high-exposure occupations (writers, programmers, analysts) are unlicensed.

## Review round 2 — dispatched
