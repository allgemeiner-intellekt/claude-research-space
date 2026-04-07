# Review — Round 2

Crumble's bubble belongs to Crumble. Down to business.

## Overall Assessment

The corpus is now in strong shape. The six deep dives did exactly what they
were assigned to do, and several of them did more — they overturned
load-bearing claims from round 1 (DD2), produced a clean four-layer model
that resolves the central tension (DD5), and gave the essay a quantitatively
grounded centerpiece (DD1's two-trajectory cost picture). The orchestrator now
has enough raw material — and enough internal coherence between findings —
to write an essay with a real position rather than a hedged survey.

There is one remaining gap that is *interesting* rather than load-bearing
(the Carlota Perez installation→deployment frame, flagged in the historical
analogies survey and never picked up), but it is a frame the orchestrator
can apply themselves at write-time using material already in the corpus.
There is no factual or interpretive hole that requires another agent
dispatch to close.

**Verdict: SATISFIED.** Recommendation below.

---

## Synthesis: What the Corpus Now Contains

### 1. The two-trajectory cost picture (DD1)

The single most important quantitative finding. The Eroom's-Law-vs-Moore's-Law
dichotomy in the round-1 analogies survey was the wrong frame because both
are operating simultaneously, on different populations:

- **Frontier trajectory:** Final-run training cost growing at **2.4x/year**
  (Epoch AI, 95% CI 2.0–3.1x). That is a doubling every 5–6 months — roughly
  *18x faster* escalation than Eroom's Law's 9-year doubling. Total
  organizational R&D compute is ~10x the final-run figure (Epoch AI March
  2026 + the OpenAI 2024 spend analysis: $5B total → ~$500M to released
  final runs). GPT-4.5's final-run cost lands somewhere in $130M–$1.2B; Grok-3
  at ~$400M rental equivalent.
- **Replication trajectory:** Compute needed for a fixed capability halves
  every **~8 months** (Epoch AI / Erdil et al.); the Densing Law (Xiao et al.,
  Nature MI 2025, *confirmed in DD2*) gives capability-per-parameter doubling
  every 3.5 months for open-source models. DeepSeek V3 is the concrete 2024
  data point: ~$5.6M compute rental for GPT-4o-class capability. The Mertens
  et al. (2026) 809-model "Secret Sauce" paper formalizes the structure: at
  the frontier 80–90% of performance variance is compute; away from the
  frontier proprietary techniques and diffused knowledge dominate.

The two trajectories are not contradictory — they describe different actors
making different choices. Frontier labs run up trajectory A; replicators ride
trajectory B. The replication trajectory is the dynamic that keeps the
"cadence" sustainable in user-perceived terms even when frontier compute
escalation hits walls.

### 2. The four-layer reconciliation of "exponential vs. flattening" (DD5)

DD5 fully resolves the headline tension from review round 1. The crucial
piece of evidence is METR's own February 2026 ablation (Jurkovic et al.):
Claude Code beats METR's generic ReAct scaffold in only **50.7%** of bootstrap
samples (statistically zero), and Codex *loses* to Triframe in 85.5% of
samples. That is a near-direct experimental refutation of the harness
hypothesis — the METR exponential is *not* in scaffolding.

The four-layer model that emerges:

1. **Pretraining capability** — decelerating at the frontier. GPT-4.5 is
   the strongest single piece of negative evidence: largest pretraining run
   OpenAI had done, no frontier advance, underperformed DeepSeek-V3 on math.
2. **RL post-training capability** — rising fast, with finite runway. The
   ECI April 2024 breakpoint (8→15 ECI/year, R²=0.97) and METR's October
   2024 acceleration both coincide with the o-series. DeepSeek-R1-Zero
   ablation shows pure RL on a base model dramatically outperforms the
   base. Epoch AI projects RL compute will converge with overall training
   compute within 1–2 years (from mid-2025), at which point its growth rate
   slows from 10x/few-months to 4x/year.
3. **Harness/scaffolding** — flat as a contributor to METR's metric, but
   the dominant value-creation lever in production (Claude Code, Cursor,
   Codex). This is the layer where METR's exponential is *not*, but where
   the user-perceived progress *is*.
4. **Cost per capability** — falling fast (Densing Law, inference cost
   collapse). The cleanest exponential trend in the corpus.

These four can all be true simultaneously, and most disagreements in the
2025–2026 discourse collapse once you specify which layer the speaker is
talking about.

### 3. The model-to-product transition (DD4)

Empirically pinned down. In the Feb–Mar 2026 window across Anthropic, OpenAI,
and Google:

- New base-model weights (category a): **1/78 = 1.3%** — only Gemma 4 (open
  source).
- Post-training updates within an existing base (category b): ~21%.
- Tools / capability / harness (c): ~14%.
- Product/interface (d): ~30%.
- Pricing/config/API (e): ~33%.

The Anthropic ratio is the starkest single number in the corpus: **266 Claude
Code releases vs. 2 model launches (Opus 4.6, Sonnet 4.6) in the Feb–Mar
window** — roughly 133:1. Stratechery's "SaaSmageddon" framing and the
~$730B early-Feb 2026 SaaS market cap drop coinciding with Cowork + Frontier
launches are the market pricing-in of the same thesis from outside.

### 4. Practitioner consensus on what comes next (DD3)

Across 10+ named senior practitioners with primary sources (Sutskever's
Dwarkesh interview, Karpathy's year-in-review + Dwarkesh + YC keynote,
Amodei's "End of the Exponential" Dwarkesh interview, Hassabis at Davos +
Hannah Fry podcast, LeCun's MILA keynote + AMI Labs founding, Jeff Dean on
Latent Space, Liang Wenfeng's translated Sina interview, Altman's Big
Technology interview, Lample on Latent Space, Silver/Sutton "Era of
Experience" paper):

- **Consensus**: pretraining-as-pretraining is approaching a ceiling
  (Sutskever explicit, Amodei explicit, Hassabis softer, Altman conspicuously
  silent). The next axis is some flavor of experience-based learning —
  RL environments, continual learning, world models — with environments as
  the new "data" being the strongest convergence point (Karpathy + Silver +
  Sutton + Hassabis institutionally via Genie+SIMA + Amodei explicitly).
- **The fault line**: LeCun is the contrarian outlier, the only senior
  voice arguing for a clean architectural break from autoregressive token
  prediction. Everyone else thinks LLMs are necessary, debating only whether
  they're sufficient. AMI Labs at $3.5B valuation is the falsifiable bet.
- **Karpathy's productive contradiction**: RLVR was the 2025 paradigm shift
  but RL is "terrible" / "sucking supervision through a straw." It just
  happens to be better than what came before. The "real" next thing is
  interactive environments, with system-prompt learning as a candidate
  research direction nobody has properly explored.

### 5. The Chinese-labs reframing (DD6)

The round-1 institutional survey's "70-75% US-institutional" claim is not
sustained by the Chinese evidence, but the alternative is *not* "universal
race dynamic." It is **equivalent institutional forces in different forms**:

- DeepSeek: research culture + AGI mission + state prestige (Xi Jinping
  personally endorsed DeepSeek; Liang met Premier Li Qiang) + export controls
  as a forcing function for efficiency innovation.
- Qwen / ByteDance: cloud market competition (the Chinese analog to MSFT
  vs GOOG cloud + AI), not IPO pressure.
- Moonshot / MiniMax: talent and brand signaling + lighter IPO-track pressure.
- Zhipu: state-backed capital + first-foundation-model-IPO ambition.
- Tencent: counter-example — low text-frontier cadence, concentrated in
  specialized modalities. Confirms that institutional structure matters
  *as the form of the pressure*, not just the existence of pressure.

The deeper finding from DD6 is the **dual frontier structure**: Chinese labs
run an efficiency frontier (DeepSeek MLA/MoE/GRPO; MiniMax M1 at $534K RL
training; Zhipu's 90% price cuts) in parallel with capability claims (R1,
Kimi K2 Thinking, Qwen3-Max-Thinking on Humanity's Last Exam). The two
frontiers compound but have different sustainability profiles. This maps
cleanly onto DD1's two-trajectory structure: the Chinese efficiency frontier
*is* the replication trajectory, partially.

### 6. DD2's claim verification — the corrections that matter

DD2 was uncomfortable but necessary. The newsletter-grade institutional survey
left several load-bearing claims that did not survive primary-source contact:

- **Dario "twelve-month delay would bankrupt me" — REFUTED.** The real Fortune
  quote is about *revenue growth rate forecasting risk* ("if growth is 5x a
  year instead of 10x a year, then you go bankrupt") — a capital-allocation
  warning about overbuilding compute against optimistic revenue forecasts,
  not a competitive cadence pressure statement. The orchestrator must use
  the real quote and the real framing. It still supports the IPO/pressure
  thesis, but in a more nuanced way.
- **RSP v3 "races into cadence" — OVERSTATED.** What RSP v3 actually does is
  abandon the unilateral pause commitment. Anthropic now matches *competitor
  safety mitigations*, not competitor *release cadences*. The competitive
  logic is about safety mitigation quality, not release velocity. The
  Atlantic article attribution could not be verified.
- **"RL ceiling in 1–2 years" attributed to OpenAI/Anthropic researchers —
  REFUTED.** It is an Epoch AI analyst (Josh You) projecting that RL compute
  will *converge* with overall training compute within ~1 year, after which
  the *rate* slows. The researchers actually quoted (Amodei, OpenAI staff)
  are publicly optimistic about RL scaling. The "researchers said RL has a
  near-term wall" framing is wrong on both attribution and direction.
- **Anthropic "74 releases in 52 days, 13 of them models" — METHODOLOGY
  CORRECTION.** The 74 number comes from a Product Compass newsletter
  trawl of eight Anthropic employees' Twitter feeds, not the official
  changelog. The actual number of distinct *model launches* in the window
  is ~3 (Opus 4.6, Sonnet 4.6, Fast Opus 4.6). The "13 model releases"
  figure overcounted by ~4x. The 74-total figure isn't *wrong*, it just
  counts every changelog tweet across all surfaces as a "release."
  (Importantly: this correction does not weaken the model-dissolves-into-
  product thesis — DD4's Anthropic ratio of 266 Claude Code releases to
  2 model releases over the same window is *more* extreme, not less, than
  the 74:13 framing suggested.)
- **CONFIRMED at primary-source level**: Meta $115–135B 2026 capex (Q4 2025
  earnings press release verbatim), Avocado underperformance (NYT March 12
  2026), Yann LeCun's Nov 2025 departure and AMI Labs founding,
  OpenAI $110B at $730B pre / Anthropic $30B at $380B post / the $35B
  Amazon contingent tranche (deadline corrected to Dec 2028, not 2026),
  Densing Law publication in Nature MI.

---

## Tension Resolution Status

| Tension | Status |
|---|---|
| T1: exponential vs. flattening | **Resolved** by DD5's 4-layer model. The exponential lives in (ii) RL post-training and (iv) cost-per-capability. The flattening is in (i) pretraining. (iii) Harness is flat as a *METR driver* but rising as a *value generator*. |
| T2: institutional vs. accelerating | **Resolved** by DD2 + DD6. The institutional pressure is real, but the round-1 70-75% number was not derived from anything and DD2 corrected several of its supporting claims. DD6 reframes it: the pressures are universal across competitive contexts, but their *form* is institutionally specific. |
| T3: pretraining dead/alive/zombie | **Resolved** by DD3 + DD5. Decelerating but not dead. GPT-4.5 was its near-last gasp at the frontier; the distillation/efficiency cascade keeps it useful. Sutskever, Amodei, Hassabis all converge here in different language. |
| T4: DeepSeek $6M number | **Resolved** by DD1. The $5.576M is confirmed as the V3 final-run rental cost (2.788M H800 hours × $2/hr from the tech report). It excludes ~$1.6B hardware capex and ~$944M operating costs (SemiAnalysis). It is a real number that means something narrow. The Densing Law gives it field context. |
| T5: model vs. product unit | **Resolved** by DD4. 1.3% of Feb–Mar 2026 releases are new base weights; 22% are model-weight changes total; 78% are product/config/tool. Anthropic 266:2 Claude Code:model ratio is the headline. |

### New tensions introduced by the deep dives

- **The ECI April 2024 breakpoint vs. the o1 release in September 2024.**
  DD5 flags this as the unexplained piece. ECI accelerated 5–6 months
  before reasoning models went public. Either internal RL experimentation
  was already in flight by April 2024 at OpenAI/Google/Anthropic (likely),
  or pretraining quality/architecture improvements briefly mattered, or
  ECI is a noisy lagging signal. *This is interesting but the orchestrator
  can flag it as an open question rather than resolve it.*
- **Hassabis vs. the consensus on pretraining decline.** Hassabis is
  notably more bullish on continued pretraining gains than Sutskever or
  Amodei. ("There's still plenty of headroom there, just with techniques
  we already know about.") Either DeepMind is sitting on something
  (Gemini 3's success suggests possibly), or Hassabis is institutionally
  required to be optimistic, or the pretraining-ceiling consensus is more
  contested than DD3 makes it look. *The orchestrator should not flatten
  this — it is a real disagreement among well-informed insiders.*
- **The DD3 "experience-based learning consensus" vs. Karpathy's "RL is
  terrible" critique.** Karpathy is bullish on environments, bearish on
  RL as the optimization mechanism. This is a productive contradiction
  the essay should preserve rather than smooth.

---

## Remaining Gaps (Honest Assessment)

These exist but do not require additional agent dispatches:

1. **No deep coverage of the Carlota Perez installation→deployment frame**
   that the round-1 analogies survey flagged. This was deferred and never
   picked up. *However*: DD4 (model-to-product) is essentially the
   installation→deployment story expressed in different language. The
   orchestrator can apply Perez's frame as a synthesis lens at write-time
   using DD4's data. Not worth a separate agent dispatch.

2. **No SSI release data point.** Sutskever has not shipped a model. The
   "different technical approach" remains opaque. This is a future research
   topic, not a gap in the current investigation.

3. **The pretraining-vs-RL decomposition for METR has not been done by
   anyone.** DD5 notes this explicitly: METR provides no causal
   decomposition between base model and RL contributions to time-horizon
   gains. The scaffold question is answered (it's not scaffold); the
   base-vs-RL split is inferred from timing correlation and the
   DeepSeek-R1-Zero ablation, not directly measured. *No amount of further
   agent work can close this gap — the literature does not contain the
   experiment.* The orchestrator should state this honestly.

4. **The user-perception question** (does cadence "look fast" because users
   perceive constant change, or is user-perceived progress flattening?) is
   indirectly answered by DD4 (product layer ships continuously, model
   layer slows) but not directly investigated. This would be a useful
   secondary research thread but the answer is essentially dictated by
   DD4's ratios.

5. **Hassabis's bullish-on-pretraining position is in tension with the
   rest of DD3 and not fully reconciled.** This is real but small. The
   orchestrator can name it as a live disagreement.

None of these gaps would justify another full agent cycle. They are gaps
the essay should *acknowledge*, not gaps the essay needs *closed*.

---

## Verdict

**SATISFIED.** Write the essay.

The corpus has reached the point where additional research would produce
diminishing marginal insight relative to the cost of another cycle. The
six deep dives delivered:

- A quantitative centerpiece (DD1's two-trajectory cost picture)
- A clean reconciliation of the central tension (DD5's four-layer model)
- An empirically grounded thesis on what's actually happening
  (DD4's model-to-product data)
- A grounded view of the field's own self-understanding (DD3's
  practitioner consensus)
- A control group that reframes (rather than refuting) the institutional
  argument (DD6)
- The verification that prevents the report from amplifying newsletter
  hallucinations (DD2)

The orchestrator now has more than enough to take a strong position. The
remaining open questions are real but are *future research topics*, not
present obstacles.

---

## Suggested Essay Outline (Brief)

### Central thesis

**The inflection point in LLM release cadence already happened — twice — and
the cadence persists not because the technology stayed constant but because
the *unit of release* mutated each time the underlying engine changed.**
The first inflection (April–October 2024) was when frontier capability
gains shifted from pretraining scale-up to RL post-training, with reasoning
models as the visible signal. The second inflection (mid-2025 to early
2026) is when "the model" dissolved into a product surface — Claude Code,
ChatGPT Agent / Frontier, Gemini Drops — such that release activity
decoupled almost entirely from new base weights (1.3% of recent releases).
The cadence is sustainable not because frontier scaling will continue
indefinitely, but because the question "what is sustainable?" was the wrong
question all along: each phase of the cadence is sustained by a different
mechanism, and the mechanism keeps changing.

### Suggested structure

1. **Hook**: the 1.3% number. New base-model weights are 1 in 78 recent
   "frontier lab releases." The cadence everyone is debating the
   sustainability of is not the cadence of the thing they think it is.

2. **Two trajectories, not one** (DD1). The Eroom-vs-Moore dichotomy is
   wrong because both are operating, on different populations. Frontier
   cost doubles every 5–6 months; replication cost halves every 8 months.
   This is the structural background for everything that follows.

3. **The first inflection: April–October 2024**. ECI breakpoint, METR
   acceleration, o1 release, the rise of RL post-training. The 4-layer
   model from DD5: pretraining decelerating, RL rising fast with finite
   runway, harness flat as METR driver but rising as value generator,
   cost-per-capability still exponentially deflating. GPT-4.5 as
   pretraining's last gasp at the frontier.

4. **The second inflection: 2025–2026**. The model dissolves into product.
   DD4's data is the centerpiece here — the 266:2 Anthropic ratio,
   Stratechery's SaaSmageddon framing, the Gemini Drops structure, the
   shift from research-communication to product-communication. This is
   what "post-cadence" actually looks like in the wild.

5. **Why labs keep racing** (DD2 + DD6). The institutional pressure is
   real but more nuanced than "IPO panic." The Dario-bankruptcy quote,
   reframed correctly, is about overbuilding compute against optimistic
   revenue forecasts — a capital-allocation argument, not a competitive
   cadence one. The Chinese control group shows that the pressures are
   universal across competitive contexts but their institutional form is
   contingent (cloud war, state prestige, talent competition, export-
   control efficiency forcing). RSP v3 is about safety mitigation quality,
   not racing into cadence — and the corrected version of that story is
   actually a *stronger* argument for collective-action cadence pressure.

6. **What comes next** (DD3). The convergence on experience-based learning
   as the next axis. Karpathy's "environments" as the closest field-wide
   bet. LeCun's $3.5B contrarian bet on JEPA. The Hassabis nuance: LLMs
   necessary but probably not sufficient. Sutskever's deliberate opacity
   and the SSI bet. What this means: even the people who agree pretraining
   is decelerating do not agree about what replaces it.

7. **The historical analogy that actually fits**. Intel post-tick-tock,
   not pharma's Eroom or telecom's broadband saturation. An industry that
   maintained release rhythm by pivoting through three-phase cycles, then
   chiplets, then packaging, while the underlying physics ran out. With
   one sharper claim: the LLM analogy is *better* than Intel because the
   release rhythm is now driven by software product cycles (DD4), not
   research cycles, which means it can persist indefinitely with no
   "real" wall. Even if pretraining stops cold, Claude Code releases
   continue. *(The Carlota Perez installation→deployment frame fits here
   naturally — the orchestrator can apply it without needing more
   research.)*

8. **The unresolved tensions**. Be honest about: the ECI/o1 timing gap,
   Hassabis vs. the pretraining-ceiling consensus, the absence of a
   direct base-vs-RL decomposition for METR's exponential, what SSI is
   actually doing, whether environment-based RL generalizes beyond
   verifiable domains. These are the open questions section.

### What the strongest evidence chains are

- For the two-trajectory cost picture: Cottier et al. 2024 (Epoch AI)
  + Erdil et al. 2024 (Epoch AI) + DeepSeek-V3 tech report + SemiAnalysis
  Jan 2025 + Mertens et al. 2026.
- For the four-layer model: METR Jurkovic Feb 2026 ablation + DeepSeek-R1
  paper + Epoch AI ECI + Epoch AI "How far can reasoning models scale?"
  + GPT-4.5 reception evidence.
- For model-to-product: DD4's primary changelogs (Anthropic, OpenAI,
  Google) + Releasebot aggregate + Stratechery Feb 2026 pieces.
- For practitioner consensus: Sutskever Dwarkesh + Karpathy year-in-review
  + Amodei Dwarkesh + Hassabis Davos + Silver/Sutton "Era of Experience."
- For Chinese control group: Liang Wenfeng ChinaTalk translation +
  ChinAI #348/#349 + DeepSeek API changelog + Recode China AI.

The orchestrator should not need to do additional fact-finding to write
this essay. The synthesis work — connecting the threads, taking the
position, applying the Perez frame, naming the unresolved tensions —
is exactly what the orchestrator role exists for.
