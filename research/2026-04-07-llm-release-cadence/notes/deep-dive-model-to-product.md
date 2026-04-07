# Deep Dive: Model Dissolving Into Product

## Question

Is "the model dissolving into a product" the actual answer to "what comes next" — i.e., does the apparent release frenzy at frontier labs actually consist primarily of product/scaffolding/tool releases, while model-weight releases have slowed? Is the post-cadence world already here, disguised as continuous product updates?

## Investigation

### Sources Examined

Primary changelogs (read in full for the Feb–Mar 2026 window, with Nov 2025–Mar 2026 context):

- Anthropic API changelog: `docs.anthropic.com/en/release-notes/api`
- Anthropic Claude Apps changelog: `support.claude.com/en/articles/12138966-release-notes`
- OpenAI API changelog: `platform.openai.com/docs/changelog`
- Google Gemini API changelog: `ai.google.dev/gemini-api/docs/changelog`
- Google Gemini App drops: `blog.google` (Feb + Mar 2026)
- ChatGPT product coverage: adsx.com (Feb 2026 roundup), thelivingdraft.com (Feb–Mar 2026)

Secondary / commentary:
- Stratechery (Thompson): "SaaSmageddon and the Super Bowl" (Feb 6, 2026), "Microsoft and Software Survival" (Feb 3, 2026), "Aggregators and AI" (Feb 13, 2026)
- Machine Herald: "OpenAI Launches Frontier" (Feb 6, 2026)
- Releasebot.io Anthropic aggregate

---

## Two-Month Inventory: February–March 2026

### ANTHROPIC

#### API / Platform Changelog (Feb–Mar 2026)

| Date | Event | Category |
|------|-------|----------|
| Mar 30 | Raised max_tokens cap to 300k on Batch API for Opus 4.6 and Sonnet 4.6 | (e) Pricing/config |
| Mar 18 | Added model capability fields to Models API (`max_input_tokens`, `max_tokens`, `capabilities`) | (e) API change |
| Mar 16 | Launched `thinking.display: "omitted"` field for extended thinking (skip thinking in response) | (e) API config |
| Mar 13 | 1M token context window GA for Opus 4.6 + Sonnet 4.6; removed dedicated 1M rate limits | (e) Pricing/config |
| Feb 19 | Launched automatic caching for Messages API | (c/e) Tool/API feature |
| Feb 19 | Retired Claude Sonnet 3.7 and Haiku 3.5 | (e) Deprecation |
| Feb 17 | **Launched Claude Sonnet 4.6** — new model with improved agentic search, 1M context | **(b) New post-training** |
| Feb 7 | Launched fast mode (research preview) for Opus 4.6 | (e) Config/tier |
| Feb 5 | **Launched Claude Opus 4.6** — most intelligent model, adaptive thinking, new architecture | **(b) New post-training** |
| Feb 5 | Launched compaction API (beta), data residency controls, effort parameter GA | (c/e) Tool + Config |
| Jan 29 | Structured outputs GA for Sonnet 4.5, Opus 4.5, Haiku 4.5 | (e) API feature |

Note: Within the 4.x family, the evidence strongly suggests these are the same base architecture with updated post-training, not new pretraining runs. The numbering scheme (Opus 4.5 → 4.6, Sonnet 4.5 → 4.6) and the rapid release cadence (Opus 4.5 Nov 2025 → Opus 4.6 Feb 2026; Sonnet 4.5 Sept 2025 → Sonnet 4.6 Feb 2026) points to continuous post-training rather than new base models.

#### Claude Apps / Consumer Changelog (Feb–Mar 2026)

