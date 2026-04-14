# Deep Dive: O*NET Signal-Reliance Proxies and Occupational Licensing Data Pipeline

## Question

What specific O*NET variables should be used to construct "signal-reliance" proxies (the degree to which entry into an occupation depends on demonstrable outputs an LLM could contaminate), and what occupational licensing data source is feasible for an MSc thesis? How should both be bridged to ACS/CPS occupation codes?

---

## Investigation

### Part A: O*NET Variable Landscape for Signal-Reliance

**Confirmed database version**: O*NET 30.2 (current production release as of March 2026, updated quarterly). Download from onetcenter.org under CC BY 4.0. All 40 files available as Excel, tab-delimited text, MySQL, or SQL Server.

The O*NET 30.2 database confirmed the following relevant files:
- `Skills.xlsx` — 62,580 rows; two scale IDs per element: `IM` (Importance, 1–5) and `LV` (Level, 0–7); analyst-rated
- `Work Context.xlsx` — 297,676 rows; Scale ID `CX` (mean rating) and `CXP` (percent endorsing each category); incumbent-reported
- `Job Zones.xlsx` — 923 rows; integer 1–4 (updated in 30.2 to a new four-level framework reflecting increased skill demands)
- `Work Activities.xlsx` — generalized and detailed work activities with Importance and Level scales
- `Abilities.xlsx` — including Written Expression (1.A.1.a.4) and Written Comprehension (1.A.1.a.2)

**Specific element IDs confirmed by O*NET content model documentation**:

Skills (file: `Skills.xlsx`, Element ID format `2.A.x.x`):
- `2.A.1.c` — Writing (Importance and Level)
- `2.A.1.d` — Speaking (Oral communication Importance and Level)
- `2.A.1.a` — Reading Comprehension
- `2.A.2.a` — Critical Thinking
- `2.A.2.b` — Active Learning
- `2.B.2.i` — Complex Problem Solving

Abilities (file: `Abilities.xlsx`, Element ID format `1.A.x.x`):
- `1.A.1.a.3` — Oral Expression
- `1.A.1.a.4` — Written Expression
- `1.A.1.a.1` — Oral Comprehension
- `1.A.1.a.2` — Written Comprehension
- `1.A.1.b.2` — Originality
- `1.A.1.b.4` — Deductive Reasoning

Knowledge (file: `Knowledge.xlsx`):
- `2.C.7.a` — English Language

Work Activities (file: `Work Activities.xlsx`, Element ID format `4.A.x.x`):
- `4.A.2.a.4` — Analyzing Data or Information
- `4.A.2.b.1` — Making Decisions and Solving Problems

Work Context (file: `Work Context.xlsx`, Element ID format `4.C.x.x`):
- `4.C.1.a.2.j` — Written Letters and Memos (frequency/importance)
- `4.C.1.a.2.h` — Electronic Mail (frequency)
- `4.C.1.a.2.c` — Public Speaking (frequency)
- `4.C.1.a.2.l` — Face-to-Face Discussions (frequency)

**Important note on Work Context scale**: Work Context uses a "context" scale (CX), not the standard Importance/Level. The categorical distribution (CXP) gives percent of respondents endorsing each frequency level. For written correspondence, category values represent never / less than once a month / once a month / once a week or more / every day. Use the mean CX value (Data Value column where Scale ID = "CX") for a continuous score.

### Part B: Prior Papers Using O*NET for AI Exposure or Screening-Related Measures

**Eloundou et al. (2023), "GPTs are GPTs"** (ARXIV:2303.10130, 525 citations):
The seminal paper. Uses O*NET task descriptions (from the Task Statements file) and a rubric assessing whether LLM access would reduce task completion time by ≥50%. Key methodological point: they use task-level text, not the structured numerical variables (Importance, Level). The exposure measure (alpha, beta, zeta) is at the task level, aggregated to occupation. They do not use Writing Importance or Work Context directly — they score free-text task descriptions against an LLM capability rubric. This is the standard comparison point for any new proxy.

