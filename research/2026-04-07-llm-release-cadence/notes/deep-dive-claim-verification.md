# Deep Dive: Primary Source Verification of Load-Bearing Claims

## Question
Six (plus one bonus) specific claims in the survey notes are sourced primarily to newsletter aggregators rather than primary sources. Can they be independently confirmed, corrected, or shown to be unverifiable?

---

## Summary Table

| Claim | Verdict | Primary Source |
|---|---|---|
| A1: Meta $115-135B 2026 capex | CONFIRMED | Meta Q4 2025 earnings press release (Jan 28, 2026) |
| A2: "Avocado" failed to reach frontier | CONFIRMED (with nuance) | NYT (Mar 12, 2026), Reuters (Mar 2026) |
| A3: Meta considering licensing Gemini | CONFIRMED | NYT, Reuters, CNBC (Mar 2026) |
| A4: Yann LeCun departed Meta ~Nov 2025 | CONFIRMED | CNBC (Nov 19, 2025), Bloomberg, TechCrunch (Nov 11, 2025) |
| A5: LeCun departure connected to Avocado | PARTIALLY CONFIRMED | Indirect: departure preceded Avocado news by 4 months; shared root cause (LLM strategy) |
| B1: 74 releases in 52 days | PARTIALLY CONFIRMED | Product Compass newsletter (crowdsourced, not official changelog) |
| B2: Only 13 model releases, rest tools | REFUTED (undercounting) | Actual model releases were ~3 in that window; ~71 were non-model updates |
| B3: "1.4 releases per day" avg | CONFIRMED (math accurate) | Derived from 74/52 |
| B4: Top three labs updating flags every few weeks | UNVERIFIABLE | No primary source found |
| C1: OpenAI raised $110B at $730B pre-money Feb 2026 | CONFIRMED | Bloomberg, TechCrunch, CNBC (Feb 27, 2026); OpenAI blog |
| C2: Anthropic raised $30B at $380B Feb 2026 | CONFIRMED | Bloomberg, TechCrunch, Anthropic.com (Feb 12, 2026) |
| C3: $35B Amazon tranche contingent on AGI/IPO | CONFIRMED | Axios, CNBC, Bloomberg (Feb-Mar 2026) |
| C4: Both labs target 2027 IPOs | PARTIALLY CONFIRMED | Anthropic eyes Oct 2026; OpenAI targets Q4 2026 or Q1 2027 — not uniformly 2027 |
| D: Dario "twelve-month delay would bankrupt me" | REFUTED (misquote) | Fortune (Feb 14, 2026) — real quote exists but differs significantly |
| E: RSP v3 bakes competitor release cadences into safety | PARTIALLY CONFIRMED (overstated) | RSP v3 PDF, Anthropic.com — competitor logic present but NOT cadence-specific |
| F: RL scaling "couldn't be sustained for 1-2 years" — researchers quoted | REFUTED (wrong framing) | Epoch AI (Josh You); no researcher said this; the projection is analyst inference |
| G: Densing Law — efficiency doubling every 3.5 months | CONFIRMED (minor correction) | Xiao et al., Nature Machine Intelligence (2025); paper says "approximately every 3.5 months" |

---

## Investigation

### Claim A: Meta "Avocado" and 2026 Capex

**The capex number ($115-135B) is solidly confirmed at the primary source level.** Meta's own investor relations press release from January 28, 2026, reporting Q4 2025 results, states: "We expect full-year 2026 capital expenditures to be in the range of $115-135 billion." The investor.atmeta.com page (which returns 403 to automated fetchers but is indexed) was reported verbatim by DCD, QZ, CNBC, and Sherwood News. This is primary-source territory.

**The Avocado story is confirmed by mainstream press — NYT first, then Reuters and CNBC.** The New York Times broke the story on March 12, 2026, reporting that Meta had delayed Avocado from March to May or later after internal tests showed it "underperforms" peers. The exact language from sourced reporting: the model "currently falls between Google's AI Gemini 2.5 and Gemini 3" — meaning it does not "fail to reach the frontier" outright but falls short of the *leading* frontier model (Gemini 3). The secondary source's framing ("failed to reach the frontier") is slightly stronger than what the NYT reported.

