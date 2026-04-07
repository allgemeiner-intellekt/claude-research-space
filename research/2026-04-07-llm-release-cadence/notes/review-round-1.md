# Review — Round 1

## Overall Assessment

The four surveys together cover a lot of ground, and individually each is
competent. The anatomy note is the strongest — it has a concrete timeline,
named primary sources (Epoch, METR, Artificial Analysis, OpenAI blog,
DeepSeek arXiv), and a genuinely sharp observation in Pattern 5 (that what
looks like "one cadence" is actually four overlapping cycles: base-generation,
reasoning-iteration, post-training, feature). That decomposition alone is
worth the entire survey.

But as a basis for an insightful essay, the corpus has three serious problems:

1. **Too many load-bearing claims rest on non-primary newsletters and
   aggregator blogs.** The Synthesis ("The Plateau"), Marc Bara, Chyshkala,
   The Quiver, Multivac, Swarmsignal, Claudelab, TokenRing, Empirics.org,
   WhatLLM, Brenndoerfer — these appear repeatedly as sources for the most
   consequential quantitative claims (Meta Avocado failure, $6M DeepSeek,
   "74 releases in 52 days", "267 models in Q1 2026", the "70-75%
   institutional" estimate, the "9 models in 90 days"). Several of these
   are borderline SEO/LLM-generated content farms. The reviewer needs to
   verify the numbers before the orchestrator commits to them in the report.

2. **The notes never actually connect to each other.** METR's task-horizon
   doubling (still exponential) and Epoch's ECI capability acceleration
   (still exponential, 8→15 ECI/yr around April 2024) live in the anatomy
   note as "surprises". The analogies note puts us "closer to 2004 than
   2016" in the Moore's Law timeline because of those same METR numbers.
   The constraints note says pretraining is softening but inference-time is
   hot. The institutional note says 70-75% of cadence is institutional.
   **These are not obviously consistent with each other.** If capability
   is genuinely still doubling on the most rigorous long-task metric, then
   the "it's all institutional momentum" claim is wildly overstated. If
   institutional momentum is 70-75%, then the METR curve either measures
   something weird, or it's picking up the reasoning-RL phase only and
   will saturate soon. No one has resolved this — it's the single most
   important tension in the whole corpus.

3. **The "what comes next" question is weak.** The user explicitly asked
   about inflection points and replacement patterns borrowed from other
   industries. The analogies note gives us Moore's-Law-circa-2004 as the
   best fit, but there's almost nothing concrete on *what the actual
   post-cadence paradigm looks like* — test-time compute economics, world
   models, RL environments as a first-class capital asset, neuromorphic /
   analog hardware, agent-as-product economics, the "model dissolves into
   product" thread that the institutional note flagged as Surprise. That
   thread alone is probably the most interesting single answer to the
   user's question and it's two paragraphs long.

Verdict: **CONTINUE**. Three to five deep dives are needed before the
orchestrator has enough to write an insightful essay instead of a patchwork.

---

## Per-Survey Quality Assessment

### Survey: Anatomy of Releases

**Strengths**:
- Excellent primary-source density for the core timeline (Epoch AI, METR,
  OpenAI learning-to-reason blog, DeepSeek V3 arXiv, Meta Llama 4 blog,
  Artificial Analysis).
- The "four overlapping cycles" decomposition (base/reasoning/post-training/
  feature) is a real analytical move, not a list of facts. The orchestrator
  can build a whole section around this.
- Epoch ECI breakpoint at April 2024 (8→15 ECI/yr, R²=0.97) and METR's
  independent ~40% acceleration in October 2024 are the closest thing the
  corpus has to a quantitatively grounded "hidden inflection" story.
- The GPT-5 Epoch quote ("better explained by more frequent cadence than
  slower progress") is a valuable counter-narrative.

**Weaknesses**:
- The timeline past roughly November 2025 becomes thinner on primary
  sources. Claude Opus 4.5, 4.6, Gemini 3, GPT-5.4, Qwen 3.5, Kimi K2
  Thinking, Moonshot, Zhipu — most of these are sourced from LayerLens
  Q1 2026 and TimesOfAI, which are aggregators. The orchestrator should
  not cite 2026 benchmark numbers without a primary source.
- Gap 1 (what actually changes in a point release) is acknowledged but
  unresolved. This matters a lot for the central claim that "cycles 2-4
  wear the aesthetic of cycle 1".
- No view from inside the labs. No practitioner quotes from Sutskever,
  Karpathy, Dario, Demis, anyone at a French or Chinese lab on what they
  think is actually happening in 2025-2026. The closest we get is
  Nathan Lambert (once) and Dario's "we are still very early on the
  scaling curve" (Jan 2025 — already a year old).
- The "Reasoning compute near its own ceiling" sub-bullet cites the Epoch
  gradient update (May 2025) saying reasoning RL scaling "couldn't be
  sustained for more than 1-2 years" — but the source attribution is
  fuzzy ("both OpenAI and Anthropic researchers were quoted"). Who, when,
  where? This is load-bearing and needs primary sourcing.

### Survey: Scaling Constraints

**Strengths**:
- Genuinely rigorous on compute and power (Epoch AI, EPRI, IEA).
- The HBM supply crisis angle is a concrete, under-discussed bottleneck.
- Data exhaustion numbers from the Villalobos et al. paper are the
  cleanest in the corpus and the ordering of which constraint binds first
  is the kind of argumentative move the essay needs.
- The DeepSeek-R1 shock is correctly framed as restructuring the whole
  discourse.

**Weaknesses**:
- "The Plateau" (The Synthesis newsletter) is the sole source for the
  Meta Avocado story. This story is load-bearing for the central claim
  that "$135B/year doesn't buy frontier quality" and needs independent
  verification. If it turns out to be newsletter speculation, the whole
  "capital returns flat" thesis collapses.
- The DeepSeek-R1 $6M cost gets quoted but the interpretation is muddled.
  It's acknowledged as "not directly comparable" to Western costs (because
  it excludes R&D, failed runs, post-training) — but the number then
  functions rhetorically as if it were. What does the "real" DeepSeek-V3
  or R1 total-spend number look like?
- The inference-time compute scaling laws ("no clean equivalent to
  Chinchilla exists yet for this regime") is acknowledged as a gap but
  it's actually central to the whole question. If there *is* an emerging
  scaling law for reasoning compute / RL environments, the cadence story
  changes completely.
- Ilya Sutskever's "age of scaling is over" is quoted from secondhand
  paraphrase (Reuters via Business Insider). The Reuters piece was Nov
  2024 — more than a year before this survey. What has he said *since*
  about reasoning models / test-time compute? And Karpathy, Demis, Dario
  — where are they in 2025-2026?
- "Four hyperscalers combined = $650B in a single year" from The Synthesis
  cannot be sourced further and is a huge number. Needs verification.

### Survey: Historical Analogies

**Strengths**:
- The Scannell Eroom's Law paper is read in full and mapped carefully.
  The "better than the Beatles" → GPT-4 as free baseline move is a real
  contribution.
- Intel tick-tock retirement (2016) as structural parallel is the
  cleanest historical analogue and the survey sticks with it.
- Balances the "it might be 2004" vs "it might be 2016" read honestly.
- Brings in broadband saturation (HighSpeedInternet.com, 58% drop in
  2024) as a concrete demand-saturation data point.

**Weaknesses**:
- **This survey never does the cost-per-capability trajectory analysis**
  that would test whether Eroom's Law is actually operating in LLMs. It
  observes that the "throw money at it" tendency is present, and cites
  Meta's $135B, but does not compute anything like "cost per ECI point"
  or "cost per METR-task-hour" over time. This is the single biggest
  missed opportunity in the whole corpus and it's exactly what the user
  flagged as the potentially most interesting angle.
- "Densing Law" (Nature MI, 2025): 3.5-month efficiency doubling is cited
  twice with high confidence. Is this paper actually published in Nature
  Machine Intelligence? DOI? Authors? I can't verify this from the note
  alone and it's load-bearing for the "efficiency is still exponential"
  counter-narrative.
- METR numbers appear twice with slightly different framing: the anatomy
  note says "doubling every ~7 months for 6 years"; this note says
  "doubling every 7 months 2019-2025, accelerating to every 4 months in
  2024-2025" — sourced to "AI Digest March 2026" rather than METR's own
  paper. The March 2025 METR paper (primary source) and the 2026 AI
  Digest update need to be separated — is the acceleration real or is the
  AI Digest piece an extrapolation?
- Carlota Perez installation→deployment framework is flagged as
  underexplored. That's fair. It's actually the framework that would
  best fit a "the cadence ends because infrastructure phase ends" argument.
- The "who was aware in real time?" gap for Dennard collapse is the exact
  thing that would tell us whether today's lab researchers are in the 2004
  state (privately aware, publicly optimistic) or not. Worth a targeted
  deep dive.

### Survey: Institutional Momentum

**Strengths**:
- The RAND prisoner's dilemma paper (Abraham, Kavner, Moon 2026) is a
  genuine primary source and is correctly framed.
- The Anthropic RSP v3 "realism, not retreat" observation is sharp and
  important — possibly the single most revealing fact in the whole corpus.
- The IPO math / Amodei "twelve-month delay would make him bankrupt"
  quote is the strongest argument for institutional lock-in.
- The 74-releases-in-52-days of which only 13 were models angle is
  genuinely eye-opening (if true).

**Weaknesses**:
- The 70-75% institutional / 25-30% technical split is stated with
  confidence but is not derived from anything. It's vibes. The orchestrator
  should not use this number in the report as written — it needs either
  derivation from observables or to be labeled as speculation.
- Many of the most striking claims are sourced to blogs that look
  LLM-generated or heavily AI-assisted (Claudelab, Multivac, Swarmsignal,
  The Quiver, Chyshkala, Marc Bara's Medium). These need spot-checking
  against primary sources or neutral journalism. If Anthropic really
  shipped 74 releases in 52 days, this is on their changelog and can be
  verified. If OpenAI's "$35B contingent on AGI or IPO by 2026" is real,
  it's in the Amazon SEC filings.
- The Anthropic RSP v3 story is sourced to FindArticles (content
  aggregator) summarizing The Atlantic. Given how load-bearing this is,
  we need either Anthropic's actual RSP v3 document or a direct link to
  the Atlantic piece.
- The Dario "twelve-month delay would make him bankrupt" quote is
  attributed to "Fortune... days after banking the round" via a Substack
  analysis (Perera). Needs direct sourcing. If this quote isn't real or
  is mis-paraphrased, a huge chunk of the IPO-pressure argument
  evaporates.
- Gary Marcus appears multiple times as the skeptic voice but no one
  balances him with an equivalently credentialed optimist from 2025-2026.
  The balance is thin.
- Surprise 3 says "Anthropic was shipping 1.4 releases per day" and "top
  three labs are updating flagship models every few weeks." These are
  extraordinary claims that need primary verification (changelogs).
- The "Chinese labs have similar cadence without IPO pressure" gap
  identified at the end is exactly right — this is the natural control
  group for the institutional hypothesis and no one has investigated it.

---

## Cross-Cutting Tensions (Unresolved)

These are the contradictions the orchestrator cannot write around:

### T1. Is capability still on an exponential, or flattening?
- **Exponential camp**: METR task horizons doubling 7 months (anatomy,
  analogies); Epoch ECI acceleration April 2024 from 8 to 15 ECI/yr,
  R²=0.97 (anatomy, constraints); Densing Law 3.5-month efficiency
  doubling (analogies).
- **Flattening camp**: Benchmark saturation documented (anatomy);
  GPT-4.5 failure (anatomy); top-5 gap on MATH-500 = 0.4pp vs 1.3pp
  run-to-run variance — rankings statistically meaningless (anatomy);
  Meta Avocado $135B couldn't beat frontier (constraints); Sutskever's
  "age of scaling is over" (constraints); Marcus's GPT-5 "overdue,
  overhyped, underwhelming" (institutional).
- **Unresolved**: Are these measuring the same thing? Plausibly:
  benchmarks are saturating on the old capability surface while agent
  task-horizons are measuring the new (reasoning-RL + scaffolding)
  surface. If so, the exponential is only on the new surface, and the
  question is how much runway that has. Nobody has reconciled this
  explicitly and it must be reconciled before the report.

### T2. Institutional 70-75% vs "AI is still accelerating on hard tasks"
- If institutional forces drive 70-75% of cadence (Institutional), then
  most of what you see in the news is marketing.
- If METR is right and frontier agents are doubling task horizons every
  4-7 months (Anatomy, Analogies), then a substantial share of the
  cadence reflects real capability gains.
- These can both be true only if the "aggregate cadence" and the
  "frontier capability rate" have decoupled — which is itself the most
  interesting finding in the corpus. The orchestrator needs to state
  this explicitly, not leave it as two separate claims in two different
  notes.

### T3. Is pretraining dead, alive, or zombie?
- Sutskever (Nov 2024): plateaued.
- Altman: "no wall".
- Meta: $135B couldn't buy it.
- Epoch: 4-5x/year FLOP growth still holding, Grok-3 >1e26 FLOP.
- GPT-4.5 (Feb 2025): OpenAI's largest pretrained model ever, explicitly
  "not a frontier model", failed.
- GPT-5 (Aug 2025): Epoch says it did hit SOTA; narrative was
  "disappointment".
- Dario (Jan 2025): still early on scaling curve, RL post-training barely
  started.
- **Unresolved**: The constraints note punts on this ("evidence is
  genuinely ambiguous"). The report can't. A deep dive on what the
  December 2024 - February 2025 Orion reporting actually said — and
  whether GPT-5 in August was Orion warmed over, or a new base —
  would clarify whether GPT-4.5 was pretraining's last gasp or a red
  herring.

### T4. What exactly is the DeepSeek-R1 $6M number?
- Anatomy, Constraints, and Analogies all cite $6M.
- Constraints acknowledges it's "not directly comparable" but still
  deploys it rhetorically.
- The orchestrator cannot write "DeepSeek proved frontier reasoning
  costs $6M" without verification. This is one of the most-cited
  numbers of the entire 2025 AI discourse and it's routinely
  misunderstood. Deep dive mandatory.

### T5. The agent-as-product thread vs the model-as-frontier thread
- Institutional note Surprise 5: "the shift from 'model releases' to
  'product releases' may fundamentally change what 'release cadence'
  means" — 74 releases, only 13 were models.
- Anatomy note Pattern 4: agent/tool framing dominant by mid-2025; "the
  release unit is no longer 'model' but 'model + configuration +
  deployment harness.'"
- These are the same phenomenon seen from different angles and nobody
  has tied them together. This might be the actual answer to "what comes
  next" — the post-cadence world is one where there is no "frontier model
  release" as such, only product updates that happen to include model
  updates.

---

## Load-Bearing Claims That Must Be Verified

Prioritized:

1. **Meta Avocado failure and $115-135B capex**. Sole source: The Synthesis.
   Load-bearing for: "capital alone doesn't buy frontier quality",
   Eroom's-Law-is-operating thesis, institutional vs technical split.
   Verifiable via: Meta 10-K/10-Q filings, earnings call transcripts,
   mainstream press (WSJ, FT, Reuters, Bloomberg), LeCun departure
   coverage (Nov 2025 should be well-covered).

2. **DeepSeek-V3/R1 training economics**. Need a clean accounting of what
   the $6M number does and doesn't include, what the full-stack cost
   actually is, and how the architecture delivered the efficiency.
   Primary sources: DeepSeek-V3 arXiv report (already cited), DeepSeek-R1
   arXiv report, SemiAnalysis Dylan Patel critique (he wrote one in
   Jan-Feb 2025), and neutral expert interpretation.

3. **Anthropic RSP v3 text**. The "racing-into-cadence" framing depends
   on the actual revised policy language. Need the Anthropic document
   directly. Also need the direct Atlantic piece ("Anthropic at war with
   itself") or confirmation that such a piece exists.

4. **METR task-horizon data 2025-2026**. The original METR paper is March
   2025. The "still accelerating to 4-month doublings" claim in the
   analogies note cites "AI Digest March 2026". Need to check if METR
   has released updated data or if the acceleration is speculative
   extrapolation.

5. **Densing Law (3.5-month efficiency doubling)**. Must verify the
   Nature Machine Intelligence publication — authors, DOI, methodology.
   Load-bearing for the "efficiency keeps doubling even if frontier
   doesn't" story which is central to any Moore's-Law-late-phase reading.

6. **"74 releases in 52 days" / "267 models in Q1 2026" / "Anthropic 1.4
   releases per day"**. These are spectacular numbers from non-primary
   sources. Anthropic changelog + OpenAI changelog + Google AI blog can
   verify directly.

7. **Dario Amodei "twelve-month delay would make him bankrupt" quote**.
   Need the original Fortune piece. If the quote is real it's the
   cleanest statement of IPO-pressure-forcing-cadence in the entire
   corpus; if it's loose paraphrase, it can't carry the weight the
   institutional note assigns it.

8. **Reasoning compute ceiling claim**. The anatomy note cites "both
   OpenAI and Anthropic researchers were quoted saying RL scaling
   couldn't be sustained for more than 1-2 years by early 2025". Who,
   when, where? This is load-bearing for the "new scaling axis has its
   own near-term wall" argument.

---

## Deep-Dive Assignments

### Assignment 1: The cost-per-capability trajectory (Eroom's Law stress test)

- **Question to answer**: Has the cost of producing a given capability
  increment in frontier LLMs been rising or falling over 2020-2026? Build
  a table of GPT-3, GPT-4, o1, o3, GPT-5, Claude Opus series, Gemini
  series, DeepSeek-V3, DeepSeek-R1 with: estimated training cost (with
  uncertainty), a capability metric (Epoch ECI points, or a set of
  benchmark deltas where comparable, or METR time horizon if available),
  and derive cost-per-capability-point year over year. Does the
  cost-per-unit-capability show the halving-every-9-years signature of
  Eroom's Law? Does it show Moore's-Law-style deflation? Something in
  between?
- **Why it matters**: This is the empirical test for whether Eroom's Law
  is actually operating in LLMs or whether it's merely an aesthetic worry.
  The user flagged it as potentially the most interesting angle. It would
  give the orchestrator a load-bearing chart for the essay.
- **Where to start**: Epoch AI AI Models database has training compute
  estimates for most models; Epoch ECI scoring gives a capability axis;
  the METR paper has task horizons; Stanford AI Index has Elo and
  benchmark deltas. Then overlay the Densing Law (if verified) which
  goes the other direction. Also consult Epoch's "Trends in training
  dataset sizes", and any Pablo Villalobos pieces on efficiency.
- **Primary sources expected**: Epoch AI data insights and
  database, Hoffmann et al. Chinchilla paper, Schaeffer et al. 2025
  Chinchilla robustness paper, arXiv training reports (GPT-4 technical
  report, DeepSeek-V3 arXiv, Llama 3/4 papers).
- **File to write to**: `notes/deep-dive-cost-per-capability.md`

### Assignment 2: Verify the headline numbers and the Meta Avocado story

- **Question to answer**: (a) Did Meta actually fail with a model called
  "Avocado" in early 2026, what is the best independent sourcing, and
  what is Meta's actual 2026 capex guidance? (b) Did Anthropic ship 74
  releases in 52 days, and what is the actual breakdown between model
  releases and product/tool releases? (c) Did OpenAI and Anthropic raise
  at the valuations claimed, on the terms claimed (especially the $35B
  contingent-on-AGI-or-IPO claim)? (d) Does the Dario "twelve-month delay
  would make him bankrupt" quote exist in primary form?
- **Why it matters**: These are the numbers doing the most rhetorical
  work in the institutional and constraints notes. If even one of them
  turns out to be newsletter hallucination, the orchestrator needs to
  know before writing.
- **Where to start**: Meta 10-K/10-Q filings, Reuters/WSJ/FT/Bloomberg
  coverage of Avocado (search "Meta Avocado model 2026"), the original
  Fortune article for Dario, Anthropic and OpenAI changelogs, the TechCrunch
  piece cited for the OpenAI round (needs to be found directly). The
  LeCun departure is well-covered and should be easy to corroborate.
- **File to write to**: `notes/deep-dive-claim-verification.md`

### Assignment 3: The inflection point and "what comes next"

- **Question to answer**: In 2025-2026, what do named practitioners in
  leading labs actually say about the status of pretraining and what the
  next paradigm looks like? Specifically trace: Sutskever after SSI
  (2025-2026), Karpathy (YouTube talks, tweets, blog), Dario Amodei
  (essays beyond "Machines of Loving Grace"), Demis Hassabis, Jeff Dean,
  Yann LeCun (especially post-Meta), Noam Shazeer, plus at least one
  French (Mistral) and one Chinese (DeepSeek Liang Wenfeng, Qwen team)
  perspective. Compile a concrete list of candidate "next paradigms"
  they name — test-time compute scaling, RL environments as first-class
  capital asset, world models, neuromorphic/analog, agent-as-product
  economics, biological/brain-inspired, continual learning, etc. — with
  who champions each.
- **Why it matters**: The user explicitly asked about inflection points
  and replacement patterns. The current notes leave this the thinnest
  area. Without this, the report can only say "Moore's Law analogy, so
  probably multi-core-equivalent will happen" — which is weak and vague.
  With this, the report can take a specific position on what the
  post-cadence world looks like.
- **Where to start**: Karpathy's 2025 YouTube talks (he has been
  publishing long videos), Dario's "On Deepseek and Export Controls"
  (Jan 2025) and any successor essays, the Dwarkesh Patel interview
  series (Sutskever, Dario, Demis have all been on), Latent Space
  podcast, Demis Hassabis interviews around Gemini 3, Mistral blog,
  DeepSeek blog, Liang Wenfeng interviews translated by
  ChinaTalk/RestofWorld.
- **File to write to**: `notes/deep-dive-what-comes-next.md`

### Assignment 4: The "model dissolves into product" thread

- **Question to answer**: Concretely, how much of frontier lab release
  activity in late 2025 and early 2026 is actually product/scaffolding
  releases vs new weights? Using Anthropic, OpenAI, and Google public
  changelogs, build a two-month inventory: how many "releases" were
  (a) new base model, (b) new reasoning/RL post-training on an existing
  base, (c) new tools/harness/computer-use, (d) pricing/config/model-router
  changes, (e) product (Claude Code, Canvas, Operator, Dispatch, etc.)?
  What does this tell us about where the "frontier" has actually moved?
- **Why it matters**: The institutional note flagged this as Surprise 5
  and the anatomy note flagged it as Pattern 4. It might be the actual
  answer to "what comes next" — the post-cadence world is one where
  labs stop shipping "frontier models" and start shipping frontier
  *products*. This is a genuinely novel thesis for the essay and the
  strongest candidate for the report's central argument.
- **Where to start**: Anthropic public changelog (changes.anthropic.com
  or equivalent), OpenAI changelog/release notes, Google AI blog. Also
  look at Ben Thompson Stratechery for the product-framing argument,
  and whether this matches the "service as software" thesis various
  VCs have pushed.
- **File to write to**: `notes/deep-dive-model-to-product.md`

### Assignment 5: Resolve the METR vs benchmark-saturation tension

- **Question to answer**: Is the METR task-horizon exponential and the
  benchmark saturation story measuring the same underlying capability
  from different angles, or are they measuring different things?
  Specifically: when we decompose METR time-horizon gains, how much
  comes from (a) better base model, (b) reasoning RL, (c) improved
  scaffolding/harness? If scaffolding is the dominant component, the
  "exponential" is in agent engineering, not in the model. The anatomy
  note's Gap 4 is exactly this question.
- **Why it matters**: This is Cross-Cutting Tension T1. Without
  resolving it, the orchestrator cannot state whether 2025-2026 is
  closer to the 2004 or the 2016 phase of Moore's Law. And the user
  explicitly wants a position taken, not hedging.
- **Where to start**: METR's March 2025 paper in full (not just the blog
  summary), any METR follow-up notes, the Epoch gradient update "How
  far can reasoning models scale?" in full, and look specifically for
  any papers decomposing time-horizon gains into contributions from
  pretraining vs post-training vs scaffold.
- **File to write to**: `notes/deep-dive-metr-vs-saturation.md`

### Assignment 6 (optional, if capacity allows): The Chinese lab control group

- **Question to answer**: Chinese frontier labs (DeepSeek, Qwen,
  Moonshot, Zhipu, ByteDance Seed) operate without the IPO pressure,
  without the US investor base, often with state capital, and under a
  different safety regulatory regime. Yet their release cadence matches
  or exceeds US labs. What does this tell us about how much of the
  cadence is institutional-US-specific vs a more universal dynamic
  (technical race / competitive momentum / employee incentives)?
- **Why it matters**: This is the natural control group for the 70-75%
  institutional claim. If Chinese labs match US cadence without any of
  the US institutional forces, then either (a) the race-dynamic is
  universal regardless of market structure, or (b) there are equivalent
  institutional forces in China (state pressure, employee poaching,
  domestic brand competition). Either conclusion is interesting.
- **Where to start**: ChinaTalk (Jordan Schneider) interviews and
  newsletters, Jeffrey Ding's ChinAI newsletter, Liang Wenfeng interview
  translations, SCMP, Pekingnology, Matt Sheehan at Carnegie. Epoch AI
  has done several Chinese-lab-specific analyses.
- **File to write to**: `notes/deep-dive-chinese-labs.md`

---

## Verdict

**CONTINUE** — with Assignments 1-5 mandatory, Assignment 6 optional.

The rationale: the corpus has enough raw material to describe the
phenomenon, but not enough cross-verified primary sourcing and not
enough resolution of tensions to write an essay that takes a clear
position. The two most important things missing are (a) an actual
cost-per-capability analysis that would empirically test the Eroom's
Law hypothesis, and (b) a concrete, sourced picture of what the
next paradigm looks like from inside the labs in 2025-2026. Without
those, the report can only describe the cadence — it cannot
argue about where it's going.

The orchestrator has a good timeline and a good set of questions.
What's missing is the evidence that would let the essay settle on
a position rather than hedge between them.
