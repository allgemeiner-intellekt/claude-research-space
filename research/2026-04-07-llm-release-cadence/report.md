# The Inflection Already Happened (Twice)

## On the supposed sustainability of the LLM release cadence

There is a question that everyone in or near AI has been asking each other at
parties for about three years: *Can this possibly keep up?* New frontier model,
new benchmarks, new headlines, every couple of months, on schedule, like a
Marvel release calendar — surely the physics, or the economics, or the
investors, or the data, will eventually break this rhythm? Surely we are about
to hit some kind of wall, some kind of plateau, some kind of inflection?

The honest answer, after looking at it carefully, is that the question is the
wrong question. The inflection point everyone has been waiting for already
happened. It happened twice, in fact, between April 2024 and February 2026, and
the cadence persisted across both inflections without anyone really noticing.
What broke and was replaced was not the cadence — the cadence is fine — but
the *thing* that the cadence is delivering. The release rhythm everybody is
debating the sustainability of is not the rhythm of the thing they think it is.

Here is the single most surprising number from this investigation. In a
representative two-month window (February–March 2026), I and one of my agents
combed through the official changelogs of Anthropic, OpenAI, and Google for
every public "release." We classified 78 distinct events. Of those, exactly
**one** was a genuinely new pretrained base model, and that one was Google's
open-source Gemma 4. **One in seventy-eight, or 1.3%.** [1] The other 77 were
post-training updates on existing bases, scaffolding tools, product features,
pricing tiers, deprecations. The cadence everyone is debating the sustainability
of is the cadence of a software product team, not the cadence of a frontier
research lab. Whatever you thought you were watching when you watched the
release calendar, you were probably watching something else.

This essay argues that the LLM industry has, very quietly, completed its
transition through the same kind of phase change that semiconductor
manufacturing went through twice — once when Dennard scaling died around 2005,
once when Intel formally retired its tick-tock strategy in 2016 — and that the
release rhythm has continued through both transitions for the same reason
Intel's release rhythm continued through theirs. The substance of what is
"new" each release has changed; the metronome has not. There is no future
inflection coming because the inflection is in the past tense. The interesting
question is not whether the cadence is sustainable but what it is now a cadence
*of* — and the answer, it turns out, is much weirder and more interesting than
"frontier AI."

---

## I. Two trajectories, not one

Most of the public discussion about LLM sustainability is a collision between
two camps that are actually talking past each other. One camp says the cost of
training a frontier model is exploding — GPT-3 cost a few million, GPT-4 around
$60 million, GPT-4.5 anywhere from $130 million to $1.2 billion [2] — and this
cannot continue. Sam Altman has openly committed OpenAI to over a trillion
dollars in compute and infrastructure deals through 2035. [3] The other camp
says this is silly because the cost of *replicating* a given capability is
collapsing fast: DeepSeek shipped a GPT-4o-class model in December 2024 for a
final-run rental cost of about $5.6 million. [4] These two camps spend a lot of
time arguing past each other on Twitter and they are both right.

The cleanest empirical anchor here comes from Epoch AI's 2024 paper by Cottier
and colleagues. [5] They built a careful cost model for top-10-compute frontier
training runs since 2016 and found a growth rate of **2.4x per year** (95% CI:
2.0–3.1x), which is a doubling every five to six months. That is a staggering
escalation. By comparison, Eroom's Law — the famous pharmaceutical "anti-Moore"
observation that drug R&D productivity has been halving every nine years since
1950 [6] — looks gentle. The frontier LLM cost trajectory is escalating roughly
**eighteen times faster** than Eroom's Law would predict. And it actually
understates the total bill. A separate Epoch piece, drawing on disclosure from
OpenAI's 2024 financial year, found that final training runs are only about
**10% of total R&D compute spend**: of the roughly $5 billion OpenAI spent on
compute in 2024, only ~$500 million went into the final runs of released
models. [7] The other $4.5 billion was experiments, ablations, failed runs, and
synthetic data generation. The total organizational compute commitment to
producing a frontier release is therefore an order of magnitude larger than the
"training cost" headline number. This is the side of the picture the "AI is
unsustainable" camp is pointing at, and they are not making it up.

But the other side of the picture is just as well-evidenced. The same Epoch
group's algorithmic-progress paper (Erdil et al., 2024) found that the compute
needed to achieve a fixed capability threshold has been **halving every ~8
months** (95% CI: 5–14 months) since at least 2012. [8] Hardware progress
contributes some of that; algorithmic progress contributes the rest. Then in
December 2024 a Tsinghua group published the "Densing Law of LLMs" in *Nature
Machine Intelligence* [9] — an even more aggressive observation: capability per
parameter for open-source models is doubling roughly every **3.5 months**.
Dario Amodei has independently estimated the compounded efficiency improvement
at as much as 10x per year. SemiAnalysis pegs it at 4x per year. [10] However
you measure it, the deflation is real and it is fast.

The right framing is not "is it Moore's Law or Eroom's Law" but **two
trajectories operating simultaneously, on different populations**:

- **Frontier trajectory (Eroom-like, but much faster):** the most capable model
  at any given moment costs 2.4x more compute per year than the previous one.
  This is the trajectory OpenAI, xAI, Anthropic, and Google are running on.
  Each successive frontier release demands a bigger cluster, more power, more
  capital, more wall-clock time. GPT-4.5's training cluster (40,000–100,000
  H100s for 90–165 days) is a national-grid-scale energy commitment. [11]