**Felten, Raj, Seamans (2018/2023)**, "A Method to Link Advances in AI to Occupational Abilities" (179 citations):
Used O*NET Abilities scores (the 1.A.x.x elements) — specifically 52 occupational abilities — weighted by their Importance scores. Surveyed Amazon MTurk workers on relatedness between AI applications (language modeling, image generation) and each ability. The AIOE (AI Occupational Exposure) index is: for each occupation, take the weighted average of ability scores where the weights are the MTurk-reported AI-ability relatedness scores. Uses `IM` (Importance) scale from the Abilities file. This approach is directly comparable to a signal-reliance proxy using the same file structure.

**Deming (2017), "The Growing Importance of Social Skills"** (QJE, 1508 citations; DOI:10.1093/QJE/QJX022):
Used O*NET Skills data to construct a social skills index. Relevant methodological point: he standardizes each skill's Importance score across occupations (z-score), then averages selected skills within a category. This is the cleanest MSc-level precedent for a custom index from the Skills file. He used elements like Social Perceptiveness, Coordination, Negotiation, Persuasion — which are exactly the non-LLM-replicable skills. The complement of this — Writing, Critical Thinking, Complex Problem Solving — is exactly the signal-reliance space.

**Autor, Levy, Murnane (2003), "The Skill Content of Recent Technological Change"** (4,507 citations; NBER WP 8337):
The task-based framework. Used Dictionary of Occupational Titles (DOT), the predecessor to O*NET. Constructed routine cognitive, routine manual, nonroutine cognitive-analytic, nonroutine cognitive-interpersonal, and nonroutine manual indices. The "nonroutine cognitive analytic" category included math, reasoning, and language ability — highly relevant as a precursor to signal-reliance. The ACS/CPS crosswalk challenge began here: they matched DOT occupation codes to Census occupation codes.

**Brynjolfsson, Mitchell, Rock (2018), "What Can Machines Learn?"** (512 citations):
Developed a machine learning suitability (MLS) rubric applied to O*NET Detailed Work Activities. Relevant: they use DWA-level text scoring, showing that text-based task scoring is the more rigorous approach vs. aggregated ability scores.

**Felten et al. (2023) AIOE generative AI update**:
Extended the 2018 method to focus on language modeling and image generation specifically. The AIOE is calculated as an average of O*NET ability scores weighted by AI-ability relatedness, collapsed from 8-digit to 6-digit SOC. This is directly usable as a baseline.

**Maya (2026), "Measuring What Cannot Be Surveyed"**:
Validates LLM-scored O*NET task statements against six existing AI exposure indices. Finds r=0.85 with Eloundou GPT-gamma and r=0.79 with Felten AIOE. Confirms that structured variable approaches (Abilities × weights) and text-scoring approaches converge.

### Part C: Conceptual Mapping — What "Signal Reliance" Means vs. Eloundou Exposure

The dissertation distinguishes **signal reliance** from simple **AI exposure**. This is crucial. Eloundou measures: can an LLM reduce task completion time? Signal reliance measures: does entry into the occupation depend on a worker demonstrating outputs (essays, code, analysis) that an LLM could ghost-write, thereby corrupting the screening signal?

These are correlated but conceptually distinct:
- A truck driver has low AI exposure (Eloundou) and low signal reliance — not an output-based entry screen.
- A paralegal has high AI exposure AND high signal reliance — writing samples and memos are the screening mechanism.
- A nurse has moderate AI exposure but low signal reliance — entry gated by clinical placement, not text outputs.
- A software engineer has high AI exposure AND high signal reliance for some entry paths (take-home coding tests) but not others (whiteboard interviews).

**This distinction motivates using Work Context items** (how important are written outputs IN THE JOB) as proxies for the screening mechanism, because jobs where written correspondence is central are precisely the ones where employers use writing samples in hiring.

### Part D: Constructing the Signal-Reliance Index

**Minimal viable (MSc-level) construction**:

Load `Skills.xlsx` from O*NET 30.2. Filter to Scale ID = "IM" (Importance). Extract for each occupation:
1. `2.A.1.c` Writing Importance (range 1–5)
2. `2.A.1.d` Speaking Importance (range 1–5) — for an oral communication intensity measure
3. `2.A.2.a` Critical Thinking Importance
4. `4.A.2.a.4` Analyzing Data or Information Importance (from Work Activities file)

Standardize each variable (z-score across all 923 occupations) and average. This gives a "cognitive-textual task intensity" index analogous to Deming's social skills index. Call it `sig_reliance`.

