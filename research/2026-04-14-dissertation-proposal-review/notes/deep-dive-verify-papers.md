# Deep Dive: Citation Verification — Galdin & Silbert (2025) and Brynjolfsson, Chandar, Chen (2025)

## Question

Do arXiv:2511.08785 (Galdin & Silbert) and Brynjolfsson, Chandar, Chen "Canaries in the Coal Mine?" actually exist, say what the survey claimed, and do the specific numeric claims hold up? What is the current state of the identification debate around Canaries, and can the dissertation proposal defensibly use a 2019-vs-2023/24 comparison in light of both papers?

---

## Investigation

### Paper 1: Galdin & Silbert (2025), arXiv:2511.08785

**Confirmed: exists, exact claims verified.**

ArXiv ID 2511.08785 resolves to "Making Talk Cheap: Generative AI and Labor Market Signaling," submitted November 11, 2025. I read the full PDF directly via the author's website (jesse-silbert.github.io).

**Authors and affiliations:** Anaïs Galdin (Dartmouth College, Tuck School of Business) and Jesse Silbert (Princeton University, Department of Economics — job market paper for 2025–26 cycle). Galdin is already an assistant professor at Tuck (PhD Princeton 2024); Silbert is still a doctoral candidate. The paper has generated major press coverage: Financial Times, The Economist, CNN, The Atlantic.

**Data:** Freelancer.com, a global digital labor platform. Data window: January 1, 2021 to July 26, 2024. Pre-LLM sample defined as before ChatGPT launch (November 30, 2022) — approximately 33,000 job postings, 960,000 applications, 92,000 unique workers. Post-LLM sample: approximately 28,000 postings, 1.7 million applications, 135,000 workers. The post-LLM sample is substantially larger in applications, which itself reflects LLM-driven volume inflation.

**The treatment event:** Freelancer.com introduced an on-platform AI proposal-writing tool on April 18, 2023. Workers with certain paid subscriptions could auto-generate applications using an LLM that takes as input both the job description and the worker's profile. The paper can observe click-level data on which applications used this tool.

**Measurement:** A novel LLM-based metric that quantifies how tailored (customized) a given application is to the specific job posting. This is the "signal" variable.

**Three descriptive findings:**
1. Pre-LLM, employers had significant willingness to pay for customized applications — this premium existed and predicted hiring.
2. Post-LLM, this willingness to pay "falls sharply" and the premium "disappears completely."
3. Applications written with the AI tool exhibit a negative correlation between bid-writing effort and the customization signal — indicating the signal has become noise.

**Structural model and counterfactual numbers:**
The 19% and 14% figures are from a counterfactual simulation, not direct empirical estimates. The paper estimates a structural model on *pre-LLM* data only (explicitly stated: "We do not estimate the model on post-LLM data, since our descriptive results suggest that the signaling equilibrium, on which our identification argument relies, has broken down in that period"). The counterfactual is: what would happen if written signals became uninformative (the no-signaling equilibrium)? Answer: top-quintile workers hired 19% less often; bottom-quintile workers hired 14% more often. These figures represent the structural model's prediction of the market becoming less meritocratic, not direct before/after measurements from the data.

**Summary of survey claims vs. actual paper:**
- Uses Freelancer.com: confirmed
- Pre/post LLM design: confirmed (ChatGPT launch as cutoff)
- Wage premium for tailored applications collapsed to zero: confirmed ("disappears completely")
- Structural model with counterfactual: confirmed
- 19% / 14% figures: confirmed, but important nuance — these are counterfactual simulation outputs, not direct DiD estimates
- "Most direct empirical quantification of the signal-erosion mechanism": fair characterization, though the numbers themselves are model-based

**What the survey slightly misrepresents:** The 19% and 14% are not direct empirical measurements of real-world hiring changes. They are structural model predictions of what would happen in a no-signaling counterfactual. The direct empirical finding is that the wage premium for customization disappeared — the structural numbers translate that into hiring probability terms. This is an important distinction for a dissertation proposal, but it does not undermine the paper's usefulness.

---

### Paper 2: Brynjolfsson, Chandar, Chen (2025), "Canaries in the Coal Mine?"

**Confirmed: exists, 16% claim verified with important nuance.**

The paper is titled "Canaries in the Coal Mine? Six Facts about the Recent Employment Effects of Artificial Intelligence," authored by Erik Brynjolfsson (Stanford HAI/SIEPR), Bharat Chandar (Stanford Digital Economy Lab postdoc), and Ruyu Chen (Stanford Digital Economy Lab research scientist). Most recent version: November 13, 2025. Full paper available at digitaleconomy.stanford.edu. The "16%" figure in the abstract of the November 2025 paper reads: "early-career workers (ages 22-25) in the most AI-exposed occupations have experienced a 16 percent relative decline in employment even after controlling for firm-level shocks."