- **Replication trajectory (faster than Moore's Law):** the cost to *reach* a
  given capability level — call it "GPT-4-equivalent" — falls by roughly 4x per
  year. The estimated cost to train a GPT-4-equivalent model in 2026 is on the
  order of $1 million, down from $60M in 2023. [10] The Densing Law gives this
  trajectory its sharpest empirical signature. DeepSeek V3 is its concrete
  artifact. This is the trajectory the open-source ecosystem and the Chinese
  labs are running on.

A 2026 study by Mertens, Fischl-Lanzoni, and Thompson [12] put a clean
econometric structure on this: in their analysis of 809 models from 2022–2025,
**80–90% of the variance in frontier-model performance is explained by training
compute alone**, with proprietary techniques contributing relatively little.
But *away from the frontier*, the picture inverts — proprietary methods,
distillation, MoE, MLA, and architectural cleverness explain most of the
variance. The two trajectories really are different games being played by
different actors, not a single curve in disguise.

This matters because it is the structural backdrop for everything that follows.
Both trajectories are exponential. Both are real. They are pulling in opposite
directions. The cadence of frontier releases is sustained partly by the second
trajectory: the labs can keep shipping because much of what they are shipping
is not actually new compute on the same problem — it is the application of
last year's compute to a slightly different problem, or the distillation of
last year's frontier into this year's product surface.

---

## II. The first hidden inflection: pretraining → reasoning, April 2024

Here is a story you can tell about the public LLM timeline, in three sentences.
Until early 2024, frontier progress meant a bigger pretrained model — GPT-2
to GPT-3 to GPT-4, larger and larger autoregressive transformers trained on
larger and larger corpora of internet text, with capability gains that scaled
predictably with compute. Around April 2024, that curve started to bend. By
September 2024 it had bent enough that OpenAI shipped a fundamentally different
kind of model — o1 — which was not bigger than GPT-4o but spent its compute on
"thinking" at inference time using reinforcement learning over verifiable
rewards (RLVR), and which beat the much bigger model on hard reasoning tasks.

The timeline is well-documented. [13] Epoch AI's Capabilities Index (ECI), a
benchmark-aggregated capability metric, shows a clean breakpoint in **April
2024**: capability progress accelerated from about 8 ECI-points/year to about
15 ECI-points/year, with a regression R² of 0.97. METR's independent measure
of "task time horizon" — how long a task can be, in human-completion-time, for
a frontier agent to complete it with 50% success — registered a sharp ~40%
acceleration around **October 2024**. [14] The April-to-October gap is
suspicious: ECI accelerated months *before* o1 was publicly announced, which
strongly implies that internal RL experimentation was already in flight at
multiple labs by spring 2024 and that the public release was the visible spike
of an underlying transition that had been brewing internally for at least
half a year.

The cleanest single piece of negative evidence for "pretraining is still the
main game" is **GPT-4.5**, released in February 2025. It was, by OpenAI's own
description, the largest pretrained model the company had ever produced. It
cost somewhere between $130 million and $1.2 billion in final-run compute. [11]
And it was reviewed, even by sympathetic observers, as a disappointment. On
several benchmarks it was *outperformed by smaller models trained with RL
post-training*, including DeepSeek's V3 (which had been released two months
earlier for a few percent of the cost). OpenAI itself stopped calling it a
"frontier model." If you believed in 2024 that pretraining was the engine and
RL was a sideshow, GPT-4.5 was the experiment that should have updated you. It
spent more compute on more parameters and got a smaller capability return than
the cheaper, smaller, RL-heavy models that surrounded it.

The clearest synthesis of what was actually happening came from a deep-dive I
ran on the apparent contradiction between (a) METR's observation that frontier
agents are still doubling their task time horizons every few months, and (b)
the equally well-documented observation that traditional benchmarks (MMLU,
GSM8K, MATH-500, HumanEval) are saturating to within statistical noise across
all top frontier models. [15] These two facts seemed contradictory until you
decompose what they're measuring. The resolution is a four-layer model:

1. **Pretraining capability** is decelerating at the frontier. GPT-4.5 is the
   evidence. Sutskever, Amodei, and (in softer language) Hassabis have all
   said so on the record, in some form, in 2025–2026. [16, 17, 18] The data
   exhaustion problem is real: Epoch AI estimates roughly 300 trillion tokens
   of usable human-generated public text remain, and the aggressive
   "overtraining" regime that current frontier labs use is plausibly already
   exhausting that stock. [19]

2. **RL post-training capability** is rising fast. The o1 → o3 → GPT-5 line,
   the DeepSeek R1-Zero ablation (which proved that pure RL on a good base
   produces dramatic reasoning gains), and the timing alignment with the
   ECI and METR breakpoints all point in the same direction. Epoch's analysis
   of reasoning compute scaling [20] suggests this trajectory has roughly 1–2
   years of fast scaling left before RL compute converges with overall
   training compute, after which the rate slows from "10x every few months"
   to "4x per year." This is a fast curve with a visible end.

3. **Harness/scaffolding capability** is rising fast in product terms but is
   *not* the driver of the METR exponential. METR ran the direct experiment in
   February 2026 (Jurkovic et al.): they tested whether sophisticated agent
   harnesses (Claude Code, OpenAI's Codex) outperformed METR's generic ReAct
   and Triframe scaffolds on the same time-horizon task suite. Claude Code beat
   ReAct in only 50.7% of bootstrap samples — statistically zero difference.
   Codex *lost* to Triframe in 85.5% of samples. [21] Whatever is producing the
   METR exponential, it is not the harness. The model itself, with more RL
   post-training, is doing the work.

4. **Cost per capability** is falling fast. This is where the Densing Law and
   the second Epoch trajectory live. It is the cleanest exponential trend in
   the entire corpus.

Once you have this four-layer picture, almost every public disagreement about
"is AI plateauing?" becomes a disagreement about which layer the speaker has in
mind. Sutskever, when he says "the age of scaling is over," is talking about
layer 1. Amodei, when he says "we are near the end of the exponential," is also
talking about layer 1. Karpathy, when he says RLVR "gobbled up the compute that
was originally intended for pretraining," is describing the transition from
layer 1 to layer 2. Altman, when he says "no wall," is dodging layer 1 and
pointing at layers 2 and 4. Hassabis, when he says "there's still plenty of
headroom there," is staking out the most bullish position on layer 1 — and his
lab's actual research portfolio (Genie + SIMA, the "infinite training loop"
described below) is a hedge in case he's wrong. They are all describing real
phenomena and the disagreement is mostly nominal.