For the written correspondence channel specifically, add from `Work Context.xlsx` (Scale ID = "CX"):
- `4.C.1.a.2.j` Written Letters and Memos mean score
- `4.C.1.a.2.h` Electronic Mail mean score

Average the two Work Context items (also z-scored), call this `written_output_intensity`.

**Strongest peer-review-ready construction**:

Follow Felten et al.'s AIOE architecture but invert the purpose. Instead of asking "is this ability exposed to AI?", ask "is this ability one that employers verify through LLM-contaminated output?" Concretely:

Step 1: Identify the set of O*NET Abilities most associated with screening-relevant outputs. From `Abilities.xlsx`, use:
- `1.A.1.a.4` Written Expression (Importance × Level / 2)
- `1.A.1.b.2` Originality (Importance × Level / 2)
- `1.A.1.b.4` Deductive Reasoning (Importance × Level / 2)
- `1.A.1.b.5` Inductive Reasoning (Importance × Level / 2)

Step 2: Weight each ability by a "contamination susceptibility" coefficient — the probability that an LLM can replicate this ability in a short-form demonstration. Use Felten et al.'s published MTurk relatedness scores for language modeling as these weights (publicly available in their replication data).

Step 3: Take the ability-weighted average per occupation. This yields a measure where high values = "occupation's key demonstrable abilities are highly LLM-replicable."

Step 4: Multiply by (1 − Job Zone) normalized, as a penalty for high-entry-requirement occupations where in-person verification dominates. (Job Zone 4 = requires Bachelor's or above and extensive experience, so screening is less pure-text-based.)

The minimum defensible specification for a thesis committee: standardized Writing Importance + standardized Critical Thinking Importance, averaged. Two variables, interpretable, directly sourced from O*NET Skills, precedent in Deming (2017).

### Part E: Occupational Licensing Data Sources

**CPS Certifications and Licenses Supplement (since January 2015)**:
Questions added to the regular monthly CPS beginning January 2015. Key variables distinguish: (a) does the respondent hold ANY license or certification, (b) is it a GOVERNMENT-ISSUED license (conveying legal authority to work, as opposed to a voluntary certification from a non-governmental body). The supplement runs annually thereafter. IPUMS CPS provides harmonized access. Key characteristic: this is INDIVIDUAL-level, not OCCUPATION-level. To create an occupation-level binary, one aggregates: "share of employed workers in occupation X who report holding a government-required license" — which is precisely the prevalence measure used by Kleiner and subsequent researchers. Coverage: nationally representative, ~60,000 households per month, linked to 3-digit and 6-digit SOC codes via Census occupation codes (OCC).

**Kleiner / OLLRP Database (WVU Knee Center, 2025 Version 1)**:
URL: https://knee.wvu.edu/data/ollrp-database. Compiled by Kleiner, Hicks, Marson et al. with support from Smith Richardson Foundation, Russell Sage, and others. Currently covers ~12 occupations in partial detail (Cosmetologist, LPN, Massage Therapist, Professional Counselor, Respiratory Therapist, Dispensing Optician, plus 4 universally-licensed occupations: Optometrist, Physician Assistant, Physician, RN). Historical coverage from 1870 to 2019 for ~300 occupations or license categories (via Carollo's SSRN paper). Variables: education hours, weeks experience, number of exams, renewal fees, minimum age, criminal record restrictions, reciprocity agreements. Coverage issue for this thesis: most of the historically-covered occupations are health, legal, or trades — many of the high-AI-exposure occupations (analysts, programmers, writers) are NOT covered.

**NCSL / CSG National Occupational Licensing Database (2017, updated 2022)**:
URL: https://licensing.csg.org/the-database/ and https://www.ncsl.org/labor-and-employment/the-national-occupational-licensing-database. 48 occupations selected on criteria: licensed in ≥30 states, no 4-year degree requirement, positive employment growth. Covers: plumbers, electricians, EMTs, nurses, cosmetologists, real estate agents, dental hygienists, etc. Variables: education hours, weeks experience, number of exams, fees, age minimums, good-moral-character requirements, criminal record restrictions, reciprocity. Key limitation: explicitly excludes occupations requiring a 4-year degree. This excludes accountants, lawyers, teachers at the bachelor's+ level, and virtually all the high-AI-exposure professional occupations.

**KRRC Annual Licensing Database Snapshot (2023–2025)**:
URL: https://knee.wvu.edu/publications/knee-center-research/2025/12/19/annual-licensing-database-snapshot-2025. Covers 77 professions as of 2025. Annual snapshots downloadable in Excel and Stata. Variables standardized to hours, biennial renewal periods. Adds "multiple pathways" indicator. This is newer and more comprehensive than the NCSL database for the covered occupations but still focused on sub-baccalaureate trades and health professions.

**Institute for Justice "License to Work" (2017, 2022, 2024 reports)**:
IJ's reports cover ~100+ low-to-moderate income occupations across all 50 states. Captures how many states license each occupation, average education hours required, fees, and IJ's "burden" score. Primarily designed for policy advocacy, not longitudinal research. The data is reported in the publications and on ij.org; a scrape or request to IJ may yield structured data. Not designed for academic panel use.

**PlainCredential** (plaincredential.com): Aggregates NCSL and IJ data for 97 professions, 51 jurisdictions. Free, no paywall. Useful for spot-checks but not primary research data.

### Part F: The Licensing × AI-Exposure Overlap Problem

The dissertation's H4 (licensing moderates AI exposure's effect on entry) requires a meaningful set of occupations that are both (a) high AI exposure and (b) licensed. Let me map this explicitly.