**Data:** ADP payroll data — the largest payroll software provider in the US, covering approximately 25 million workers. AI exposure measure from Eloundou et al. (2024), scored 0–1 by occupation, assigned to quintiles.

**What "16%" means:** This is a relative decline measured from October 2022 (around ChatGPT launch) to approximately July–October 2025. It is a relative measure — 22–25 year-olds in the most AI-exposed quintile compared to less-exposed workers. The absolute number matters: the Dallas Fed's independent CPS replication (Atkinson and Yamco, January 2026) found a 0.9 percentage-point decline in employment share for young workers in most-AI-exposed occupations since November 2022 — a smaller absolute number, though consistent in direction.

**The February 2026 blog post:** Published February 9, 2026 on the Stanford Digital Economy Lab website. Full title: "Canaries, Interest Rates, and Timing: More on the Recent Drivers of Employment Changes for Young Workers." Authors: Brynjolfsson, Chandar, Chen. This post addresses two specific questions:

1. Can rising interest rates explain the disproportionate decline in AI-exposed entry-level occupations better than AI itself?
   - Finding: No. Using data from Zens et al. (2020) on occupational interest rate sensitivity, they find AI-exposed jobs are *negatively* correlated with interest rate sensitivity (construction workers: high rate sensitivity, low AI exposure). The pattern holds within both high- and low-interest-rate-exposed occupational groups.

2. Is the timing consistent with AI causation?
   - This is where the post makes a crucial concession. With firm-time fixed effects (their most stringent specification), the employment decline for AI-exposed young workers "starts becoming notable in 2024" — not late 2022 or 2023 as in their main figures. The earlier declines are "likely (at least partly) due to some combination of other factors, not just AI."
   - Updated figure: With the extended dataset through October 2025, the firm-time fixed-effects specification shows approximately 16% decline (same number, but the earlier version in the paper only had data through July 2025, showing 13%).

**Critical nuance on the timing concession:** The February 2026 post is a partial concession, not a defense. The authors' own most rigorous specification — controlling for firm-level employment shocks — pushes the significant effect to 2024 only. This is exactly the pre-trend problem. The 2022 baseline in their main figures partly captures a post-pandemic tech sector contraction that preceded widespread AI adoption. The more causally credible finding is a 16% decline becoming significant in 2024, sustained through October 2025.

---

### The "Frank et al. (2026) pre-trend critique": Misidentified

The survey agent claimed the February 2026 blog post "responded to Frank et al. (2026)" and that this "defends the result against the Frank et al. (2026) pre-trend critique." This characterization is inaccurate in two ways:

1. **"Frank et al. (2026)" does not appear to exist as a pre-trend critique paper.** What exists is Frank, Ahn & Moro (2025), published in PNAS Nexus, April 2025 — but this paper studies unemployment risk using data from 2010–2020 (entirely pre-ChatGPT) and does not raise pre-trend concerns about Canaries specifically.

2. **The February 2026 blog lists "Frank et al. (2025)" in a general bibliography** of papers exploring AI employment effects, with no specific engagement. The blog says these papers "each use different data and methods, and thus subject to different strengths and weaknesses." This is not a targeted response to a Frank critique.

3. **The actual pre-trend concession in the February 2026 post is self-generated**, not a response to any external critic. The Canaries authors themselves discovered that with firm-time effects, significance only appears in 2024. The AEI commentary (Orrell, August 2025) raised the 2022 base-year issue, and the paper's own November 2025 version already flagged it. There is no specific "Frank et al. (2026) pre-trend critique paper" that the blog responds to.

The survey agent appears to have hallucinated the "Frank et al. (2026)" attribution or confused Frank, Ahn & Moro (2025) with a targeted pre-trend critique that does not exist.

---

### The Reconciliation Question: Can the Proposal Use 2019-vs-2023/24?

**The identification problem is real but not fatal, if handled correctly.**

The Canaries finding, as confirmed, shows that when firm-time effects are included, the employment gap only becomes significant in 2024. This means a simple 2019-vs-2023/24 comparison in a dissertation proposal has an identification problem: the 2021–2022 tech sector contraction (post-pandemic overhiring correction) will contaminate the 2019-vs-2023/24 gap.

However, this is a narrower concern than it first appears:

- The contamination is concentrated in software/tech occupations specifically. The Chandar primer explicitly notes "the precipitous decline in employment for young software developers is a consequence of various factors." For other AI-exposed occupations (customer service, clerical), the pre-2023 trend is less problematic.
- The Dallas Fed (CPS-based) independent replication confirms the directional result for young workers in high AI-exposure occupations, using data back to 2022 as a baseline — consistent with a real, if modest, effect.
- The full Canaries paper shows the result holds "after controlling for firm-level shocks" even in their main specification. The 13% figure in the paper already has some robustness to this.
- The Galdin & Silbert paper sidesteps this problem entirely by using within-platform variation (pre/post ChatGPT on Freelancer.com), exploiting a specific on-platform tool introduction as a sharper treatment event.