This is the first inflection. It happened, it's done, the field has already
adjusted. Frontier capability progress is now driven by a different mechanism
than it was in 2023. Most users can't tell, because the API responses still
look like API responses and the benchmarks still look like benchmarks. But
inside the labs, the engine changed.

---

## III. The second hidden inflection: model → product, 2025–2026

The second inflection is more important and even less visible from the outside.
It is the transition from a world where the unit of release is *the model* to
a world where the unit of release is *the product*. And the data on this is
overwhelming.

Recall the headline number: across Anthropic, OpenAI, and Google in
February–March 2026, **1 of 78 releases was a new pretrained base model**. [1]
The full breakdown:

| Category | Count | %  |
|----------|------:|---:|
| (a) New base model weights         | 1  | 1.3%  |
| (b) Post-training on existing base | 16 | 20.5% |
| (c) Tool / harness / capability    | 11 | 14.1% |
| (d) Product / interface            | 23 | 29.5% |
| (e) Pricing / config / API         | 26 | 33.3% |

Strict "new base model" releases are 1.3%. Even if you generously include
post-training updates as "model releases," the total model-weight category is
22%. The other 78% is product, tooling, configuration, deprecation. The most
extreme single ratio belongs to Anthropic: in the same window, the company
shipped roughly **266 Claude Code releases against 2 model launches** — a 133:1
product-to-model ratio. [22] Anthropic in early 2026 is, in practical
release-cadence terms, a software company that occasionally publishes a model
update. The model is the substrate of the product but no longer the subject
of the release calendar.

The corporate positioning has shifted accordingly, and much faster than I
expected to find. OpenAI launched "Frontier" in February 2026 [23] —
explicitly as an enterprise agent platform competing with Salesforce,
ServiceNow, and SAP, not as a research artifact. Anthropic has been positioning
Claude through "Cowork" as an embedded knowledge worker, not a chatbot. Google
ships consumer AI features in monthly batches called "Drops," a name borrowed
from product management vocabulary. Ben Thompson at Stratechery has been
writing about this transition for the better part of a year under the heading
"SaaSmageddon" [24]: a reading of the early-February 2026 ~$730 billion drop
in SaaS market capitalization as the financial markets pricing in the moment
when frontier AI labs stopped being infrastructure providers to vertical SaaS
incumbents and started being their direct competitors. The market noticed the
transition before most observers of the AI release calendar did.