**High AI exposure by Eloundou et al.** (top exposed, ≥50% tasks affected with LLM+software): software developers, mathematicians, financial analysts, writers/authors, accountants/auditors, legal secretaries, paralegals, customer service reps, translators/interpreters, data scientists, budget analysts, insurance underwriters, tax preparers.

**Licensed occupations in available datasets**:
- CPS-derivable (individual-level data → occupation-level prevalence): registered nurses, lawyers, teachers, doctors, dentists, pharmacists, physical therapists, real estate agents, electricians, financial advisors.
- NCSL/KRRC (structured database): real estate agents, nurses (LPN, RN), EMTs, dental hygienists, cosmetologists, electricians, plumbers.

**The overlap**:
- Accountants / CPAs: high AI exposure + CPA license (universally licensed at state level). This is the clearest case. CPA requires passage of Uniform CPA Exam + state-specific education/experience.
- Lawyers / paralegals: lawyers are licensed (bar exam); paralegals are NOT universally licensed (only a handful of states). Paralegals have high AI exposure. The distinction between licensed lawyers and unlicensed paralegals is itself interesting.
- Financial advisors / securities: Series 7 license (FINRA-administered, state-registered). High AI exposure for financial analysts. The securities licensing data is not in NCSL/KRRC but is derivable from CPS.
- Teachers: licensed in all states + high AI exposure for certain tasks. But teacher licensing is a credential barrier distinct from the screening-by-output mechanism.
- Insurance sales agents: in NCSL database, moderately high AI exposure.
- Real estate agents: universally licensed, moderate AI exposure.

**Assessment of overlap adequacy**: The overlap is non-trivial but narrower than the proposal might imply. The cleanest high-exposure + licensed set is: accountants (CPA), lawyers, financial advisors (securities license), and teachers. Paralegals are borderline. The major high-exposure occupations — software developers, data scientists, writers, customer service reps — are overwhelmingly UNlicensed.

For H4 to have statistical power, the dissertation needs to define licensing either (a) as a binary at the occupation level using CPS prevalence (% of workers in that occupation who self-report a government-required license) or (b) by merging in a simple licensed/not-licensed occupation-level flag from the NCSL database with manual expansion to cover professional licenses (CPA, bar, Series 7, teaching).

The CPS prevalence approach is preferable because it (1) uses actual self-reports, (2) covers all occupation codes, and (3) is available at the SOC-level granularity that matches O*NET. The NCSL database approach is preferable if one wants intensity of licensing (hours of training required) rather than just binary licensed/not, but it only covers 48 occupations.

### Part G: SOC–Census OCC Crosswalk

This is the critical pipeline problem. O*NET uses O*NET-SOC codes (e.g., "15-1256.00" for Software Developers). The CPS and ACS use Census OCC codes (2018 version, derived from 2018 SOC, introduced in the 2019 ACS). Prior years used 2010 Census OCC (derived from 2010 SOC).