**Practical implication for the proposal:** A 2019-vs-2023/24 comparison is defensible if the proposal explicitly acknowledges the pre-trend concern and designs around it. The cleanest approaches would be: (a) use 2022 (ChatGPT launch) as the pre-period rather than 2019 to avoid the tech-sector contraction contamination; or (b) use occupation-level heterogeneity in AI exposure as a triple-difference, comparing young vs. older workers within AI-exposed vs. unexposed occupations to difference out the tech contraction; or (c) limit the analysis to occupations where the pre-trend concern is minimal (non-tech AI-exposed occupations).

Using 2019 as the pre-period without addressing the 2021–2022 confound would be vulnerable to a straightforward critique. But the Canaries result, appropriately cited, provides evidence that a real phenomenon exists — the proposal can cite the *2024* result as the cleaner causal estimate and frame the 2019 baseline as establishing the long-run trend.

---

## Key Findings

- **Galdin & Silbert (2025) is real, confirmed, and the survey's claims are accurate.** (Strong evidence) ArXiv:2511.08785 exists, uses Freelancer.com, employs a pre/post-ChatGPT design (data January 2021–July 2024), has a structural model, and produces the exact 19%/14% counterfactual figures. Galdin is at Dartmouth Tuck; Silbert is a Princeton PhD candidate (job market paper). Institutional weight: high.

- **One nuance on the 19%/14% numbers:** These are counterfactual structural model predictions, not direct DiD estimates. The direct finding is that the wage premium for customized applications disappeared post-LLM. (Strong evidence)

- **Brynjolfsson, Chandar, Chen "Canaries" (2025) is real and the 16% claim is confirmed.** (Strong evidence) November 13, 2025 version, Stanford Digital Economy Lab, using ADP payroll data on 25 million workers. Ages 22–25, most AI-exposed quintile, relative to less exposed workers.

- **The February 2026 blog post is real, dated February 9, 2026.** (Strong evidence) It addresses interest rates (no effect) and timing (firm-time effects push significance to 2024). The 16% figure in the blog reflects the updated data through October 2025 with firm-time fixed effects — up from 13% in the July 2025 data.

- **The "Frank et al. (2026) pre-trend critique" cited by the survey agent does not appear to exist.** (Strong evidence — absence confirmed) The February 2026 blog does not respond to Frank et al. as a specific critique. "Frank et al. (2025)" appears in their bibliography as one of several related papers. The pre-trend concession in the February 2026 blog is the authors' own finding, not a defense against external criticism.

- **The identification concern is genuine but manageable.** (Moderate evidence) The Canaries authors' own most rigorous specification only shows significant effects from 2024, not 2022. For a dissertation proposal using a 2019 baseline, this is a real vulnerability that requires explicit methodological acknowledgment and design choices to address.

---

## Assessment

Both papers are genuine, high-quality, and citable. The survey agent's characterization of Galdin & Silbert is essentially correct — the only refinement is that 19%/14% are structural counterfactual outputs rather than raw DiD estimates, which is actually a strength (they have a theoretical mechanism, not just a reduced-form number). Galdin & Silbert is the cleanest available paper for the signal-erosion mechanism, with Princeton/Dartmouth institutional weight, major media coverage, and a transparent pre/post design.

For Canaries, the 16% figure is confirmed but sits at the end of a methodological spectrum. The main-text figure (no firm-time effects) shows 16% relative decline from October 2022 to October 2025. The firm-time specification, which is arguably the more causally credible estimate, shows the same 16% but as a 2024-onward phenomenon, not a 2022-onward one. This distinction matters enormously for a proposal using a 2019 pre-period.

The claim that the February 2026 blog "responds to Frank et al. (2026)" is fabricated — there is no such paper, and the blog does not respond to it. The blog's key contribution is the authors' own timing concession, which the proposal must acknowledge rather than suppress.

**Recommendation for the final report:** Cite Galdin & Silbert at face value — the claims are accurate. Cite Canaries with explicit acknowledgment that the causally credible window (firm-time effects) is 2024-onward, not 2022-onward. Drop any mention of "Frank et al. (2026)" — it does not exist. The proposal's 2019-vs-2023/24 design needs a methodological section that distinguishes the pre-trend concern from the AI-onset effect, or it should reconsider the 2022 ChatGPT launch as the pre-period. The Galdin & Silbert paper is actually more useful here because its design (pre/post ChatGPT on a single platform with a platform-specific AI tool event) is far cleaner causally.
