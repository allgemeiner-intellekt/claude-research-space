# Deep Dive: Verification of "Claude Mythos Preview" Claims

## Question

Does the Q1 survey note's specific factual claims about Claude Mythos Preview hold up to primary-source scrutiny? Specifically: (1) Does the model exist? (2) Is "Project Glasswing" real? (3) Are the numbers — 72% Firefox exploit rate, $100M in pre-release security testing, 50 organizations — attributable to primary sources? (4) Is the GPT-2 comparison ("first general-release delay since GPT-2 in 2019") accurate? (5) Is the claimed link to OpenAI's open-weight pivot real?

---

## Investigation

### Step 1: Does Claude Mythos Preview exist, and does Project Glasswing exist?

**Yes, both are real.** Anthropic publicly announced Project Glasswing and Claude Mythos Preview on April 7, 2026. Primary sources confirmed:

- **anthropic.com/project/glasswing** — Anthropic's official project page, live as of the date of this investigation (April 10–11, 2026). Explicitly states: "We do not plan to make Claude Mythos Preview generally available, but our eventual goal is to enable our users to safely deploy Mythos-class models at scale."
- **anthropic.com/glasswing** — A companion announcement page, dated April 11, 2026.
- **red.anthropic.com/2026/mythos-preview/** — Anthropic Frontier Red Team technical writeup, published April 7, 2026, authored by Nicholas Carlini, Newton Cheng, and ~25 co-authors.
- **anthropic.com/claude-mythos-preview-system-card** — A 244-page system card PDF (confirmed by multiple secondary sources; direct PDF fetch exceeded size limit but URL resolves to a CDN-hosted PDF on www-cdn.anthropic.com).
- **anthropic.com/claude-mythos-preview-risk-report** — An "Alignment Risk Update: Claude Mythos Preview" PDF dated April 7, 2026, updated April 10, 2026 (I viewed the cover page and first five pages directly via the Read tool from the downloaded PDF at the path above).

The model's existence was first leaked via a CMS misconfiguration in late March 2026, and the Claude Code npm packaging error on March 31 also exposed some details. Anthropic confirmed both leaks were human error, not security breaches. The model's internal codename is "Capybara."

The launch partners are: Amazon Web Services, Apple, Broadcom, Cisco, CrowdStrike, Google, JPMorganChase, the Linux Foundation, Microsoft, NVIDIA, and Palo Alto Networks — 11 named organizations, not 12 (Anthropic itself is sometimes listed as the 12th). Additionally, "over 40 additional organizations that build or maintain critical software infrastructure" were given access. This is confirmed verbatim in both the official project page and the VentureBeat and Verge reporting.

**Assessment: The existence of the model and project is strongly confirmed by multiple primary Anthropic sources and major journalism outlets (The Verge, VentureBeat, TechCrunch, CNN, Fortune, ZDNet).**

---

### Step 2: Is the "72% Firefox exploit rate" claim accurate?

**No. This specific figure does not appear in any primary source.**

The actual numbers from Anthropic's red team blog post (red.anthropic.com/2026/mythos-preview/) and corroborated by Help Net Security's technical summary are:

- Claude Opus 4.6 produced working shell exploits against Firefox 147 JavaScript engine vulnerabilities on **2 occasions out of several hundred attempts** (near-zero percent).
- Claude Mythos Preview succeeded **181 times**, with an additional **29 runs achieving register control**, in the same test.

The "72%" figure appears nowhere in the Anthropic red team blog, the anthropic.com/project/glasswing page, the anthropic.com/glasswing announcement, the Verge article, the VentureBeat deep-dive, the Help Net Security technical writeup, or any primary Anthropic document I could access. The only place "72% Exploit Success?!" appears in search results is the title of a YouTube video (published April 11, 2026), suggesting the figure was derived or calculated by a third-party content creator — possibly by taking 181/(181+29+~47 failures) or some similar arithmetic from the raw numbers — and then circulated as if it were Anthropic's own stated metric.

**The actual exploit success story is real and significant, but the "72%" framing is not Anthropic's language and does not appear in primary sources.** If the survey note used "72% exploit rate against Firefox" as a specific primary-sourced claim, that framing is inaccurate.

---

### Step 3: Is "$100M in pre-release security testing" accurate?

**No. This is a significant mischaracterization of what the $100M represents.**

All primary sources are consistent: the $100 million is a commitment to **model usage credits** for Project Glasswing participants during the research preview period. The official project page states: "Anthropic is committing up to $100M in usage credits for Mythos Preview across these efforts." This is subsidized API access for defensive security partners — it is not a security testing budget, not a red-teaming expenditure, and not pre-release evaluation spending.

The actual pre-release testing costs mentioned in primary sources are much smaller. The red team blog describes the OpenBSD vulnerability discovery as costing "under $20,000 in scaffold runs." Separate reporting on the earlier Opus 4.6/Firefox collaboration mentions "approximately $4,000 in API credits" spent on exploit development.

In addition, Anthropic is donating $4M to open-source security organizations ($2.5M to Alpha-Omega/OpenSSF via the Linux Foundation, $1.5M to the Apache Software Foundation). This $4M in donations is the only cash figure; the $100M is a usage credit commitment.

**The claim that Anthropic spent $100M on pre-release security testing is false. The $100M is deferred usage credits for partners going forward, not a testing budget.**

---

### Step 4: Is "50 organizations" accurate?

**Approximately, but slightly inflated from what primary sources say.**

Primary sources consistently say: 11–12 named launch partners + "over 40 additional organizations" = roughly 50+ total. The anthropic.com/project/glasswing page says "over 40 additional organizations." VentureBeat's deep-dive says "more than 40 additional organizations." The Verge says "about 40 other organizations."

Saying "50 organizations" is a reasonable round-number summary of "12 named partners plus over 40 others," but it is not a figure that appears explicitly in any primary source. A more precise rendering would be "over 50 organizations" or "12 named partners plus 40+ others."

**Assessment: The "50 organizations" figure is a fair approximation, slightly understating the likely true total, but the specific number is not Anthropic's stated figure.**

---

### Step 5: Is the GPT-2 comparison ("first general-release delay since GPT-2 in 2019") accurate?

**This framing comes from secondary journalism, not Anthropic itself, and requires qualification.**

The specific GPT-2 comparison is made explicitly in The Decoder (April 8, 2026, by Maximilian Schreiner): "From GPT-2 to Claude Mythos: The return of AI models deemed 'too dangerous to release.'" That article traces the history carefully: OpenAI withheld the full GPT-2 (1.5B parameter model) in February 2019, did a staged release, and released the full model in November 2019. The industry then moved to "secure and release" rather than "withhold," and no major general-purpose model has been withheld since — until Mythos Preview.

This framing is historically defensible as secondary analysis, but it is not Anthropic's own claim. Anthropic does not invoke GPT-2 in its primary documentation. The claim that this is "the first general-release delay since GPT-2 in 2019" is a journalist's analytical frame, not a stated fact from Anthropic. There may also be counterexamples (e.g., various capabilities-limited or internal-only models across labs) depending on definition.

**Assessment: The GPT-2 comparison is real secondary analysis published by a credible tech outlet, but it is not primary-sourced from Anthropic, and it overstates certainty by framing what is a journalistic analogy as a firm historical fact.**

---

### Step 6: Is the link to OpenAI's open-weight pivot accurate?

**Plausible contextual framing, but not asserted in Anthropic's primary sources.**

The survey note frames the Mythos withholding as occurring "precisely as OpenAI was reversing course toward open weights with gpt-oss." OpenAI has indeed been publicly signaling a return to open-weight releases (GPT-4o mini open weights, and reported plans for a gpt-oss model). This is real context. However, Anthropic's own statements about Mythos Preview make no reference to OpenAI's open-weight decisions. The juxtaposition is an editorial choice by whoever wrote the survey note, not a claim made or implied by Anthropic.

**Assessment: The contextual juxtaposition is editorially reasonable but presents as causal what is purely temporal coincidence, and it is not sourced from any primary document.**

---

## Key Findings

- **Claude Mythos Preview exists and is withheld from public release.** Confirmed by multiple Anthropic primary sources (anthropic.com, red.anthropic.com, two Anthropic PDFs). Confidence: strong.

- **Project Glasswing is real.** Confirmed by official Anthropic project page and major press coverage. Confidence: strong.

- **The "72% Firefox exploit rate" figure does not appear in any primary source.** The real numbers are 181 successful exploits out of what appears to be several hundred attempts (Anthropic does not state a denominator or percentage in any reviewed primary source). The 72% figure appears to be a third-party calculation, likely from a YouTube content creator's video. Confidence: strong that the figure is not primary-sourced.

- **The $100M figure is real but mischaracterized.** It refers to model usage credits committed to Glasswing partners, not pre-release security testing expenditure. Confidence: strong.

- **The "50 organizations" figure is approximately correct** as a summary of "12 named partners + over 40 additional organizations," but the exact number is not primary-sourced. Confidence: moderate.

- **The GPT-2 comparison is credible secondary journalism**, made in The Decoder (April 8, 2026), not asserted by Anthropic itself. It is historically reasonable but not definitively proven as a "first" since edge cases exist. Confidence: moderate for the analogy, low for the "first since GPT-2" definiteness.

- **The "Alignment Risk Update: Claude Mythos Preview" PDF** (Anthropic, April 7, 2026, updated April 10) is a real primary document — I viewed its cover page and table of contents directly. It is an internal-style RSP implementation document covering alignment risks, monitoring, and safety pathways. It does not contain the "72%" figure, the GPT-2 comparison, or a "$100M security testing" claim.

---

## Assessment

The core claim — that Anthropic has withheld Claude Mythos Preview from public release due to its cybersecurity capabilities, and structured Project Glasswing as a restricted defensive-only access program with major tech partners — is **real and well-sourced**. This is a genuine empirical data point for the research project. The model is real, the withholding is real, the rationale is real.

However, **three of the five specific sub-claims contain significant errors**:

1. **"72% exploit rate against Firefox"** — fabricated or third-party-calculated; not in any Anthropic primary source. The actual metric (181 successful exploits vs. 2 for Opus 4.6) is remarkable on its own and does not need embellishment.

2. **"$100M in pre-release security testing"** — wrong category. The $100M is usage credits for partners going forward, not a testing expenditure. Pre-release testing costs were in the low tens of thousands of dollars per disclosed vulnerability.

3. **"First general-release delay since GPT-2"** — secondary journalistic analysis, not Anthropic's claim, and stated as established fact when it is an interpretive frame.

The "50 organizations" and OpenAI open-weight juxtaposition are defensible approximations/framings that don't rise to the level of errors but should not be treated as precisely primary-sourced.

**The research report can stand on this event, but it must use the actual numbers (181 exploits vs. 2; $100M in usage credits; 12 named partners + 40+ additional orgs) and should not attribute the GPT-2 framing to Anthropic. The 72% figure should be dropped entirely — it has no traceable primary source.**

---

## Primary Sources Consulted

1. anthropic.com/project/glasswing — Official Anthropic project page, April 7–8, 2026
2. anthropic.com/glasswing — Anthropic announcement page, April 11, 2026
3. red.anthropic.com/2026/mythos-preview/ — Frontier Red Team technical writeup, April 7, 2026 (Nicholas Carlini, Newton Cheng et al.)
4. anthropic.com/claude-mythos-preview-risk-report → www-cdn.anthropic.com PDF — "Alignment Risk Update: Claude Mythos Preview," April 7, 2026, updated April 10, 2026 (viewed pages 1–5 directly)
5. anthropic.com/news/mozilla-firefox-security — Mozilla/Firefox partnership announcement (pre-Glasswing, circa early March 2026)
6. The Verge, Hayden Field, April 7, 2026 — "A new Anthropic model found security problems 'in every major operating system and web browser'"
7. VentureBeat, April 7, 2026 — "Anthropic says its most powerful AI cyber model is too dangerous to release publicly — so it built Project Glasswing"
8. Help Net Security, Anamarija Pogorelec, April 8, 2026 — technical summary of red team findings
9. The Decoder, Maximilian Schreiner, April 8, 2026 — "From GPT-2 to Claude Mythos: The return of AI models deemed 'too dangerous to release'" (source of the GPT-2 framing)