**Exact crosswalk files**:
- Census Bureau provides: https://www2.census.gov/programs-surveys/demo/guidance/industry-occupation/2018-occupation-code-list-and-crosswalk.xlsx — this maps 2018 Census OCC to 2018 SOC.
- For pre-2019 ACS/CPS data: use 2010-occ-codes-with-crosswalk-from-2002-2011.xls from the same Census directory.
- For the transition: "Tables E1-E3: 2010 to 2018 Occupation Conversion Rates" from census.gov/data/tables/time-series/demo/industry-occupation/acs-tp78.html gives probabilistic conversion rates between 2010 and 2018 Census OCC codes.

**O*NET SOC to Census OCC bridge**: O*NET uses 6-digit SOC (e.g., 15-1256) which maps to 2018 SOC. The Census 2018 OCC is derived from 2018 SOC but aggregates some 6-digit SOC codes into a single Census OCC. The Census crosswalk file (2018-occupation-code-list-and-crosswalk.xlsx) contains the explicit mapping. The link is many-to-one: multiple 6-digit SOC codes often map to a single Census OCC. When aggregating O*NET variables to the Census OCC level, use employment-weighted averaging across the constituent 6-digit SOC occupations. BLS Occupational Employment and Wage Statistics (OEWS) provides employment counts by 6-digit SOC.

**IPUMS CPS** (cps.ipums.org) provides harmonized OCC codes across CPS years, standardized to 2010 Census OCC for 2009–2018 and 2018 Census OCC for 2019+. Using IPUMS is strongly recommended over raw CPS microdata for this thesis.

**Known mapping problems**:
1. O*NET has 923 occupation codes; 2018 Census has ~500 OCC codes. Some Census OCC codes aggregate 2–5 O*NET occupations. For common broad occupations (e.g., "Computer programmers"), the aggregation is substantial and can blur within-category heterogeneity.
2. Some O*NET codes (especially new ones added in 30.x releases) may not yet have a direct 2018 SOC code and require a provisional crosswalk.
3. CPS OCC codes for the licensing supplement (2015+) use 2010 Census OCC, not 2018 — so if using both O*NET 30.2 and CPS licensing data, the crosswalk goes: O*NET SOC → 2018 Census OCC → via conversion rates → 2010 Census OCC.

---

## Key Findings

**O*NET variables for signal-reliance proxy:**
- Primary: `2.A.1.c` Writing Importance (Skills.xlsx, Scale ID = "IM"), `2.A.1.c` Writing Level (Scale ID = "LV"). Strong evidence from Deming (2017) as the methodological precedent for this exact style of index construction.
- Secondary: `2.A.1.a` Critical Thinking Importance, `4.A.2.a.4` Analyzing Data or Information Importance (Work Activities)
- Written correspondence channel: `4.C.1.a.2.j` Written Letters and Memos mean score, `4.C.1.a.2.h` Electronic Mail mean score (Work Context, Scale ID = "CX")
- For a richer measure: `1.A.1.a.4` Written Expression and `1.A.1.b.2` Originality from Abilities.xlsx, weighted by Felten et al.'s published language modeling relatedness scores
- Confidence: **strong evidence** — variable names, element IDs, file structure, and scale types all confirmed from O*NET Resource Center documentation.

**Database version**: O*NET 30.2 (current as of March 2026). Download all 40 files as one ZIP from onetcenter.org/database.html. CC BY 4.0 license.
Confidence: **strong evidence**.

**Licensing data — recommended source for MSc:**
- CPS Certifications and Licenses data (since January 2015 annual supplement, available via IPUMS CPS) provides individual-level government-license indicator. Aggregate to occupation using 2010 or 2018 Census OCC codes to get occupation-level prevalence (share of workers holding a government-required license).
- This covers all occupations (not just 48) and enables the licensing × AI-exposure interaction in H4.
- For intensity-graded licensing (hours required, fees): use KRRC OLLRP 2025 database or NCSL database, but coverage is limited to sub-baccalaureate trades and health professions.
- Confidence: **strong evidence** for CPS approach; **moderate evidence** for coverage adequacy of NCSL/KRRC for high-exposure occupations.