**The Gemini licensing discussion is also confirmed** by both NYT and Reuters. Leaders of Meta's AI division "discussed the possibility of temporarily licensing Gemini to power the company's AI products." No decisions were finalized as of March 2026.

**Yann LeCun's departure is confirmed** as a November 2025 event. TechCrunch first reported plans on November 11; LeCun confirmed departure on November 18-19, 2025, widely covered by CNBC, Bloomberg, Fortune, and Euronews. He launched Advanced Machine Intelligence (AMI) Labs, headquartered in Paris.

**The connection between LeCun's departure and Avocado is real but indirect.** The departure was announced four months before Avocado news broke. Both share a common root: Meta's 2025 reorganization under chief AI officer Alexandr Wang (Scale AI founder), which deprioritized fundamental research (LeCun's domain) and emphasized aggressive LLM scaling — the exact approach that produced Avocado's disappointing results. LeCun's stated reason for leaving ("LLMs cannot get to human-level AI") is structurally connected to the Avocado failure, but the departure is not reported as *caused by* Avocado specifically.

**Verdict: The secondary sources slightly overstate the connection between LeCun and Avocado specifically, and describe the Avocado failure in stronger terms than the primary reports warrant. But all the core facts are confirmed.**

Primary sources:
- Meta Q4 2025 earnings: https://investor.atmeta.com/investor-news/press-release-details/2026/Meta-Reports-Fourth-Quarter-and-Full-Year-2025-Results/default.aspx
- NYT Avocado delay (Mar 12, 2026): sourced via Reuters/Yahoo Finance https://finance.yahoo.com/news/meta-delays-rollout-ai-model-235602299.html
- CNBC LeCun departure: https://www.cnbc.com/2025/11/19/meta-chief-ai-scientist-yann-lecun-is-leaving-the-company-.html
- TechCrunch LeCun plans: https://techcrunch.com/2025/11/11/metas-chief-ai-scientist-yann-lecun-reportedly-plans-to-leave-to-build-his-own-startup/
- Bloomberg LeCun: https://www.bloomberg.com/news/articles/2025-11-19/meta-ai-s-lecun-to-announce-exit-startup-as-soon-as-this-week

---

### Claim B: Anthropic's Release Pace

**The "74 releases in 52 days" figure comes from a single newsletter, not from Anthropic's official changelog.** Paweł Huryn (Product Compass newsletter) compiled this independently by tracking the public X/Twitter feeds of eight individual Anthropic team members — Boris Cherny, Thariq (trq212), Noah Zweben, Felix Rieseberg, Lydia Hallie, Anthony Morris, Adam Feldman, and Dickson Tsai. This is a crowd-sourced count from social media, not a count against Anthropic's published release notes.

**The official Anthropic platform changelog (fetched directly from platform.claude.com/docs/en/release-notes/overview) shows a notably different picture.** For the same period (approximately February 3 – March 24, 2026), the official changelog lists approximately 8-10 distinct entries, covering:
- Model launches: Claude Opus 4.6 (Feb 5), Claude Sonnet 4.6 (Feb 17)
- API features: fast mode (Feb 7), structured outputs GA (Jan 29), automatic caching (Feb 19), model capability fields (Mar 18), extended thinking display (Mar 16), 1M context GA (Mar 13)
- Deprecations and retirements

The Claude Code repository has its own CHANGELOG.md on GitHub with more frequent entries, and there is a separate Claude Apps help center changelog not captured in the API changelog. The "74" figure aggregates all surfaces — Claude Code (28 releases), a desktop product called Cowork (15 releases), API/infrastructure (18 releases), and models/core platform (13 releases).

**The claim that only 13 were model releases while the rest were tools/products is itself an overcount of model releases.** In the February 3 – March 24, 2026 window, there were only three distinct model launches on the API: Opus 4.6, Sonnet 4.6, and Fast Opus 4.6 (a speed variant). The "13 models and core platform" category likely bundles model launches with model-related platform changes (deprecations, context window changes, etc.).

**The 1.4 releases per day math is correct** (74 divided by 52 = 1.42), but the denominator definition is important: this counts any announcement, tweet, or changelog entry from any surface as a "release," including internal tooling updates, documentation changes, and feature flags.

**Verdict: The 74/52 figure is sourced from a newsletter's social media trawl, not Anthropic's official changelog. It is not wrong per se — it counts things that were shipped — but the methodology inflates the apparent pace by aggregating releases across all surfaces and counting incremental updates as discrete releases. The survey should note the source is Product Compass (a newsletter), that the count method was social media tracking, and that only ~3 were major model releases.**

Primary sources:
- Anthropic official API changelog: https://platform.claude.com/docs/en/release-notes/overview
- Product Compass "74 releases" piece (newsletter, crowdsourced): https://www.productcompass.pm/p/claude-shipping-calendar

---

### Claim C: OpenAI and Anthropic 2026 Funding Rounds

**All funding figures are confirmed at primary source level.**

OpenAI's round was announced February 27, 2026:
- $110 billion initial close at $730B pre-money / $840B post-money valuation
- Investors: Amazon ($50B, with $35B contingent), Nvidia ($30B), SoftBank ($30B)
- The round later grew to $122B total at $852B post-money (as of March 31, 2026, per Bloomberg)
- OpenAI's own blog post: https://openai.com/index/scaling-ai-for-everyone/

Anthropic's round was announced February 12, 2026:
- $30B Series G at $380B post-money valuation
- Led by Coatue and GIC (Singapore sovereign wealth fund), with Microsoft, Nvidia, D.E. Shaw, Dragoneer, Founders Fund
- Anthropic's own press release: https://www.anthropic.com/news/anthropic-raises-30-billion-series-g-funding-380-billion-post-money-valuation

**The $35B contingent tranche is confirmed, but the trigger condition needs nuancing.** Multiple sources (Axios, CNBC, Bloomberg) confirm Amazon's $35B is contingent. Specific conditions: Amazon's $50B breaks down as $15B immediate plus $35B contingent on either (1) an OpenAI IPO, or (2) reaching an AGI milestone — by December 31, 2028 (not 2026 as the secondary source suggested). The survey notes said "by 2026" which is incorrect; it's December 2028 per the SEC filings analyzed by GeekWire.

**IPO targets are 2026, not uniformly 2027.** Anthropic is targeting October 2026 IPO (per The Information); OpenAI's CFO Sarah Friar has guided toward 2027 specifically (Q4 2026 or Q1 2027). The survey's claim that "both labs target 2027 IPOs" is partially wrong — Anthropic is targeting 2026.

**Verdict: Funding figures confirmed precisely. Two corrections needed: (1) the Amazon contingent tranche trigger deadline is December 2028, not "by 2026"; (2) Anthropic targets a 2026 IPO, not 2027.**

Primary sources:
- OpenAI blog: https://openai.com/index/scaling-ai-for-everyone/
- OpenAI completion announcement: https://openai.com/index/accelerating-the-next-phase-ai/
- Bloomberg (OpenAI Feb 27): https://www.bloomberg.com/news/articles/2026-02-27/openai-finalizes-110-billion-funding-at-730-billion-valuation
- Anthropic press release: https://www.anthropic.com/news/anthropic-raises-30-billion-series-g-funding-380-billion-post-money-valuation
- Bloomberg (Anthropic Feb 12): https://www.bloomberg.com/news/articles/2026-02-12/anthropic-finalizes-30-billion-funding-at-380-billion-value
- Axios (Amazon tranche detail): https://www.axios.com/2026/02/27/openai-funding-nvidia-amazon
- CNBC (Amazon contingent): https://www.cnbc.com/2026/02/27/open-ai-funding-round-amazon.html

---

### Claim D: Dario Amodei "Twelve-Month Delay Would Bankrupt Me"

**The exact phrase "twelve-month delay would bankrupt me" does not exist in the primary source.** A search for that precise phrasing returned no results. The Fortune article is real and does contain a bankruptcy quote, but it is materially different.

**The actual Fortune article** (February 14, 2026, headline: "Anthropic CEO Dario Amodei explains his spending caution, warning if AI growth forecasts are off by just a year, 'then you go bankrupt'") contains two relevant quotes:

1. "If I'm just off by a year in that rate of growth, or if the growth rate is 5x a year instead of 10x a year, then you go bankrupt."

2. "What if the country of geniuses comes, but it comes in mid-2028 instead of mid-2027? You go bankrupt."

3. "If my revenue is not $1 trillion, if it's even $800 billion, there's no force on Earth, there's no hedge on Earth that could stop me from going bankrupt if I buy that much compute."

**The misquote matters because the real quote is about revenue growth rate accuracy, not about competitive release timing.** Amodei is discussing the danger of building compute infrastructure based on aggressive revenue forecasts — if growth comes in at 5x/year instead of 10x/year, or if the "country of geniuses" (AGI-driven economic boom) arrives a year later than projected, then companies that bought $100B+ in compute are insolvent. This is a warning about capital allocation timing relative to AI capability arrival, not about falling behind competitors in the release race.

**The secondary source appears to have paraphrased and sharpened the quote** into "twelve-month delay would bankrupt me," which converts a conditional probability argument about revenue forecasting into a direct statement about competitive cadence. These are meaningfully different claims. The real quote supports the IPO pressure thesis but is more nuanced.

**Verdict: REFUTED as stated. The real quote exists and is powerful, but must be reproduced accurately. The real quote: "If I'm just off by a year in that rate of growth, or if the growth rate is 5x a year instead of 10x a year, then you go bankrupt." The context is revenue forecast accuracy, not competitive release delay.**

Primary source:
- Fortune, Feb 14, 2026: https://fortune.com/2026/02/14/anthropic-ceo-dario-amodei-spending-capex-risk-ai-revenue-forecasts-bankruptcy/

---

### Claim E: Anthropic RSP v3 Baking Competitor Release Cadences into Safety

**The claim as stated is an overstatement. The RSP v3 does incorporate competitive dynamics, but not release cadences specifically.**

**What RSP v3 actually says:** The document (effective February 24, 2026) shifts from purely unilateral safety commitments toward a framework that distinguishes between unilateral commitments (baseline protections Anthropic will maintain regardless) and conditional commitments (which depend on what competitors do). The key competitive language:

- "If one AI developer paused development to implement safety measures while others moved forward training and deploying AI systems without strong mitigations, that could result in a world that is less safe."
- Anthropic commits to matching or exceeding competitor safety *mitigations* if competitors implement "more effective mitigations" at comparable cost.
- The old policy committed to pausing development when capability thresholds were reached regardless of competitors; RSP v3 abandons the hard pause commitment.

**What RSP v3 does NOT say:** It does not mention competitor release cadences, release pace, or release timelines as inputs to safety calculations. The competitive logic is about *safety mitigation quality*, not about *how fast competitors are shipping*.

**The Atlantic article** attributed by the secondary source does not appear to exist as described. Searching for Ross Andersen and Charlie Warzel's recent Atlantic pieces about Anthropic turned up Warzel's general AI coverage and an Atlantic Council (different organization) piece, but no specific Atlantic magazine article that characterizes RSP v3 as "baking competitor release cadences into safety calculations."

**The correct characterization is important.** What Anthropic actually did was abandon its unilateral pause commitment, arguing that unilateral pauses disadvantage responsible developers while doing nothing to stop irresponsible ones. This is a collective action argument, not a cadence-matching argument. The difference: the survey's claim implies Anthropic is now tracking *how fast* others release; what actually happened is that Anthropic is no longer committing to *stop entirely* if a competitor crosses a threshold without equivalent safeguards.

**Verdict: PARTIALLY CONFIRMED but materially overstated. RSP v3 does incorporate competitive dynamics — it explicitly reasons about what happens when responsible developers unilaterally pause while others don't. But it does not "bake competitor release cadences" into safety calculations; it changes the conditions under which Anthropic would pause. The competitive logic is about safety mitigation quality, not release velocity. The Atlantic attribution could not be verified.**

Primary sources:
- Anthropic RSP v3 PDF (direct): https://www-cdn.anthropic.com/e670587677525f28df69b59e5fb4c22cc5461a17.pdf
- Anthropic RSP v3 blog announcement: https://www.anthropic.com/news/responsible-scaling-policy-v3
- GovAI analysis: https://www.governance.ai/analysis/anthropics-rsp-v3-0-how-it-works-whats-changed-and-some-reflections
- Zvi Mowshowitz detailed analysis: https://thezvi.wordpress.com/2026/04/01/anthropic-responsible-scaling-policy-v3-a-matter-of-trust/

---

### Claim F: RL Scaling Ceiling — "Researchers Quoted Saying 1-2 Years" (Early 2025)

**This claim cannot be verified as stated. No OpenAI or Anthropic researcher is on record saying RL scaling "cannot be sustained for more than 1-2 years."**

**What the primary source (Epoch AI, Josh You, "How far can reasoning models scale?") actually says:**
- The analysis is by Epoch AI analyst Josh You, not an OpenAI or Anthropic researcher.
- The actual projection: "if reasoning training continues to scale at 10x every few months, in line with the jump from o1 to o3, it will reach the frontier of total training compute before long, perhaps within a year. At that point, the scaling rate will slow and converge."
- This is an *analyst inference* about when RL compute will converge with pretraining compute, not a statement that RL scaling "cannot be sustained."
- Dario Amodei is quoted in the piece saying Anthropic is "still very early on the scaling curve" — the *opposite* of a ceiling warning.
- OpenAI researchers are described as "projecting confidence that they can rapidly scale up reasoning models."

**The Ilya Sutskever NeurIPS 2024 "pretraining as we know it will end" quote** is frequently cited in this context, but refers specifically to pretraining data saturation, not RL scaling. Sam Altman explicitly rejected scaling ceilings, saying "there is no wall."

**What did exist in early 2025:** Discussion of data availability constraints for RL (you need problems with verifiable answers to do RLVR), potential ceiling from the domain specificity of verifiable rewards (math/code work well; other domains are harder), and economic constraints on scaling inference compute. But these are concerns and research challenges, not researcher statements that RL "cannot be sustained for 1-2 years."

**The secondary source appears to have attributed to researchers a conclusion that was only an analyst's projection, and flipped the framing from optimism ("early in the scaling curve") to pessimism ("cannot be sustained").**

**Verdict: REFUTED as stated. No researcher made this claim in the form described. The Epoch AI analysis projects RL compute will converge with frontier pretraining compute within roughly a year, after which it will slow from 10x/few-months to 4x/year — but this is an analyst projection and an acknowledgment that the *rate of gain* will slow, not that scaling "cannot be sustained." The survey must not attribute this to "OpenAI and Anthropic researchers."**

Primary sources:
- Epoch AI, Josh You, "How far can reasoning models scale?": https://epoch.ai/gradient-updates/how-far-can-reasoning-models-scale/
- Epoch AI Substack version: https://epochai.substack.com/p/how-far-can-reasoning-models-scale
- NeurIPS 2024 Sutskever context: https://bytepawn.com/ai-ilya-dwarkesh-satya-altman-2025.html

---

### Claim G (Bonus): Densing Law of LLMs

**Confirmed, with a minor correction on the number.**

**The paper is real and published in Nature Machine Intelligence.** Full citation:

Xiao, C., Cai, J., Zhao, W., Zeng, G., Lin, B., Zhou, J., Zheng, Z., Han, X., Liu, Z., & Sun, M. (2025). "Densing law of LLMs." *Nature Machine Intelligence*, 7(11). DOI: https://www.nature.com/articles/s42256-025-01137-0

- Authors: Researchers from Tsinghua University and ModelBest Inc.
- Published: 2025 (appears in Vol. 7, Issue 11 of Nature Machine Intelligence)
- ArXiv preprint: 2412.04315 (submitted December 2024)
- Citation count: 28 as of early 2026

**What the paper actually measures and claims:** The paper introduces "capability density" as a new metric, defined as the ratio of effective parameter size to actual parameter size (where effective parameter size is the minimum parameters a reference model needs to match a given model's performance). It then observes empirically that capability density of open-source LLMs has grown exponentially.

**The doubling period:** The Semantic Scholar abstract states "doubles approximately every 3.5 months." The ArXiv HTML text states "the capacity density of LLMs doubles approximately every three months" (95 days per the mathematical model A≈0.007). There is a slight discrepancy between the abstract (3.5 months) and the mathematical derivation (~3 months / 95 days) — possibly reflecting rounding or different benchmark sets. The claim in the survey ("every 3.5 months") matches the paper's stated headline finding.

**Important caveat the paper itself acknowledges:** The growth rate "is affected by specific evaluation benchmarks and reference models." The paper measures open-source models only; proprietary models are not included in the analysis. The trend is backward-looking (observed over ~2 years of open-source LLM history) and extrapolation is speculative.

**Verdict: CONFIRMED. Paper is real, published in the right journal, by Tsinghua/ModelBest researchers. The "3.5 months" figure matches the paper's headline claim (though the math suggests closer to 3 months in their model). The survey can cite this, but should note it applies to open-source models and is a backward-looking empirical observation.**

Primary sources:
- Nature Machine Intelligence: https://www.nature.com/articles/s42256-025-01137-0
- ArXiv preprint: https://arxiv.org/html/2412.04315v1
- Semantic Scholar entry (paper ID: 593eb9e34076a78ee1914bd8253b8b02de50e0eb)

---

## Key Findings

- **Claim A (Meta/Avocado/capex):** All core facts confirmed via mainstream press (NYT, Reuters, CNBC) and Meta IR. The LeCun-Avocado connection is indirect (shared root cause, not direct causation). "Failed to reach the frontier" is slightly stronger than what primary reports say. (Strong evidence)

- **Claim B (74 releases in 52 days):** Sourced to a newsletter's social media tracking, not Anthropic's official changelog. Factually close but methodologically opaque. Critically, only ~3 were model releases, not 13 — the survey's "only 13 model releases" claim overcounts model releases by a factor of 4. (Moderate evidence for the headline figure; methodology is newsletter-grade)

- **Claim C (funding rounds):** Confirmed at primary source level (Bloomberg, TechCrunch, company press releases). Two corrections: contingent tranche deadline is December 2028 not 2026; Anthropic targets 2026 IPO not 2027. (Strong evidence)

- **Claim D (Dario "twelve-month delay" quote):** The specific phrase does not exist. The real quote differs materially in meaning — it's about revenue growth rate forecasting risk, not competitive release delay. Can be used only with accurate quotation. (Strong evidence of misquote)

- **Claim E (RSP v3 bakes in competitor cadences):** Overstated. RSP v3 does incorporate competitive dynamics (abandons unilateral pause commitment), but does not reference release cadences. The logic is about safety mitigation quality, not release pace. Atlantic article attribution unverifiable. (Moderate evidence; the correct characterization is directionally similar but substantively different)

- **Claim F (researchers saying RL scaling 1-2 years):** Unverifiable as stated; the primary source (Epoch AI) is an analyst projection, not a researcher quote, and it projects a *slowdown* not a *ceiling*, while the researchers quoted are actually optimistic. (Strong evidence the claim is wrong as stated)

- **Claim G (Densing Law, 3.5 months):** Confirmed. Real paper, Nature Machine Intelligence, 2025. Minor note: the math in the paper suggests ~3 months; 3.5 months is the headline claim. (Strong evidence)

---

## Assessment

The survey notes have a solid empirical foundation on the major financial facts (funding rounds, capex guidance) and Meta/Avocado developments — these are confirmed at mainstream press and company-IR level. The failure modes fall into three patterns:

**Pattern 1 — Sharpened misquotes:** Claim D (Dario bankruptcy quote) is the clearest example. The original is striking enough to use accurately; the paraphrased version is demonstrably wrong. The report should quote Amodei directly from Fortune with the actual language.

**Pattern 2 — Correct facts, wrong source tier:** Claim B (74 releases) is factually not wildly off, but it's sourced from a newsletter's social media trawl rather than Anthropic's official changelog. This is appropriate for a newsletter but not for a serious report without disclosure. The additional claim that "only 13 were model releases" overcounts by 4x — the actual number of model launches in that period was approximately 3.

**Pattern 3 — Correct direction, overstated claim:** Claims E and F both have a real phenomenon underneath but overstate it. RSP v3 really does incorporate competitive dynamics — just not release cadences specifically. RL scaling really does face eventual convergence constraints — but researchers are not quoted saying this, and the framing in the survey inverts the actual sentiment (which was optimistic about near-term RL scaling).

**For the final report:** Claims A, C (with corrections), G can be used as stated with their primary sources. Claim B can be used with the caveat that it is a newsletter's social-media-sourced count. Claim D must be corrected to the actual quote. Claim E should be recharacterized as "RSP v3 abandons the unilateral pause commitment, reasoning that unilateral restraint disadvantages responsible developers without preventing irresponsible ones from proceeding" — which is accurate and arguably a stronger point. Claim F should be reframed as an analyst projection (Epoch AI), not researcher quotes, and the direction should be corrected: the projection is that RL scaling will *slow* as it converges with pretraining compute, not that researchers believe it *cannot be sustained*.