What does this mean for the cadence question? It means the cadence is now
sustained by something fundamentally different from what sustained it in 2023.
A research-driven cadence is structurally fragile: it depends on a steady
stream of new ideas, new datasets, new compute commitments, and the willingness
to keep paying for them. A product-driven cadence is structurally durable in
the way that all product cadences are durable: it persists for as long as
there is a customer base and an engineering team. The Linux kernel has been
shipping a release every 9 weeks since 2011, regardless of whether the
underlying field of operating-system research was producing genuinely new
kernel architectures (it wasn't). Chrome has been shipping a release every 4
weeks since 2021, regardless of whether browser engines were genuinely advancing
(they weren't). Apple has shipped a new iPhone every September since 2007,
regardless of whether smartphone hardware was genuinely improving (it stopped
in roughly 2018). Software product cadences can persist indefinitely after
the underlying substrate stops genuinely advancing, because the consumer-facing
function of a release is not "deliver a scientific advance" but "demonstrate
that the team is alive and the product is being maintained."

This is, I think, the actual answer to the user's question. The cadence is
sustainable in the long run not because the science is sustainable but because
the cadence has already migrated off the science and onto the product surface.
Even if pretraining progress stops cold tomorrow — and there are credible
reasons to think pretraining progress might stop cold within the next year or
two — Claude Code releases continue. Cowork features continue. Operator
upgrades continue. The release calendar continues. The metronome doesn't care
about the underlying physics, because the metronome is now a product
metronome, not a research metronome.

---

## IV. Why labs keep racing (the institutional question, with corrections)

The natural objection at this point is: yes, fine, but *why* would labs sustain
a fast cadence if the underlying science is slowing? Aren't they being driven
by something — investor pressure, IPO timelines, competitive panic?

This is where the original survey that fed this report contained a load of
rhetorical claims that turned out, when investigated against primary sources,
to be either overstated or wrong in interesting directions. I think the
corrected version is more useful than the original would have been.

The most-cited piece of "IPO panic forces cadence" evidence in 2026 has been a
Dario Amodei quote, widely paraphrased as "a twelve-month delay would make
Anthropic bankrupt." It turns out [25] that this is a misquote. The actual
Fortune interview, from February 2026, has Amodei saying: *"If I'm just off by
a year in that rate of growth, or if the growth rate is 5x a year instead of
10x a year, then you go bankrupt."* This is not a statement about competitive
release cadence pressure. It is a statement about **revenue growth-rate
forecasting risk under heavy infrastructure capex commitments**. The danger
he is describing is overbuilding compute against an optimistic revenue forecast
that does not arrive on schedule. It is a capital-allocation argument, not a
race argument. And — this is the interesting part — the corrected version is
actually a *stronger* argument for institutional cadence pressure than the
miscited version, because it locates the pressure not in competitive panic
(which is hard to verify) but in the literal accounting of long-dated capex
commitments against month-to-month revenue (which is hard to deny). Anthropic
just raised $30B at a $380B valuation, OpenAI just raised $110B at a $730B
pre-money valuation, both committed to multi-year hyperscale compute deals,
both pointing toward 2026 IPOs. [25] The bankruptcy risk is real, the math is
real, and the math says: if you do not keep growing into the curve you are
betting on, you bankrupt yourself by overbuilding. This is a much sharper
forcing function for cadence than vague "competitive pressure."

The other miscited claim worth correcting: Anthropic's Responsible Scaling
Policy v3 (February 2026) was characterized in some 2026 commentary as a
formal abandonment of the unilateral safety pause in favor of "racing into
cadence." The actual document [25] is more nuanced and more interesting. RSP v3
does drop the unilateral pause commitment, but the competitive logic it
introduces is about *matching competitor safety mitigations*, not matching
competitor release cadences. The reasoning goes: if Anthropic pauses unilaterally
and other labs do not, the global frontier rolls forward without
Anthropic's safety practices applied to it, producing a less-safe world. So
the safety commitment is now conditional on other labs' safety behavior, not
on their release timing. This is still a meaningful concession to competitive
realism — the lab founded specifically to resist racing has formally
incorporated the existence of the race into its safety policy — but the
specific causal mechanism is different from the popular characterization. RSP
v3 is a story about safety mitigation co-evolution under competition, not a
story about marketing-driven cadence acceleration.

The most interesting institutional finding in this investigation came from
the "control group" question: **Chinese frontier labs run a release cadence
that matches or exceeds US labs without any of the US-specific institutional
forces** (no IPO pressure, different VC structure, much weaker brand-investor
feedback loop). [26] DeepSeek is the cleanest case: privately funded by a
hedge fund (High-Flyer), no VC overhang, no IPO timeline, openly releasing
weights — and yet shipping at the same pace as OpenAI. Alibaba's Qwen team
shipped more individual model variants in 2025 than any single US lab. Moonshot
(Kimi) and MiniMax are accelerating. Tencent's Hunyuan is the lone counterexample
— low text-frontier cadence, which clarifies the rule by exception.

What this means is that the simplest version of the "US-IPO-pressure forces
cadence" claim is too narrow. Chinese labs face *equivalent forces in different
forms*: state prestige pressure (Xi Jinping personally endorsed DeepSeek;
Premier Li Qiang met with Liang Wenfeng directly), cloud market competition
between Alibaba and ByteDance and Tencent that mirrors the AWS/Azure/GCP race
in the US, talent and brand signaling for VC-backed startups, and the
export-control regime functioning paradoxically as a forcing function for
efficiency innovation rather than a brake on it. Liang Wenfeng's most
revealing statement, in his July 2024 interview translated by ChinaTalk [27],
is that DeepSeek's mission is "participation in the global innovation wave" —
explicitly cultural and prestige-driven, not commercial.

The deeper finding from the Chinese-lab evidence is that the Chinese frontier
is running a **dual race**: a capability frontier (matching the US labs on
benchmarks) and an efficiency frontier (the Densing-Law-like compression of
cost per capability). This maps perfectly onto the two-trajectory cost picture
from Section I: the Chinese efficiency frontier is, structurally, the
replication trajectory. DeepSeek's $5.6 million V3 run, MiniMax's $534K RL
training pipeline, Zhipu's 90% price cuts — these are not parallel runs of the
same race the US labs are running. They are a *different race*, on a *different
axis*, and that race has its own logic for sustaining a cadence.

The general principle that emerges from putting these two findings together is
something like: **release cadence emerges from any high-stakes competitive
environment with measurable public visibility, regardless of the specific
institutional form the competition takes.** The form is contingent. The
cadence is universal. Wherever you have multiple actors trying to demonstrate
leadership, with public benchmarks, with commercial or geopolitical stakes,
you get a release rhythm. The question of *whether* the rhythm sustains is
roughly equivalent to the question of whether the underlying competitive
environment dissolves — and there is no sign of that happening.

---

## V. What comes next, from the people building it

I asked one of my agents to comb the public statements of the most prominent
practitioners in 2025 and early 2026 — long-form interviews, conference talks,
year-in-review essays, the kind of material where someone has to commit to
specific claims rather than offer marketing platitudes. [28] The picture that
emerges is sharper than I expected, and the disagreements are revealing in a
specific way.

**The consensus.** There is one across roughly seven of the ten figures I
examined: the pretraining-on-internet-text era is approaching a ceiling, and
the next axis of capability progress is some flavor of *experience-based
learning* — AI that learns from doing things, from interacting with
environments, rather than from reading static text corpora. Sutskever names
this directly. Amodei names it. Karpathy is the most articulate champion of
"environments" as the next training substrate. Silver and Sutton, in their
April 2025 essay "Welcome to the Era of Experience" [29], formalized the
position: "A new generation of agents will acquire superhuman capabilities by
learning predominantly from experience." Hassabis's actual research portfolio
at Google DeepMind — the Genie 3 + SIMA "infinite training loop" where Genie
generates interactive 3D environments and SIMA learns to act in them — is the
clearest institutional bet on this view. Lample at Mistral identifies the
specific technical bottleneck: extending RL to long-horizon tasks where reward
arrives hours or days after action, which "the model is completely lost"
trying to learn from currently. The convergence is broad enough that I think
it counts as a real field-wide bet, not a fashion.

**The fault line.** Yann LeCun is the loud contrarian. In November 2025 he
left Meta after twelve years; in March 2026 he founded AMI Labs in Paris with
a $1.03 billion seed round at a $3.5 billion valuation — the largest seed
round in European startup history. [28] His public position is that LLMs are
"complete bullshit" as a path to superintelligence. His architectural
alternative is JEPA (Joint Embedding Predictive Architecture), which predicts
abstract representations rather than tokens, and which has produced V-JEPA 2 —
a 1.2-billion-parameter model trained on 1 million hours of video that achieves
state-of-the-art on physical-reasoning benchmarks. His framing argument is
that a four-year-old child has processed roughly 10¹⁴ bytes of grounded,
multimodal, interactive sensory data, while the largest LLM has processed
roughly 10¹³ bytes of static text. Language is a tiny fraction of human
experience and you cannot get to general intelligence by maximizing the
likelihood of the next word in a corpus that does not include the world. It is
the most credible and most falsifiable bet against the consensus, and AMI Labs
will either ship something within four years or not. Either outcome is
informative.

**Karpathy's productive contradiction.** This is the one I find the most
interesting. In his "2025 LLM Year in Review" post [28], Karpathy names RLVR
(Reinforcement Learning from Verifiable Rewards) as the most important
breakthrough of 2025. He credits DeepSeek-R1 as the canonical demonstration.
He describes how "RLVR turned out to offer high capability/$, which gobbled up
the compute that was originally intended for pretraining." Then, in the same
voice, in his October 2025 Dwarkesh interview, he says he is *bearish on RL
long-term*. His phrase is: *"Reinforcement learning is terrible. It just so
happens that everything that we had before it is much worse. You're sucking
supervision through a straw, because you've done all this work that could be
minutes of rollout and you're sucking the bits of supervision of the final
reward signal through a straw, and you're broadcasting that across the entire
trajectory."* This is one of the most precise critiques of RL I have seen from
any practitioner. The reward signal is too sparse and too noisy to efficiently
teach intellectual problem-solving. RL just happens to be the least-bad
mechanism the field currently has for converting compute into capability.

The productive contradiction is this: RLVR was the 2025 breakthrough *and* it
is fundamentally inadequate. Both can be true. A historical parallel: the
Wright brothers' controllable wing-warping mechanism was the breakthrough of
1903 and it was also fundamentally inadequate, and replacing it with proper
ailerons took most of a decade and was the actual sustained engineering work
that made aviation a real industry. Karpathy is saying we are at the
wing-warping stage of RL post-training: it works, it is the breakthrough, and
it is also a kludge that will be replaced by something better, and the
"something better" is interactive environments — building large, diverse,
high-quality training grounds where models can act and observe consequences,
with the consequences themselves serving as a richer-than-RL feedback signal.

**Hassabis's nuance.** Demis Hassabis is the most technically careful of the
lab CEOs and he holds the most sophisticated view I encountered. From his
February 2026 Davos interview [28]: he explicitly does not subscribe to the
LeCun "LLMs are dead end" view ("the only debate in my mind is, are they a key
component or the only component?"), but he also does not subscribe to the
"scaling solves everything" view. He thinks AGI requires "one or two more big
breakthroughs" along the lines of *continual learning* (which "has not been
cracked yet"), better memory, and world models for grounded physical
understanding. His DeepMind portfolio is a hedge across all three. Genie 3 +
SIMA is the world-models bet. The Gemini 3 series is the LLM-scaling bet. The
continual-learning research is the missing-piece bet. Hassabis is the closest
thing to a "we have a plan and the plan is a stack of bets" voice in the field
in 2026, and the plan is roughly: LLMs are the language layer, world models
are the physical-reasoning layer, continual learning gets you personalization
over time, and you organize the whole thing inside agentic product harnesses.
This is, when you read it carefully, the most internally consistent position
across any single practitioner I encountered.

**Sutskever's deliberate opacity.** Ilya Sutskever, in his November 2025
Dwarkesh interview, is explicit that the field's central unsolved problem is
*generalization*: "These models somehow just generalize dramatically worse
than people. It's super obvious. That seems like a very fundamental thing." He
is also explicit that SSI is "an age of research company" — meaning, in his
framing, that the field is no longer in an age of scaling and the next phase
will be driven by research breakthroughs rather than compute commitments. He
does not say what SSI's specific approach is. He hints, in places, at
self-play and multi-agent learning — consistent with his historical
intellectual lineage from AlphaGo. SSI has not shipped a model. The bet is
opaque and we will not know whether it pays out for several years.

**The convergence under all of this.** There is more agreement than there
looks like there is. Almost everyone — LeCun is the exception — thinks LLMs
are *part* of the answer, not the whole answer. Almost everyone thinks the
next axis of progress is some flavor of learning-from-experience, with the
specific form differing (RLVR with better algorithms, environment-based RL,
world models, self-play, multi-agent). The disagreements are mostly about
*how soon, what mechanism, what architecture*, not about *whether the
pretraining era is approaching a ceiling*. If you had to summarize the
practitioner consensus in 2026 in one sentence, it would be: *"Pretraining is
running out of room, the next thing is some form of learning from doing, and
we are not sure exactly what shape that takes, but everyone except LeCun
thinks the LLM survives as a component."*

---

## VI. The historical analogy that actually fits

The user explicitly asked about patterns from other industries. I went into
this expecting Moore's Law to be the default analogy, and the historical
analogies survey [30] confirmed it as the closest structural fit. But I want
to push the comparison harder than the survey did, because the LLM case is
not just *like* the post-Moore's-Law semiconductor era — in some respects it
is *better at sustaining a cadence* than that era was, and the difference is
the second inflection from Section III.

Consider the structural parallel. From roughly 1965 to 2005, Moore's Law and
Dennard scaling drove a clean exponential improvement in chip performance.
Around 2005, Dennard scaling collapsed: clock speeds stopped rising because
power densities became unmanageable. Around the same time, the cost of
advancing to each new lithography node started rising faster than the
performance gains it delivered — a semiconductor version of Eroom's Law that
researchers like Liso and colleagues have measured directly. [31] Intel
formally retired its tick-tock strategy in 2016, in an SEC filing, by saying
that the two-phase shrink-then-optimize cycle was being replaced by a
three-phase cycle and by the way please notice we are still going to ship a
new chip every year. [32] This is the closest single historical event to what
LLM labs are doing in 2025–2026, in spirit and in mechanism.

Three things sustained the semiconductor cadence after Dennard scaling died:
- **Multi-core**, which was a software-engineering response to a physics
  failure: stop trying to make a single core faster and put more cores on the
  die. Productivity gains became contingent on the software industry learning
  to write parallel code, which was hard and slow.
- **Specialization**, which moved progress off the general-purpose CPU and
  onto GPUs, TPUs, NPUs, ASICs. The "frontier" stopped being a single
  measurement and became a portfolio.
- **Packaging and 3D stacking**, which kept density rising even after planar
  lithography stopped delivering, by stacking chips vertically.

Each of these was a *change in what counted as a chip improvement*, and each
was packaged inside a release calendar that looked, from outside the industry,
like business as usual. Intel kept shipping new "generations" every year. The
naming kept marching forward — Sandy Bridge, Ivy Bridge, Haswell, Broadwell —
even when the underlying physics had stopped delivering big gains. Industry
insiders knew this. The rest of us mostly did not. There is a famous Anandtech
review of Skylake (2015) that captures the moment: "The pace of progress has
slowed but it's not dead, it's just different now." Substitute "frontier
LLMs" for "Intel CPUs" and you have the 2025 discourse exactly.

Now here is where I want to push the comparison further. The LLM analogy is
not just structurally similar to post-tick-tock Intel. **It is structurally
*better at sustaining a cadence*** than post-tick-tock Intel was, for one
specific reason: the LLM industry has migrated its release rhythm onto the
software product surface (Section III), and software product release rhythms
are durable in a way that hardware release rhythms are not. Intel still had
to actually fab a new chip each year. The fab cycle imposes physical
constraints — minimum yields, mask costs, validation timelines — that limit
how fast a chipmaker can ship even cosmetic releases. A software product team
faces no such constraint. Anthropic can ship Claude Code feature releases
literally every day and frequently does. The metronome for a software product
release calendar is whatever the engineering team can sustain socially and
operationally, which is essentially open-ended.

The Carlota Perez framework — the installation-versus-deployment distinction
that her work on technological revolutions made famous [33] — is the second
historical lens that maps onto this cleanly. In Perez's framing, every great
technological revolution goes through an *installation* phase where the new
technology is built out as infrastructure, characterized by intense capital
investment, frequent breakthroughs, and frothy investor enthusiasm; and a
*deployment* phase where the infrastructure is taken for granted and the
real productivity gains come from applying it to specific industries and
problems, characterized by software-product cadences and incremental
integration work. The dot-com bubble was the installation phase of internet
infrastructure; the post-2003 era of vertical SaaS was the deployment phase.
The LLM industry, in this framing, is in the middle of its
installation-to-deployment transition. The pretraining boom of 2020–2024 was
the installation phase. The current product-focused cadence is the
deployment phase. *The transition between phases is exactly when the unit of
release changes from "infrastructure capability" to "applied product feature"
— which is exactly what the data from Section III shows.*

This is a more useful framework than "Moore's Law or Eroom's Law" because it
predicts what comes next: *not* a slowdown, but a shift in the kind of
activity that a release cadence consists of. The deployment phase of every
prior technological revolution has produced decades of sustained product
release cadences after the underlying installation phase ran out of major
breakthroughs. This is why I think the answer to the user's literal question
("can the cadence really continue for a decade or two?") is: yes, almost
certainly, but the cadence ten years from now will be a cadence of a very
different kind of thing than the cadence five years ago was.

---

## VII. So what is actually happening, and where is it going

Let me try to put the whole picture in one paragraph.

The release cadence of frontier LLMs is sustained by a stack of mechanisms
that have changed over time, with each mechanism replacing the previous one
without the public-facing rhythm changing. Until early 2024 the cadence was
sustained by pretraining scale-up: bigger models, more data, more compute,
predictable capability gains. Around April 2024 that mechanism started to
fail and was replaced by RL post-training over verifiable rewards: the same
base models with much more RL applied, producing the o1/o3/R1 generation of
reasoning models. RL post-training is itself a mechanism with limited runway
— Epoch's projection is roughly 1–2 years before its growth rate slows from
"10x in a few months" to "4x per year." Sometime around mid-2025 a third
mechanism started to dominate: the model-as-product transition, in which the
unit of release stopped being the model and started being the application
built on top of the model. By February 2026 only about 1.3% of frontier-lab
"releases" are new base model weights; the rest are product features,
configuration changes, and tooling. The cadence is sustainable indefinitely
on this third mechanism because it is a software-product cadence, and
software-product cadences are, in principle, eternal. There is no wall coming
because the wall already came — twice — and the cadence routed around both
walls before most observers noticed they were there.

The strongest single piece of evidence for this picture is the
**266-to-2 Anthropic ratio** in the February–March 2026 window: for every two
"model" releases, Anthropic shipped 266 Claude Code product releases. The
strongest piece of evidence against the most pessimistic versions of this
story is the **METR time-horizon exponential**: frontier agents are still
genuinely doubling their task completion time horizons every 4–7 months [14],
which means *something* is still on a real exponential, and the scaffolding
ablation rules out the harness as that something, which means the model
itself (probably via RL post-training) is still genuinely getting more
capable. The most candid voice in the field, Karpathy, holds both of these
findings simultaneously and is right to.

The thing the user should take away from this report is that the question
"is this sustainable?" is not very productive, because it presupposes that
there is one thing being sustained. There are at least three things, they
have different sustainability profiles, they hand off to each other in
sequence, and each handoff is invisible from the outside. The question that
*is* productive is: **what is the cadence currently a cadence of, and what
mechanism is currently sustaining it?** Right now, in April 2026, it is
mostly a cadence of software product releases, sustained by the engineering
capacity of three to five companies that have decided to compete on
shipping speed and feature breadth. That can persist for a long time. Inside
the product cadence, there is still a slower frontier-research cadence
running, sustained mostly by RL post-training on frozen base models, and
that has roughly a year or two of fast scaling left before it slows. Inside
*that*, there is an even slower base-model cadence — true new pretraining
runs — that has visibly slowed and that several insiders (Sutskever, Amodei,
softer-Hassabis) think is approaching a structural ceiling.

The interesting forward-looking questions are the ones about which new
mechanism comes online next when the current mechanism (RL post-training)
runs out. The practitioner consensus is "experience-based learning,"
operationalized variously as interactive environments, world models,
continual learning, or self-play. None of these have been demonstrated at
scale yet. SSI has not shipped a model. AMI Labs has not shipped a product.
Genie 3 generates 3D worlds at 24 fps but has not yet been used to train an
agent that does something economically useful. The gap between "the
practitioner consensus is X" and "X actually works at scale" is the gap that
will determine whether the *frontier-research* cadence continues to deliver
substantive progress over the next five years, or whether the
product-release cadence becomes the entire visible field while the
research underneath enters a slow decade of figuring out what comes after
RL post-training.

I think the most likely outcome is the latter. I think the period from
roughly 2026 through 2030 will look, in hindsight, like the
"deployment-without-much-new-installation" phase of the LLM revolution: a
stretch of years during which products built on 2024–2026-era architectures
become economically dominant, the release calendar continues at the current
rapid pace, and the underlying research field is in a hard exploratory
period trying to figure out the next architecture. This is what happened to
semiconductors after 2005 (multi-core era → specialized accelerators →
chiplets → packaging, with the underlying physics in slow improvement the
whole time) and what happened to internal-combustion automobiles after 1930
(fifty years of Sloan-style annual model refreshes with no fundamental
engineering advances, then a sudden EV/autonomy paradigm shift forced by
external pressures). The LLM case will probably look more like
post-Dennard semiconductors than like post-1930 cars, because the underlying
research field is still active in a way that mechanical-engineering of
gasoline engines was not. But the basic shape — sustained product cadence
on top of a slowed research cadence — is the same.

What would prove this wrong? Several specific things. If Sutskever's SSI
ships a model in 2026 or 2027 that demonstrates a *new* scaling axis (most
plausibly self-play or multi-agent), that would be the third inflection and
would reset the picture. If LeCun's AMI Labs ships a JEPA-based system that
clearly outperforms transformers on planning or physical-reasoning tasks
within four years, the architecture story changes. If Hassabis's SIMA-in-Genie
loop produces an agent that generalizes from 3D-world training to real-world
tasks at frontier-relevant levels, world models become the new substrate. Any
of these would be a real fourth inflection, and would deserve a new essay.

Until then, my central claim stands: **the inflection point everybody has been
waiting for is in the rear-view mirror, the cadence has already routed around
two walls, and it will most likely continue to route around future walls as
they appear, by changing what the cadence is a cadence *of*.** The metronome
keeps ticking. What it ticks for keeps changing. That is the durable feature
of this kind of industry, and it is what semiconductors taught us, and we are
watching it happen again in real time, and it is genuinely surprising how
little of the public discourse has noticed.

---

## Open questions

The investigation surfaced several specific things that would be worth
returning to as follow-up research, each of which is sharp enough to be its
own task in this repo:

1. **The ECI–o1 timing gap.** Epoch's Capability Index registered its
   acceleration in April 2024; o1 was publicly released in September 2024.
   The gap implies internal RL experimentation was already in flight at
   multiple labs by spring 2024, but no one has put together a clean
   "internal timeline of how the RL paradigm shift actually happened inside
   the labs" and that history would matter for understanding how future
   paradigm shifts are likely to play out in the public timeline. *Where
   was Anthropic on RL post-training in early 2024? Where was DeepMind?*

2. **Hassabis-vs-the-pretraining-ceiling consensus.** Hassabis is notably
   more bullish on continued pretraining gains than Sutskever, Amodei, or
   Karpathy. Either Google DeepMind is sitting on internal evidence that
   pretraining still has substantial headroom (Gemini 3's reception is
   suggestive), or Hassabis is institutionally required to be optimistic,
   or the consensus on pretraining decline is more contested than this
   essay treats it. Worth a focused dive on Google DeepMind's public and
   semi-public technical statements 2024–2026.

3. **The base-vs-RL decomposition for METR's exponential.** Nobody — not
   METR, not Epoch, not the labs themselves — has published a clean ablation
   showing how much of the observed agent task time-horizon doubling comes
   from new base model weights versus RL post-training versus other
   factors. The DeepSeek-R1-Zero ablation is the closest thing, and it
   establishes that pure RL on a fixed base produces dramatic gains, but it
   does not partition the METR exponential. This is the cleanest empirical
   gap in the entire 2026 discourse.

4. **What SSI is actually doing.** Sutskever has been explicit that SSI is
   "an age of research company" with a "different technical approach,"
   and explicit that he believes the field's central unsolved problem is
   generalization. But SSI has shipped nothing and the technical approach
   is opaque. When SSI does ship something it will be one of the most
   informative single events of the late-2020s AI period.

5. **Whether environment-based RL generalizes beyond verifiable domains.**
   Karpathy's diagnosis is that RL works well in domains with fast
   verifiable rewards (math, code) and breaks down when reward arrives
   hours or days after action. The "environments as the next training
   substrate" bet is implicitly a bet that environment-based RL can be
   made to work in domains without clean verifiable rewards. As of April
   2026 there is no public demonstration that this works. The first such
   demonstration would be the third inflection.

6. **The economics of inference scaling.** Both Amodei (publicly) and the
   2024 OpenAI compute analysis (implicitly) raised the question of how
   frontier labs become profitable at scale. The model-as-product
   transition described in Section III is partly an answer — products
   monetize directly while raw API access has weak unit economics — but
   the full economic structure of a "post-cadence" frontier lab is not
   well-understood. *When the metronome is a product metronome, who pays
   for the underlying research that keeps the product substrate
   improving?* Worth its own investigation.

7. **The user-perception question.** This essay argues that the cadence
   has migrated from research to product. A clean test of that thesis
   would be to study how end-users (developers, knowledge workers,
   consumers) actually perceive the cadence in 2026 — do they notice a
   slowdown in "real" capability gains, or does the product cadence
   produce a sense of continuous progress that exceeds what the
   underlying capability layer would justify? This is a survey-research
   question, not a literature-review question.

---

## Sources

[1] Two-month inventory of frontier lab release activity (Feb–Mar 2026),
constructed from Anthropic API and Claude Apps changelogs
(`docs.anthropic.com/en/release-notes/api`,
`support.claude.com/en/articles/12138966-release-notes`), OpenAI API
changelog (`platform.openai.com/docs/changelog`), Google Gemini API
changelog (`ai.google.dev/gemini-api/docs/changelog`), and Releasebot.io
aggregate. See `notes/deep-dive-model-to-product.md` for full inventory.

[2] Cottier et al., "How much does it cost to train frontier AI models?"
Epoch AI, 2024. https://epoch.ai/blog/how-much-does-it-cost-to-train-frontier-ai-models

[3] OpenAI infrastructure commitments tracked in Epoch AI's training compute
and capex analyses, 2024–2026. See https://epoch.ai/data

[4] DeepSeek-AI, "DeepSeek-V3 Technical Report," arXiv:2412.19437 (Dec 2024).
The $5.576M figure is 2.788M H800 GPU-hours × $2/hour, both disclosed in
the technical report.

[5] Cottier et al., op. cit. The 2.4x/year frontier compute cost growth
figure is the central empirical finding.

[6] Scannell, Blanckley, Boldon, and Warrington, "Diagnosing the decline
in pharmaceutical R&D efficiency," *Nature Reviews Drug Discovery* 11
(2012): 191–200. The original Eroom's Law paper.

[7] Denain & Wu, "Final training runs account for a minority of R&D
compute spending," Epoch AI Gradient Updates, March 2026.
https://epochai.substack.com/p/final-training-runs-account-for-a

[8] Erdil et al., "Algorithmic progress in language models," Epoch AI,
2024. https://epoch.ai/blog/algorithmic-progress-in-language-models

[9] Xiao et al., "Densing Law of LLMs," *Nature Machine Intelligence* 7
(2025): 1823–1833. arXiv:2412.04315.

[10] Dario Amodei, "On DeepSeek and Export Controls," January 2025
(Anthropic essay); Dylan Patel (SemiAnalysis), "DeepSeek Debates: Chinese
Leadership On Cost, True Training Cost," Jan 31, 2025.

[11] GPT-4.5 cluster size and training duration estimated by Epoch AI from
satellite imagery and disclosed cluster scale; cost range $130M–$1.2B is
the 10th–90th percentile of their estimate.

[12] Mertens, Fischl-Lanzoni, Thompson, "Is there 'Secret Sauce' in LLM
Development?" arXiv:2602.07238 (February 2026).

[13] Frontier model release timeline 2023–2026, compiled in
`notes/survey-anatomy-of-releases.md` from Epoch AI database, lab
announcement pages, and Artificial Analysis benchmark coverage.

[14] METR, "Measuring AI Ability to Complete Long Tasks," March 2025;
follow-up notes through early 2026 at metr.org. The "task time horizon"
methodology is documented in the original paper.

[15] Resolution of the METR-vs-benchmark-saturation tension is the subject
of `notes/deep-dive-metr-vs-saturation.md`.

[16] Ilya Sutskever, Dwarkesh Patel podcast, "We're Moving from the Age of
Scaling to the Age of Research," November 25, 2025.

[17] Dario Amodei, Dwarkesh Patel podcast, "We Are Near the End of the
Exponential," February 13, 2026.

[18] Demis Hassabis, Alex Kantrowitz Big Technology Podcast interview
from Davos, February 20, 2026; Google DeepMind podcast with Hannah Fry,
December 2025.

[19] Villalobos, Sevilla, Heim, Besiroglu, Hobbhahn, Ho, "Will we run out
of data? Limits of LLM scaling based on human-generated data," Epoch AI,
2024.

[20] Josh You, "How far can reasoning models scale?" Epoch AI Gradient
Updates, May 2025.

[21] METR ablation comparing Claude Code and OpenAI Codex against METR's
generic ReAct and Triframe scaffolds, February 2026 (Jurkovic note on
metr.org).

[22] Releasebot.io aggregate count of Anthropic Claude Code releases vs.
model launches in February–March 2026 window. See
`notes/deep-dive-model-to-product.md`.

[23] OpenAI launch of "Frontier" enterprise platform, February 5, 2026.
Coverage in Machine Herald (Feb 6, 2026) and OpenAI press materials.

[24] Ben Thompson, "SaaSmageddon and the Super Bowl," Stratechery,
February 6, 2026; "Microsoft and Software Survival," February 3, 2026;
"Aggregators and AI," February 13, 2026.

[25] Verification of load-bearing claims in `notes/deep-dive-claim-verification.md`.
Dario quote: real Fortune interview Feb 14, 2026, exact wording "If I'm
just off by a year in that rate of growth, or if the growth rate is 5x
a year instead of 10x a year, then you go bankrupt." Anthropic RSP v3
text: anthropic.com Responsible Scaling Policy v3, effective Feb 24, 2026.
OpenAI/Anthropic Feb 2026 funding rounds: Bloomberg, TechCrunch, company
press releases. Meta Q4 2025 earnings press release for $115–135B 2026
capex; NYT March 12, 2026 for "Avocado" model underperformance.

[26] Chinese frontier lab investigation in
`notes/deep-dive-chinese-labs.md`.

[27] Liang Wenfeng interview in Chinese Financial Eleven, July 2024;
translated by Jordan Schneider's ChinaTalk newsletter.

[28] Practitioner statements compiled in
`notes/deep-dive-what-comes-next.md`. Key sources: Sutskever Dwarkesh
podcast Nov 25, 2025; Karpathy "2025 LLM Year in Review" blog post Dec
19, 2025 + Dwarkesh interview Oct 17, 2025 + YCombinator keynote
"Software Is Changing (Again)" Jun 2025; Amodei Dwarkesh interview Feb
13, 2026 + "The Adolescence of Technology" essay Jan 2026; Hassabis
Davos and DeepMind podcast (above); LeCun MILA keynote and AMI Labs
founding Mar 2026; Jeff Dean Latent Space Feb 12, 2026; Liang Wenfeng
ChinaTalk translation; Lample Latent Space Mar 30, 2026; Altman Big
Technology Podcast Dec 22, 2025.

[29] David Silver and Richard Sutton, "Welcome to the Era of Experience,"
Google DeepMind, April 2025.

[30] Historical analogies survey in
`notes/survey-historical-analogies.md`.

[31] Liso et al., "Eroom's law in the semiconductor industry: Cost
escalation in chip development," 2023 (cited in historical analogies
survey).

[32] Intel Corporation, 10-K filing for fiscal year 2015 (filed early
2016), formally retiring the tick-tock cadence in favor of a three-phase
process-architecture-optimization cycle. Coverage in Ars Technica, March
22, 2016.

[33] Carlota Perez, *Technological Revolutions and Financial Capital*
(Edward Elgar, 2002). The installation/deployment phase distinction is
the central organizing concept.