**Licensing × AI overlap:**
- The overlap is real but narrow. The cleanest cases are: CPAs (high AI exposure + CPA license), lawyers (high AI exposure + bar license), financial advisors (securities license), and teachers (teaching license).
- Most of the top-AI-exposure occupations (software developers, data scientists, writers) are NOT licensed.
- This means H4 likely has limited statistical power unless "licensing" is defined broadly to include partial state coverage (% of states requiring a license, from NCSL data).
- Confidence: **moderate evidence** — occupation list cross-matching is clear, but power calculations require actual cell sizes from ACS/CPS.

**SOC-OCC crosswalk:**
- Use Census Bureau's 2018-occupation-code-list-and-crosswalk.xlsx for O*NET SOC → 2018 Census OCC.
- For CPS pre-2019 (where licensing supplement data begins): use 2010 Census OCC → requires applying conversion rates from the 2010-to-2018 transition tables.
- Employment-weight O*NET aggregations using OEWS employment counts.
- Confidence: **strong evidence** — crosswalk files confirmed at Census Bureau.

---

## Assessment

### On O*NET signal-reliance construction

The MSc-feasible approach is two variables: `2.A.1.c` Writing Importance and `2.A.2.a` Critical Thinking Importance from O*NET Skills, standardized and averaged. This has direct precedent in Deming (2017) and is immediately defensible. For something more distinctive, add the Work Context written correspondence items (`4.C.1.a.2.j` and `4.C.1.a.2.h`) which capture whether the job's workflow actually centers on written output — the thing an LLM would corrupt. The peer-review-ready version uses the Felten et al. AIOE architecture (O*NET Abilities weighted by MTurk AI-relatedness scores) but focused on the subset of abilities most associated with verifiable text output.

The critical conceptual choice: signal-reliance is not the same as AI exposure. Eloundou's measure asks whether LLMs save time on tasks. Signal-reliance asks whether employers screen for exactly the tasks LLMs do well. These can diverge: a radiologist has high AI exposure but low signal reliance (licensing, board certification, and residency placements dominate entry); a marketing copywriter has high signal reliance but perhaps lower Eloundou exposure (because the LLM does the task faster, not necessarily more detectably). The Work Context written correspondence items capture signal reliance better than pure task exposure measures.

One potential issue: Job Zone is a confound. High-Job-Zone occupations (requiring advanced degrees) have strong writing demands but also have many non-text entry signals (degrees, recommendation letters, in-person interviews). The interaction Writing Importance × (1 − Job Zone / 4) may better isolate the occupations where writing IS the dominant screening mechanism and alternative signals are weak.

### On licensing data

The CPS supplementary module approach is clearly the right choice for an MSc thesis. It is (a) nationally representative, (b) linked to actual individual workers (not aggregated guesses), (c) available via IPUMS with minimal data wrangling, and (d) annually available from 2015 onward, so overlapping with ACS waves used in the main analysis. The occupation-level licensing prevalence constructed from CPS will be available for every Census OCC code — unlike the NCSL/KRRC databases which cover only 48–77 occupations.

The genuine problem is that the occupations with both high AI exposure and high licensing prevalence are few. This does not mean H4 is untestable — it means the hypothesis requires careful framing. Rather than "licensed vs. unlicensed occupations," H4 should contrast high-exposure occupations by their licensing rates, testing whether the handful of high-exposure/licensed occupations (accountants, lawyers, financial advisors, teachers) show different patterns than high-exposure/unlicensed ones. This is a legitimate heterogeneity test; it just requires being honest about the small number of double-exposed cells.

The strongest version of H4 would treat licensing as continuous (fraction of states requiring a license, from NCSL data) and test the interaction with AI exposure across the 48 covered occupations as a validation exercise alongside the broader CPS binary approach.

### On the crosswalk

The O*NET SOC → Census OCC crosswalk is manageable but introduces measurement error through aggregation. The most problematic aggregations are in white-collar professional occupations (e.g., all "computer and mathematical" occupations may compress into a few Census OCC codes). This is worth documenting as a limitation. Employment-weighting the O*NET scores using OEWS data is standard practice and reduces but does not eliminate this problem. Using IPUMS harmonized codes throughout is non-negotiable for time-series consistency.

---

## Concrete Data Pipeline Specification