| Date | Event | Category |
|------|-------|----------|
| Mar 25 | Interactive apps in Claude for iOS/Android | (d) Product |
| Mar 23 | Computer use research preview in Cowork and Claude Code | (c) Tool |
| Mar 17 | Control Cowork from phone via persistent thread | (d) Product |
| Mar 12 | Claude creates interactive charts/visualizations inline | (d) Product |
| Mar 11 | Work across Excel and PowerPoint (add-in improvements) | (d) Product |
| Mar 2 | Memory for free users | (d) Product |
| Feb 25 | Scheduled tasks in Cowork | (d) Product |
| Feb 24 | Cowork plugins and admin controls | (d) Product |
| Feb 17 | Claude Sonnet 4.6 launch (consumer announcement) | (b) Model (same as API) |
| Feb 13 | Analytics API for Enterprise plans | (e) API |
| Feb 12 | Self-serve Enterprise plans | (d) Product |
| Feb 5 | Claude Opus 4.6 launch (consumer); Claude for PowerPoint; Claude for Excel improvements | (b)+(d)+(d) |

**Anthropic Feb–Mar 2026 category counts:**

| Category | Count | Examples |
|----------|-------|---------|
| (a) New base model | 0 | — |
| (b) New post-training on existing base | 2 | Opus 4.6, Sonnet 4.6 |
| (c) Tool / harness / capability | 3 | Computer use in Cowork, compaction API, automatic caching |
| (d) Product / interface | 10 | Cowork features (4), visualizations, memory, Excel/PPT, scheduled tasks, plugins, self-serve enterprise, PowerPoint add-in |
| (e) Pricing / config / API | 7 | 1M context GA, max_tokens cap, model capabilities API, fast mode, deprecations, structured outputs GA, data residency |

**Model releases as % of total Anthropic events: 2/22 = ~9%**

---

### OPENAI

#### API Changelog (Feb–Mar 2026)