### Step 1: O*NET Signal-Reliance Index

**Source**: O*NET 30.2 database, download from https://www.onetcenter.org/database.html

**Files needed**:
- `Skills.xlsx` — Writing (2.A.1.c), Critical Thinking (2.A.2.a), Reading Comprehension (2.A.1.a); Scale ID = "IM" for Importance
- `Work Context.xlsx` — Written Letters and Memos (4.C.1.a.2.j), Electronic Mail (4.C.1.a.2.h); Scale ID = "CX" for mean
- `Job Zones.xlsx` — Job Zone integer 1–4
- `Abilities.xlsx` — Written Expression (1.A.1.a.4), Originality (1.A.1.b.2); Scale ID = "IM"

**Minimal index** (thesis-defensible):
```
sig_reliance_min = mean(z_score(Writing_IM), z_score(CritThinking_IM))
```

**Full index** (peer-review-ready):
```
sig_reliance_full = mean(
  z_score(Writing_IM),
  z_score(CritThinking_IM),
  z_score(WrittenLetters_CX),
  z_score(Email_CX)
) × (1 − Job Zone / 5)
```

The Job Zone divisor adjusts downward for occupations where non-text entry barriers (advanced degrees, licensure) already dominate the screening mechanism, reducing the contamination risk.

**Unit of observation**: O*NET-SOC code (6-digit), ~923 occupations.

### Step 2: Licensing Variable

**Source 1 (binary, all occupations)**: CPS Certifications and Licenses Annual Supplement
- Access: IPUMS CPS (https://cps.ipums.org), select all years 2015–present, include certification/license variables
- Key variable: whether the worker's license was government-required (as opposed to voluntary certification)
- Aggregate to Census OCC code: `license_prev_occ = mean(government_license_indicator)` across all employed respondents in occupation × year cell
- Merge to ACS/CPS analysis sample on Census OCC code

**Source 2 (intensity, 48 occupations)**: NCSL National Occupational Licensing Database
- Access: https://licensing.csg.org/the-database/ — free download
- Variables: training_hours, experience_weeks, n_exams, initial_fee by state
- Aggregate to occupation level: national average of state requirements
- Limitation: covers only 48 occupations, excludes degree-required professions

**Recommended approach**: Use CPS licensing prevalence as the primary variable (covers full occupational distribution). Use NCSL as robustness/validation for the 48 covered occupations.

### Step 3: Crosswalk Chain

**O*NET SOC → 2018 Census OCC**:
- Download: https://www2.census.gov/programs-surveys/demo/guidance/industry-occupation/2018-occupation-code-list-and-crosswalk.xlsx
- This is a direct lookup: each 6-digit SOC maps to a 2018 Census OCC code

**2018 Census OCC → 2010 Census OCC** (for CPS data pre-2019):
- Download conversion rates: https://census.gov/data/tables/time-series/demo/industry-occupation/acs-tp78.html → Tables E1-E3
- For panel consistency, convert all OCC codes to a single base (recommend 2018 Census OCC throughout and restrict CPS licensing sample to 2019+, or use IPUMS harmonized OCC2010 codes)

**IPUMS recommendation**: IPUMS CPS provides the `OCC` variable harmonized to 2010 Census OCC codes for all years. Use `OCC` as the merge key if using pre-2019 data. For 2019+ use `OCC2010` (IPUMS crosswalked backward) for consistency.

**Employment-weighting for O*NET aggregation**:
- BLS OEWS (https://www.bls.gov/oes/) provides employment counts by 6-digit SOC
- For each Census OCC = aggregation of multiple SOC codes, compute weighted average of O*NET scores using OEWS employment as weights
- Update: use OEWS 2022 or 2023 employment weights (most recent available without COVID distortions)

### Step 4: Known Data Issues

1. **O*NET update lag**: Some occupations have data from different survey years. The "Date" column in each O*NET file indicates when that occupation's data was last updated. For rapidly-changing occupations (data scientists, AI specialists), the O*NET data may lag actual job requirements. Check the Date column for anomalies.

2. **CPS licensing supplement identification**: The CPS does not ask "what is your occupation's license?" — it asks whether the individual holds a government-required license. Some workers in licensed occupations don't have a license (e.g., unlicensed apprentices); some workers in unlicensed occupations report having one (e.g., a contractor with a state license). The resulting occupation-level prevalence is a behavioral share, not a legal indicator. For some analysis it's better to use a dichotomous "any state legally requires a license for this occupation" indicator, constructed from NCSL for coverage.

3. **Census OCC aggregation problem**: Several O*NET occupations map to the same Census OCC. "Software developers" (15-1252) and "software quality assurance analysts" (15-1253) both map to the 2018 Census OCC 1010. If these have different signal-reliance scores, the merged variable is an employment-weighted average that may not represent either cleanly.

4. **O*NET Job Zone revision in 30.2**: The 30.2 release changed Job Zones from a 5-level to a 4-level framework (325 occupations updated). If comparing to prior work using 5-level Job Zones, re-download the 30.1 or use the "legacy" values. The 4-level framework is the current standard.

5. **CPS licensing supplement coverage gap**: The supplement was not asked in every monthly CPS — it was an annual supplement through the January survey month in its early years. Check which months/years contain the licensing questions. IPUMS documentation is authoritative on this.

6. **Licensing is time-invariant as stated in proposal**: The proposal treats licensing as time-invariant. For most occupations this is defensible over a 5–10 year window. The main exceptions are occupations where licensing status changed (added or removed) during the study period — these should be flagged. The KRRC annual snapshots (2023–2025) enable a longitudinal check but their historical coverage is limited.

---

## Sources

- O*NET 30.2 Database Documentation: https://www.onetcenter.org/database.html
- O*NET 30.2 Skills Data Dictionary: https://www.onetcenter.org/dictionary/30.2/excel/skills.html
- O*NET 30.2 Work Context Data Dictionary: https://www.onetcenter.org/dictionary/30.2/excel/work_context.html
- O*NET 30.2 Job Zones Data Dictionary: https://www.onetcenter.org/dictionary/30.2/excel/job_zones.html
- O*NET Content Model Reference (element IDs): https://www.onetcenter.org/dl_files/database/db_30_2_text/Content%20Model%20Reference.txt
- Eloundou, Manning, Mishkin, Rock (2023). "GPTs are GPTs: An Early Look at the Labor Market Impact Potential of Large Language Models." arXiv:2303.10130. https://arxiv.org/abs/2303.10130
- Deming, D.J. (2017). "The Growing Importance of Social Skills in the Labor Market." QJE 132(4): 1593–1640. DOI:10.1093/QJE/QJX022
- Autor, Levy, Murnane (2003). "The Skill Content of Recent Technological Change." NBER WP 8337. http://papers.nber.org/papers/w8337.pdf
- Felten, Raj, Seamans (2018). "A Method to Link Advances in Artificial Intelligence to Occupational Abilities." AAAI. https://scholar.semanticscholar.org/paper/c0fad7473a74ce9d8075ab65161313e31d82fdde
- Brynjolfsson, Mitchell, Rock (2018). "What Can Machines Learn, and What Does It Mean for Occupations and the Economy?" AEA P&P. https://scholar.semanticscholar.org/paper/bf1a1f8f1c51500bb96055957c371825499841c3
- BLS CPS Certifications and Licenses (2015+): https://www.bls.gov/cps/certifications-and-licenses.htm
- IPUMS CPS: https://cps.ipums.org
- NCSL National Occupational Licensing Database (2017/2022): https://www.ncsl.org/labor-and-employment/the-national-occupational-licensing-database
- KRRC/Kleiner OLLRP Database (2025): https://knee.wvu.edu/data/ollrp-database
- KRRC Annual Licensing Database Snapshot 2025: https://knee.wvu.edu/publications/knee-center-research/2025/12/19/annual-licensing-database-snapshot-2025
- Kleiner, Xu (2020). "Occupational Licensing and Labor Market Fluidity." NBER/Minneapolis Fed SR 606. https://doi.org/10.21034/sr.606
- Census Industry and Occupation Code Lists and Crosswalks: https://www.census.gov/topics/employment/industry-occupation/guidance/code-lists.html
- Census 2010-to-2018 OCC Conversion Rates: https://census.gov/data/tables/time-series/demo/industry-occupation/acs-tp78.html
- Council of State Governments Licensing Database: https://licensing.csg.org/the-database/