| Date | Event | Category |
|------|-------|----------|
| Mar 17 | **Released GPT-5.4 mini and GPT-5.4 nano** | **(b) New post-training** |
| Mar 16 | Updated gpt-5.3-chat-latest slug | (e) Config |
| Mar 13 | Fixed image encoder bug in GPT-5.4 | (e) Bug fix |
| Mar 12 | Expanded Sora API: character refs, longer generations, 1080p, video extensions | (c/d) Tool + Product |
| Mar 12 | Added POST /v1/videos/edits (replacing /remix) | (e) API change |
| Mar 5 | **Released GPT-5.4 and GPT-5.4 pro** | **(b) New post-training/weights** |
| Mar 5 | Tool search in Responses API; built-in computer use for GPT-5.4; 1M context + compaction | (c) Tool |
| Mar 3 | Released gpt-5.3-chat-latest (slug to ChatGPT's production model) | (e) Config |
| Feb 24 | Expanded input_file support to more document types | (c) Capability |
| Feb 24 | Released `phase` parameter for Responses API | (e) API feature |
| Feb 24 | **Released gpt-5.3-codex** | **(b) Specialized model** |
| Feb 23 | Launched WebSocket mode for Responses API | (e) API feature |
| Feb 23 | **Released gpt-realtime-1.5** and **gpt-audio-1.5** | **(b) New model variants** |
| Feb 10 | Batch API for GPT Image models | (e) API feature |
| Feb 10 | Updated gpt-5.2-chat-latest slug | (e) Config |
| Feb 10 | Launched server-side compaction in Responses API | (c) Tool |
| Feb 10 | Launched Skills support in Responses API | (c) Tool |
| Feb 10 | Launched Hosted Shell tool + networking in containers | (c) Tool |
| Feb 3 | Optimized inference stack: GPT-5.2 and GPT-5.2-Codex now ~40% faster (weights unchanged) | (e) Config |

**ChatGPT Product releases (Feb–Mar 2026, from primary coverage):**

- Feb: ChatGPT Agent (unified Operator + deep research + conversational), ChatGPT Shopping research, Instant Checkout (Agentic Commerce Protocol), expanded file uploads (to 20), Projects update (Slack/Google Drive ingestion), Interactive Code Blocks, Business workspace collaboration, deep research overhaul
- Mar: GPT-5.3 upgrade, GPT-5.4 launch, GPT-5.1 retirement, Codex Windows app, learning modules (70+ topics), context window expansion to 256k tokens for Thinking, advertising test on Free/Go tiers

**OpenAI Feb–Mar 2026 category counts:**

| Category | Count | Examples |
|----------|-------|---------|
| (a) New base model | 0 | — |
| (b) New post-training on existing base | 6 | GPT-5.4, GPT-5.4 pro, GPT-5.4 mini, GPT-5.4 nano, gpt-5.3-codex, gpt-realtime-1.5/gpt-audio-1.5 (counting as 1) |
| (c) Tool / harness / capability | 5 | Tool search, computer use, compaction (API), Skills in Responses, Hosted Shell |
| (d) Product / interface | 8 | ChatGPT Agent, Shopping, Instant Checkout, Projects update, Code Blocks, Codex Windows, learning modules, ad test |
| (e) Pricing / config / API | 9 | WebSocket mode, phase parameter, file type expansion, batch for image, slug updates (3), inference optimization, GPT-5.1 retirement |

**Model releases as % of total OpenAI events: 6/28 = ~21%**

(Note: OpenAI's model variant proliferation in this period — nano, mini, codex, realtime, audio — is characteristic of product differentiation within a single base, not fresh pretraining runs.)

---

### GOOGLE

#### Gemini API Changelog (Feb–Mar 2026)

| Date | Event | Category |
|------|-------|----------|
| Apr 2 | Released gemma-4-26b and gemma-4-31b (open models) | (a) New base model (open source) |
| Apr 1 | Introduced Flex and Priority inference tiers | (e) Pricing/config |
| Mar 31 | **Launched Veo 3.1 Lite Preview** (video gen model) | **(b) New specialized model** |
| Mar 31 | Shut down gemini-2.5-flash-lite-preview-09-2025 | (e) Deprecation |
| Mar 26 | **Released gemini-3.1-flash-live-preview** (audio-to-audio) | **(b) New model** |
| Mar 25 | **Launched Lyria 3 music generation** (clip + pro) | **(b) New specialized model** |
| Mar 23 | Prepay and Postpay billing plans in AI Studio | (e) Pricing |
| Mar 18 | Built-in Tools + Function Calling combination feature; Grounding with Google Maps for Gemini 3 | (c) Tool |
| Mar 16 | Revamped Usage Tiers and billing spend caps | (e) Pricing |
| Mar 12 | Project-level spend caps | (e) Pricing |
| Mar 10 | **Released gemini-embedding-2-preview** (multimodal embedding) | **(b) New specialized model** |
| Mar 10 | Deprecation of gemini-2.5-flash-lite-preview-09-2025 | (e) Deprecation |
| Mar 9 | Gemini 3 Pro Preview shut down; gemini-3-pro-preview → gemini-3.1-pro-preview | (e) Config |
| Mar 3 | **Launched Gemini 3.1 Flash-Lite Preview** | **(b) New model** |
| Feb 26 | **Launched Nano Banana 2 / Gemini 3.1 Flash Image Preview** (image model) | **(b) New specialized model** |
| Feb 26 | Deprecation of gemini-3-pro-preview | (e) Deprecation |
| Feb 19 | **Released Gemini 3.1 Pro Preview** | **(b) New model** |
| Feb 19 | Separate endpoint for custom tools | (c) Tool |
| Feb 18 | Deprecation of Gemini 2.0 Flash family | (e) Deprecation |
| Feb 17 | Shut down gemini-2.5-flash-preview, imagen-4 preview versions | (e) Deprecation |
| Jan 29 | Launched Computer Use tool for Gemini 3 | (c) Tool |

**Gemini App "Drops" (Feb + Mar 2026):**

- Feb Drop: Lyria 3 music creation, Gemini 3.1 intro with Deep Think reasoning mode, Nano Banana 2 image model, Veo Templates, scientific citations
- Mar Drop: AI memory/chat history transfer from other providers, Personal Intelligence (free, US, connects Gmail/Photos/YouTube), Gemini on Google TV, Lyria 3 Pro (full songs), Gemini Live upgrade on 3.1

**Google Feb–Mar 2026 category counts:**

| Category | Count | Examples |
|----------|-------|---------|
| (a) New base model | 1 | Gemma 4 (open source, early April) |
| (b) New post-training / specialized model | 8 | Gemini 3.1 Pro, 3.1 Flash-Lite, 3.1 Flash Live, Veo 3.1 Lite, Lyria 3 (x2), gemini-embedding-2, Nano Banana 2 |
| (c) Tool / harness | 3 | Computer Use for Gemini 3, Built-in Tools + Function combo, custom tools endpoint |
| (d) Product / interface | 5 | Personal Intelligence, memory transfer, Google TV, Veo Templates, scientific citations in app |
| (e) Pricing / config | 10 | Multiple billing changes (5), deprecations (4), config changes (1) |

**Model releases as % of total Google events: 9/27 = ~33%**

Note: Google's model count is elevated because they ship far more differentiated product-line models (audio, video, music, image, embedding all separately versioned). The Gemini 3.1 series entries are largely iterative previews of the same architecture.

---

## Release-Mix Analysis

### Aggregate across all three labs, Feb–Mar 2026:

| Category | Anthropic | OpenAI | Google | Total | % |
|----------|-----------|--------|--------|-------|---|
| (a) New base model | 0 | 0 | 1 | 1 | 1.3% |
| (b) New post-training/specialized | 2 | 6 | 8 | 16 | 20.5% |
| (c) Tool / capability | 3 | 5 | 3 | 11 | 14.1% |
| (d) Product / interface | 10 | 8 | 5 | 23 | 29.5% |
| (e) Pricing / config / API | 7 | 9 | 10 | 26 | 33.3% |
| **Subtotal** | **22** | **28** | **27** | **78** | **100%** |

**Model weight changes (a + b): 17/78 = 21.8% of all releases**
**Product + tool (c + d): 34/78 = 43.6% of all releases**
**Infrastructure/config (e): 26/78 = 33.3% of all releases**

### Critical caveat on model categorization

Even category (b) overstates genuine model-weight changes. Several (b) entries are:
- Slug updates pointing to an existing model (not new weights)
- Minor point releases on existing architectures (GPT-5.3 → 5.4 within the same GPT-5 base family)
- Specialized fine-tunes of existing models (gpt-5.3-codex = GPT-5.3 tuned for coding; same with Anthropic's Opus 4.6 which is the same 4.x architecture with new post-training)

A strict reading of "new base model weights" (category a) finds exactly **1 release in two months across three labs**: Google's open-source Gemma 4. If we require "genuinely new pretraining run" as the test, the 2-month score is **1/78 = 1.3%**.

---

## The "Release Rhythm" of Each Lab

### Anthropic

Anthropic has converged on a clear two-track rhythm:

**Track 1: Model weights** — Quarterly or longer. Opus 4.5 (Nov 2025) → Opus 4.6 (Feb 2026) = 3 months. Sonnet 4.5 (Sep 2025) → Sonnet 4.6 (Feb 2026) = 5 months. These are likely post-training updates (new RLHF/reasoning), not new pretraining.

**Track 2: Product/infrastructure** — Continuous, weekly or biweekly. The Claude Apps changelog records 12 distinct product/tool/config releases in Feb–Mar 2026 alone. The Claude Code changelog on Releasebot shows **266 Claude Code releases** in total (vs. 107 for the developer platform), suggesting multiple Claude Code releases per week.

The Releasebot aggregate: **505 total Anthropic releases** tracked (across all Claude products). Of those: Claude Code = 266, Claude Apps = 69, Developer Platform = 107, Claude product = 36. This is unambiguously a software-product release cadence, not a research-lab release cadence.

**Conclusion:** Anthropic moved to a Cowork/Claude Code-driven product cadence. The model weight releases are on a slow drumbeat (roughly quarterly); the product infrastructure releases are continuous deployment.

### OpenAI

OpenAI's pattern is similar but with heavier model-variant proliferation:

**Model releases** occur roughly monthly but are nearly all fine-tunes within the GPT-5.x base: GPT-5 (Aug 2025), GPT-5.1 (Nov 2025), GPT-5.2 (Dec 2025), GPT-5.3 (Mar 2026), GPT-5.4 (Mar 2026) — plus codex, audio, realtime, mini, nano, pro variants. This looks like rapid iteration but is actually product differentiation: the same underlying capability carved into different price/speed tiers.

**ChatGPT product releases** are continuous: agent capabilities (Operator → ChatGPT Agent), shopping, commerce protocol, workspace features, interactive code blocks, learning modules, advertising test — all within Feb–Mar 2026 alone.

OpenAI explicitly launched "Frontier" as an enterprise platform (Feb 5, 2026) — explicitly framing itself as an enterprise SaaS competitor to Salesforce, ServiceNow, SAP. This is the clearest statement of the thesis in corporate action.

**Conclusion:** OpenAI is running a two-track cadence: the ChatGPT product team deploys continuously; the model team does monthly point releases within the GPT-5 family. The "frontier" in "GPT-5.4" is largely a branding claim for a fine-tune.

### Google

Google shows the most complex cadence due to its sprawling multimodal product line:

**Model releases** are frequent but fragmented by modality: video (Veo), music (Lyria), image (Imagen/Nano Banana), audio (Gemini Live), text (Gemini 3.x series). Counting each separately inflates the apparent model release count. The underlying Gemini 3 base appears stable, with point releases (3.0 → 3.1) and modality-specific fine-tunes.

**Gemini Drops** are Google's explicit product-release cadence: a named monthly consumer update (February Drop, March Drop) analogous to a software product's monthly changelog. The March 2026 Drop contained zero new model weights — it was entirely UX, ecosystem, and feature-layer changes (memory transfer, Personal Intelligence, Google TV, extended Live context).

**Conclusion:** Google has adopted the most explicit SaaS-style release cadence, down to named monthly "drops" for consumers, while model weight changes happen on a slower schedule beneath that surface.

---

## Stratechery / Commentator Framing

Ben Thompson did not write a piece explicitly titled "the model is dissolving into the product" — but his Feb 2026 work converges tightly on the same observation from the value-chain angle:

**"Microsoft and Software Survival" (Feb 3, 2026)**: Thompson argues that AI is changing software's *input* (code generation) rather than destroying software as a category. But crucially: "The SaaS story has been about growing the pie: the next decade is going to be about fighting for it, **and the model makers will be the arms dealers**." This frames the model labs as infrastructure providers — arms dealers, not the combatants — while the real competition is at the application layer.

**"SaaSmageddon and the Super Bowl" (Feb 6, 2026)**: The framing names a $730B SaaS market cap destruction as labs (Anthropic with Claude Cowork, OpenAI with Frontier) moved directly into enterprise application territory. Thompson notes that software companies "have more moats than their skeptics acknowledge" but face "painful corrections, consolidation, and substantial layoffs." The implied thesis: the labs are now product companies competing against the SaaS incumbents.

**"Aggregators and AI" (Feb 13, 2026)**: Thompson's discussion of Spotify as a "content network" with individualized delivery frames AI (including the model labs) as a sustaining technology for existing aggregators, not necessarily a replacement. This complicates the "model dissolves into product" thesis by suggesting there are multiple layers.

**OpenAI Frontier launch (Feb 5, 2026)**: Machine Herald coverage describes Frontier as "a semantic layer for the enterprise" — OpenAI's explicit move to compete with SaaS application vendors, treating AI agents as employees with digital identities and onboarding processes. Fidji Simo (OpenAI CEO of Applications) framed it as "one platform to create and manage all of an organization's agents." This is plainly enterprise software positioning, not research lab positioning.

**The "SaaSmageddon" observation**: The combined $730B+ market cap destruction in enterprise SaaS (Adobe, Microsoft, Salesforce, SAP, ServiceNow, Oracle) in early Feb 2026 — triggered by Claude Cowork + OpenAI Frontier announcing simultaneously — is the market pricing in exactly the thesis: model labs are now direct competitors at the application layer, and the "frontier model" is becoming table stakes within a larger product offering.

---

## Assessment: Is "Model Dissolves Into Product" Actually Happening?

### The empirical verdict: Yes, and it's measurable.

The data supports the thesis strongly. Three independent findings converge:

**1. Release-mix data is decisive.** In a representative two-month window (Feb–Mar 2026), new-base-model releases constitute approximately 1.3% of all releases (1/78) and new post-training releases constitute an additional ~20% — for a total model-weight-change share of ~22%. Product/interface releases and infrastructure/config releases account for ~77% of all activity. This is a SaaS product team's cadence, not a research lab's cadence.

**2. The model versioning systems confirm it.** Anthropic's 4.5 → 4.6 versioning, OpenAI's 5.0 → 5.1 → 5.2 → 5.3 → 5.4 versioning, Google's 2.5 → 3.0 → 3.1 versioning all tell the same story: point releases within a fixed base architecture, not new pretraining runs. The appearance of rapid model release velocity is actually rapid post-training iteration — which is far cheaper, faster, and more product-driven than frontier research.

**3. Corporate positioning has explicitly shifted.** OpenAI launched "Frontier" as an enterprise agent platform (not a model). Anthropic launched "Cowork" as a knowledge-work product suite. Google renamed model releases as "Drops" and made them monthly consumer events. None of these framings are research communications; all are product communications.

### Where the thesis is partially wrong or overstated:

**Post-training is still substantive work.** Calling Opus 4.6 "just a product update" would understate it. Extended thinking, adaptive reasoning, improved coding benchmarks — these are real capability jumps achieved through significant post-training compute. The line between "model research" and "product engineering" is blurring precisely because RLHF/RLAIF at scale is becoming a product-team function, not a pure research function. The thesis holds, but "model dissolving into product" should be read as "research becoming engineering" rather than "models stopping improving."

**Google's model count is elevated for structural reasons.** Google ships video, music, audio, image, and embedding models separately, inflating apparent model velocity. Gemini 3's proliferation of specialized variants (Flash, Flash-Lite, Flash-Live, Nano Banana, embedding) is partly a product architecture choice (separate models for separate modalities) rather than evidence of accelerating frontier research.

**The strongest version of the thesis applies most cleanly to Anthropic.** Anthropic's 266-release Claude Code changelog vs. 2 model releases in two months is the starkest illustration. Google's model-release count (8 in category b over two months) looks more like research activity — but most of those are modal specializations, not new base capability.

---

## Implications for the Cadence Question

If the model dissolves into the product, the "release every 3 months" framing of frontier model cadence becomes an artifact of an earlier phase. The actual question is already shifting from:

- "When does Claude 5 ship?" → "What can Claude Code do this week?"
- "When does GPT-6 ship?" → "What does ChatGPT Agent do this month?"
- "When does Gemini 4 ship?" → "What's in this month's Gemini Drop?"

The release cadence that everyone perceived as "frantic" (a new model every 3 months) is actually the *slow track* — the research post-training cycle. The fast track — product deployment — is continuous. Nobody asks when Gmail's next version ships; they notice when a new feature appears.

This creates a specific prediction: the concern about "slowing cadence" for frontier model releases is a legitimate observation about one track, while the product release velocity keeps going up regardless. The public discourse conflates the two tracks. When people worry about "model release slowdown," they are tracking the wrong clock.

**The deeper implication**: Competitive advantage is progressively shifting from "having better weights" (the research-lab frame) to "having better scaffolding, tooling, and product layer" (the software-company frame). This is already visible in the fact that both Anthropic and OpenAI are competing on enterprise agent platforms — products — not on benchmark superiority alone. The "frontier" is softening into a product differentiator rather than a hard gate.

---

## Key Findings

1. **New base model weights (category a) = 1.3% of all Feb–Mar 2026 releases across three labs.** Only Gemma 4 (open source) qualifies. (Strong evidence — primary changelogs.)

2. **Post-training model updates (category b) = ~20% of all releases.** These are versioning updates within existing base architectures (GPT-5.x series, Claude 4.x, Gemini 3.x). They are substantive but not "frontier research" in the classical sense. (Strong evidence.)

3. **Product/tool/infrastructure = ~77% of all releases.** The largest single category is pricing/config/API (33%), followed by product/interface (30%), then tools/capability (14%). (Strong evidence — primary changelogs.)

4. **Anthropic is the clearest case.** 266 Claude Code releases total vs. 2 model releases in Feb–Mar 2026. The release ratio is approximately 133:1 in favor of software product activity. (Strong evidence — Releasebot aggregate.)

5. **Thompson's "SaaSmageddon" framing** (Feb 2026) confirms the market is pricing in labs as product competitors to SaaS incumbents, not as pure infrastructure providers. The $730B+ SaaS equity destruction coincided with Claude Cowork + OpenAI Frontier launching. (Moderate evidence — secondary market reaction.)

6. **All three labs have adopted explicit product-release structures.** Google's "Gemini Drops" (monthly consumer updates), Anthropic's Cowork feature cadence, OpenAI's ChatGPT Agent evolution — these are software product management practices, not research communication practices. (Strong evidence — public communications.)

7. **The "fast frontier" concern conflates two tracks.** Model-weight cadence is slowing (or at minimum, becoming harder to perceive as discontinuous jumps). Product-layer cadence is accelerating. The industry commentary that focuses on "model release frequency" is tracking the wrong clock. (Moderate evidence — inference from data.)

---

## Open Gaps

1. **No public data on pretraining compute timelines.** We cannot directly verify when the last new base pretraining run happened for any of the three labs. The inference that Claude 4.x, GPT-5.x, and Gemini 3.x are all post-training iterations of fixed bases is strong but circumstantial. Lab employees who know the actual architecture won't say publicly.

2. **Claude Code's 266 releases need qualitative breakdown.** The Releasebot count tells us software-product velocity but not the distribution of those releases by type. Some Claude Code releases may include model-behavior changes (e.g., system prompt updates, tool execution changes) that blur the software/model boundary.

3. **The post-training/base-model boundary is genuinely fuzzy.** A RLHF run that involves significant architectural changes (e.g., Claude 4.5 → 4.6 if the extended thinking system is substantially different) might legitimately be called "new model weights" even without new pretraining. The nomenclature is insufficient to resolve this.

4. **Stratechery's paywalled content limits direct access.** Thompson's most detailed analysis on the "model makers as arms dealers" thesis is behind the subscription wall. The free-tier summaries and related posts give us the framework but not the full argument.

5. **The Cowork / Claude Cowork launch is poorly documented in terms of timing.** Machine Herald (Feb 6, 2026) references "Claude Cowork triggered a $285 billion rout in software stocks" but the Anthropic news page doesn't show a separate Cowork launch announcement in this window. The Claude Apps changelog shows Cowork features being added incrementally through Jan–Mar 2026. This matters because the thesis depends partly on whether Cowork was a discrete product launch or a continuous feature expansion.
