# Survey: Intellectual Schools in LLM × Economics — Mapping the Landscape

## Summary

Six distinct research programs have formed around LLMs and economics, with varying levels of maturity,
institutional backing, and publishability in top journals. The landscape is clearer than it first appears:
the empirical-effects school is the safest bet for a PhD student who wants top-5 publications quickly;
the task/automation school remains the most theoretically coherent but is facing genuine empirical stress
from its own offshoots; the transformative-AI school is intellectually the most ambitious but exists
partly outside mainstream macro. Korinek is genuinely unusual in occupying positions across three of these
simultaneously, with a credibility bridge that few others have. The biggest gap in the whole landscape is
general equilibrium modeling that connects micro RCT productivity estimates to the macro questions the
growth theorists care about — that junction is largely unmapped and is where an ambitious student could
own terrain.

---

## Key Sources

### School 1: The Task/Automation School — Acemoglu, Restrepo, Autor

**Key figures:** Daron Acemoglu (MIT, Nobel 2024), Pascual Restrepo (Boston University), David Autor (MIT)

**Canonical papers:**
- Acemoglu & Restrepo, "Automation and New Tasks: How Technology Displaces and Reinstates Labor," *Journal
  of Political Economy*, 2019. (~1,781 citations on SS)
  URL: https://doi.org/10.3386/w25682
- Acemoglu & Restrepo, "Tasks, Automation, and the Rise in US Wage Inequality," *Econometrica*, 2022.
  (~368 citations)
  URL: https://doi.org/10.3386/w28920
- Acemoglu & Johnson, *Power and Progress*, PublicAffairs, 2023. (Trade book synthesizing the normative case)
- Acemoglu, "The Simple Macroeconomics of AI," NBER WP 32487, 2024. (~44 citations already)
  URL: https://doi.org/10.3386/w32487
- Autor & Thompson, "Expertise," MIT Economics working paper, 2025.
  URL: https://economics.mit.edu/sites/default/files/2025-06/Autor-Thompson-Expertise-22050620.pdf
- Autor, "The Skill Content of Recent Technological Change," *QJE*, 2003. (Foundational; ~4,484 citations)
  URL: http://papers.nber.org/papers/w8337.pdf

**Central intellectual commitments:**
- AI is best modeled as automation of specific tasks, not wholesale job elimination
- Every technology displaces some tasks and creates new tasks ("reinstatement effect")
- The labor market effect depends on the balance between displacement and creation
- Historically, robots/prior automation have been biased toward displacement, not creation
- Social outcomes depend on which direction AI goes — "wrong kind" of AI accelerates inequality

**How they are updating to LLMs specifically:**
Acemoglu's 2024 "Simple Macroeconomics" paper is the clearest statement. His argument: even if LLMs
affect many tasks, Hulten's theorem says the macro effect is bounded by (fraction of tasks affected) ×
(average productivity gain per task). Using existing empirical estimates, he calculates at most 0.66%
TFP increase over 10 years — "nontrivial but modest." He is skeptical of explosive-growth scenarios
because hard-to-learn tasks (those involving contextual judgment, tacit knowledge) will resist
automation even if easy routine tasks fall quickly. This is a deliberate intellectual counterpoint to
Korinek/Trammell.

Autor's evolution is more optimistic. His June 2025 interview distinguishes "exposure" (not intrinsically
bad) from "commodification of expertise" (bad). He is increasingly focused on how AI might democratize
access to expert-level judgment — doctors, lawyers, contractors — and is writing about "expertise" as
the relevant unit, not just tasks. His new work with Thompson (2025) pushes in this direction.

**What it is good at:**
- Precise, testable predictions about which worker groups will be displaced vs. complemented
- Connecting to inequality, wage polarization, labor share — classic labor econ questions
- Publishable in top journals using O*NET + occupational data as inputs
- Normative guidance on "steering" technology toward better outcomes

**What it systematically misses:**
- Treats AI as just another capital-biased technology shock — same framework as robotics
- The "task" unit of analysis may be wrong for LLMs, which do multi-step reasoning and knowledge
  synthesis — not just discrete tasks
- Does not engage with AGI/recursive-improvement scenarios at all; the framework breaks down if AI
  can itself generate new tasks or automate the creation of new tasks
- Largely static framework; transition dynamics are undermodeled
- Humlum & Vestergaard (2025) is a significant empirical challenge: they find very small wage
  and hours effects even with widespread adoption, which does not fit the displacement narrative
  cleanly (though could reflect slow diffusion)

**Relation to Korinek:**
Korinek has co-authored directly with this school — specifically "Governing AI to Advance Shared
Prosperity" (2021, with Acemoglu) and "AI and Shared Prosperity" (with Klinova, AIES 2021), and
"Steering Technological Progress" (with Stiglitz, 2025). His "How Innovation Affects Labor Markets:
An Impact Assessment" (2023) uses an explicit task-based framework and cites Acemoglu/Restrepo heavily.
But Korinek uses the task framework as input for welfare analysis and then extends it toward
transformative scenarios — a hybrid position. Acemoglu and Korinek agree on the normative importance
of steering AI but disagree sharply on the plausibility of explosive-growth scenarios.

---

### School 2: Transformative AI / AGI Scenarios — Korinek, Trammell, Erdil, Davidson

**Key figures:** Anton Korinek (UVA/Brookings), Philip Trammell (Oxford/GPI), Tamay Besiroglu &
Ege Erdil (Epoch AI), Tom Davidson (Open Philanthropy), Basil Halperin (MIT)

**Canonical papers:**
- Trammell & Korinek, "Economic Growth under Transformative AI," NBER WP 31815, 2023.
  URL: https://doi.org/10.3386/w31815
- Korinek & Suh, "Scenarios for the Transition to AGI," 2024.
- Korinek, Davidson, Halperin, Houlden, "When Does Automating AI Research Produce Explosive Growth?",
  Jan. 2026.
- Korinek, "Preparing for the (Non-Existent?) Future of Work" (with Juelfs), 2022.
- Korinek, "The Rise of Artificially Intelligent Agents," 2019.
- Korinek, "Valuing AGI and an Analysis of OpenAI's Capital Structure," April 2025.

**Central intellectual commitments:**
- AI may be quantitatively different from prior automation waves, potentially approaching general
  automation of cognitive labor including R&D itself
- If machines can self-replicate and self-improve, the Kaldor Facts (stable labor share, stable
  growth rate) break down — explosive growth becomes possible, wages may rise or fall depending on
  returns to scale and natural resource constraints
- The right framework is long-run growth theory (Jones, Romer, Aghion-Howitt) extended to endogenous
  AI capability accumulation, not just labor economics
- Welfare under these scenarios requires rethinking: traditional utilitarian calculus may need revision
  when labor income approaches zero
- Scenario planning, not point prediction: the uncertainty range is enormous, so policymakers need
  to prepare for multiple futures including very bad ones

**How rigorous is this work? How is it received by mainstream economics?**
More rigorous than critics often assume. The Trammell-Korinek paper is a careful Solow-style extension
with explicit assumptions; it appears in the Annual Review of Economics (by invitation). The math is
impeccable but rests on assumptions — full automation of production, full automation of R&D — that most
mainstream economists regard as speculative rather than near-term. Reception is cautious-skeptical in
standard labor/macro journals. The work is more at home in growth theory workshops, at Oxford's Future
of Humanity Institute, GovAI, Open Philanthropy, and in NBER AI-economics projects than in JLE or AER.
Korinek's institutional home bridges this: he is at the Brookings Institution, holds UVA faculty
affiliation, and is associated with INET, giving him both EA-adjacent credibility and mainstream
legitimacy.

Acemoglu's "Simple Macroeconomics" paper (2024) is explicitly a rebuttal to this school's framing,
arguing Hulten's theorem puts a ceiling on near-term GDP effects. The debate is ongoing and genuine.

**What it is good at:**
- Asking the right long-run welfare questions (who gets the gains from explosive growth?)
- Connecting AI economics to existential risk governance
- Growth accounting framework that handles nonlinear transitions
- Policy design for scenarios where labor income vanishes (redistribution, UBI, capital taxation)
- Collaborating naturally with the AI safety/governance community

**What it systematically misses:**
- No empirical traction: these papers are almost entirely theoretical
- Transition dynamics to AGI are underspecified — how do you get from current LLMs to full automation
  of R&D? The scenarios leap over the hard empirical parts
- May be disconnected from the actual LLM-economy interactions happening right now
- Vulnerable to the objection that explosive-growth conditions (fully automated R&D) require
  assumptions about AI capability jumps that are themselves deeply uncertain
- Little mechanism for how macro growth dynamics connect to micro task-level evidence from RCTs

**Relation to Korinek:**
This is Korinek's primary intellectual home. He is arguably the central figure who has made this work
"economics" rather than "speculation" — by grounding it in formal growth models, publishing in JEL
and Annual Review, and writing governance papers that connect the scenarios to concrete policy.
His personal research page lists "The Economics and Governance of Transformative AI" as his first
field of interest. His 2026 paper with Davidson et al. on when automating AI research produces
explosive growth is the current frontier of this program.

---

### School 3: The Empirical-LLM-Effects School — Brynjolfsson, Noy/Zhang, Humlum, Eloundou

**Key figures:** Erik Brynjolfsson (Stanford HAI), Shakked Noy & Whitney Zhang (MIT PhD students, now
faculty), Anders Humlum (Chicago Booth), Tyna Eloundou & Sam Manning (OpenAI, Wharton-affiliated),
Sida Peng (Microsoft Research), Danielle Li & Lindsey Raymond (MIT)

**Canonical papers:**
- Noy & Zhang, "Experimental Evidence on the Productivity Effects of Generative AI," *Science*, 2023.
  (~1,159 citations) URL: paper in Science, no OA
- Brynjolfsson, Li & Raymond, "Generative AI at Work," NBER WP 31161, 2023. (~950 citations)
  URL: https://doi.org/10.3386/w31161
- Peng, Kalliamvakou, Cihon & Demirer, "The Impact of AI on Developer Productivity: Evidence from
  GitHub Copilot," arXiv 2023. (~523 citations) URL: https://arxiv.org/abs/2302.06590
- Eloundou, Manning, Mishkin & Rock, "GPTs are GPTs: An Early Look at the Labor Market Impact
  Potential of Large Language Models," arXiv 2023. (~523 citations)
- Humlum & Vestergaard, "Large Language Models, Small Labor Market Effects," BFI WP 2025-56.
  URL: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5219933

**Central intellectual commitments:**
- Use RCTs, field experiments, or natural experiments to measure the actual productivity effects
  of LLM adoption
- Heterogeneous effects: the most consistent finding is that LLMs disproportionately help lower-skilled
  workers, compressing within-occupation productivity distributions
- Exposure analysis: classify tasks/occupations by how much of their content LLMs can do, measure
  what fraction of workers face high exposure
- The unit of analysis is typically the task-completion speed or quality, not aggregate GDP

**Key empirical findings (state of evidence, April 2026):**
- Noy/Zhang: ChatGPT raised professional writing output quality by 18%, reduced time by 40%; helped
  weaker workers most
- Brynjolfsson/Li/Raymond: customer support AI raised productivity ~15%; less experienced workers
  gained most; learning spillovers observed
- Peng et al. (GitHub Copilot): software developers completed tasks 55.8% faster
- Humlum & Vestergaard (2025): the most important challenge to optimistic narratives. Using large-scale
  Danish administrative data with ~25,000 workers across 11 LLM-exposed occupations, they find that
  despite widespread adoption (most employers encourage use, many deploy in-house models), labor market
  effects on wages and hours worked are small. The micro-level productivity gains from RCTs do not
  appear to translate into detectable aggregate wage or employment effects yet. The gap between RCT
  results and macro outcomes is the central puzzle this school now faces.

**Rising stars:**
Noy and Zhang (MIT) are the clearest rising stars — "Experimental Evidence" in *Science* with 1,159
citations is extraordinary for a working paper by early-career researchers. Humlum at Chicago Booth
has positioned himself as the serious empiricist who can access administrative data and produce
credible natural-experiment estimates (his earlier work on robot adoption won prizes). Daniel Rock
(Wharton) is building out the exposure-index methodology.

**What it is good at:**
- Publishable in top journals: Science, QJE, AER — this is the safest PhD path
- Clear causal identification (RCTs)
- Speaking the language mainstream economists trust
- Connecting to policy: productivity, inequality, worker welfare

**What it systematically misses:**
- Individual productivity experiments cannot identify general equilibrium effects (price effects,
  market structure changes, who captures productivity gains)
- Exposure indices (Eloundou et al.) classify tasks but are not causal estimates
- Does not engage with the long-run or explosive-growth scenarios at all
- The Humlum puzzle — why do micro gains not show up in wages — is unresolved
- Publication bias toward finding effects: null results from LLM productivity experiments are
  underrepresented

**Relation to Korinek:**
This school runs largely in parallel to Korinek. He has not produced RCT papers. However, his
"Generative AI for Economic Research" JEL paper (2023, lead article, 4 versions now including
AI Agents, Aug 2025) is adjacent: it argues for using LLMs as research productivity tools and maps
the use cases — a kind of auto-ethnography of the productivity effects within economics itself.
His "How Innovation Affects Labor Markets" (2023) uses a task-based framework and integrates
Brynjolfsson-adjacent framing. He reads and cites this school but does not live in it.

---

### School 4: LLMs-as-Research-Tools / "Homo Silicus" — Horton, Manning, Ludwig, Mullainathan

**Key figures:** John Horton (MIT Sloan), Benjamin Manning (MIT), Ludwig & Mullainathan (Chicago),
Ashesh Rambachan (MIT), Gary Charness (UCSB, recently deceased but influential)

**Canonical papers:**
- Horton, Filippas & Manning, "Large Language Models as Simulated Economic Agents: What Can We Learn
  from Homo Silicus?," ACM EC 2023. (~393 citations)
  URL: https://apostolos-filippas.com/papers/hs.pdf
- Ludwig, Mullainathan & Rambachan, "Large Language Models: An Applied Econometric Framework,"
  NBER WP 33344, Dec. 2024; forthcoming *Annual Review of Economics*.
  URL: https://arxiv.org/abs/2412.07031
- Korinek, "Generative AI for Economic Research: Use Cases and Implications," *JEL* 61(4), 2023.
  (Adjacent; covers LLMs as research tool)

**Central intellectual commitments:**
Two distinct sub-programs that share a name but are methodologically different:

**4a. LLMs as synthetic subjects / simulated agents (Horton's "homo silicus"):**
LLMs are trained on human-generated text and can mimic how humans would behave in economic experiments.
You can give an LLM an "endowment," a "preference profile," and scenario, then run the experiment
on LLM agents cheaply and at scale. Key claims: LLMs can replicate qualitative results of classic
experiments (ultimatum game, trust game, public goods games) with some fidelity. Use cases: pilot
studies, sensitivity analysis, generating heterogeneous-type populations.

**4b. LLMs as measurement instruments / classifiers (Ludwig-Mullainathan):**
LLMs can annotate text at scale — classifying political speeches, news articles, survey responses —
replacing expensive human coders. The crucial econometric insight of Ludwig et al. (2024/26): this
is valid for *prediction* tasks (requiring "no training leakage" — use open-source models with
documented training data) and valid for *estimation* tasks (requiring a human-coded validation
sample to debias LLM errors). Without the validation sample, LLM measurement error correlates
with covariates in ways that destroy causal inference. This paper is becoming the methodological
standard-setter for applied economists using LLMs for text analysis.

**Methodological debates:**
- The "homo silicus" approach faces deep validity challenges: LLMs don't have preferences, stakes,
  or social context. A finding that GPT-4 splits offers in the ultimatum game similarly to humans
  may reflect what LLMs *know about* ultimatum game results (in training data) rather than
  revealing anything about cognition
- The strongest version of the critique: LLMs are compressed representations of human text, so
  replicating survey findings proves they learned the finding, not that they model decision processes
- Charness and others have pushed for validation against out-of-sample behavioral data
- Ludwig et al.'s framework is more defensible precisely because it *acknowledges* these errors
  and builds a correction mechanism

**What it is good at:**
- Opening vast new data sources: all text corpora (speeches, documents, court records) become
  potentially tractable
- Dramatically lowering the cost of pre-piloting experimental designs
- Enabling hypothesis generation at scale
- Publishable in AER, REStud, JEL — especially the Ludwig-Mullainathan econometric framework

**What it systematically misses:**
- Simulated agents don't face real incentives, real stakes, or real social pressure
- No model of welfare: using LLMs as classifiers tells you about measurement, not about the
  normative implications of AI adoption
- Largely agnostic about the effects of LLMs on the labor market or broader economy

**Relation to Korinek:**
Korinek's JEL paper "Generative AI for Economic Research" is the nearest neighbor from the
transformative-AI school to this program. He provides an extensive practitioner's guide to
LLMs-as-tools for economists — writing prompts, use cases, research workflows — but does not
make the econometric contributions that Ludwig et al. make. His work is more like a practitioner
synthesis than a methodological contribution. He cites and is adjacent to Horton, but the
methodological foundations are different communities.

---

### School 5: Mechanism Design / Market Design Meets LLMs

**Key figures:** Paul Duetting (Google Research, now also Harvard CS), Vahab Mirrokni (Google),
Haifeng Xu (UChicago CS), Renato Leme (Google), David Parkes (Harvard CS/Econ)

**Canonical papers:**
- Duetting, Mirrokni, Leme, Xu & Zuo, "Mechanism Design for Large Language Models," *WWW 2024*.
  (~56 citations) URL: https://arxiv.org/pdf/2310.10826

**Central intellectual commitments:**
- LLMs introduce a new kind of principal-agent problem: when multiple advertisers or agents want
  to influence AI-generated content, how do you design an incentive-compatible mechanism?
- The "token auction" model: agents bid on tokens in a generative process; the LLM aggregates
  preferences through a distribution over token sequences; incentive-compatibility maps to
  monotonicity conditions on output aggregation
- Second-price auction design is possible even without explicit valuation functions if preferences
  are represented as LLMs over output distributions
- The market design question for AI ads, AI-generated recommendations, and AI-mediated marketplaces

**Assessment: is this a real school?**
Barely. The Duetting et al. paper is genuinely rigorous theoretical work from top CS theory people
(Google Research, UChicago CS) but it is CS-econ, not economics. The questions are real — how do
you prevent advertiser gaming of AI-generated content, how do you run auctions for AI-generated
ad copy — but the community is small and sits primarily in CS conferences (WWW, EC), not in economics
journals. There is no Acemoglu-style programmatic vision; it is scattered papers solving specific
mechanism design puzzles. David Parkes has been working at this intersection for decades
(computational mechanism design) and represents the academic home for this work, but there is not
yet a clear "school" with shared empirical commitments.

**What it is good at:**
- Technically precise: welfare analysis with LLM preferences, auction theory, strategy-proofness
- Connects to real commercial problems (ad auctions, recommendation systems)
- Potentially very high-value: the platforms where LLMs matter most are also the platforms running
  the world's largest auctions

**What it systematically misses:**
- Largely disconnected from labor market effects or growth
- No empirical tradition
- The mechanism design questions become moot if LLM providers are monopolists who just set prices
  (Korinek/Vipra's concentration argument is directly relevant)

**Relation to Korinek:**
Limited direct overlap. Korinek's "Concentrating Intelligence" paper (Economic Policy, 2025) on
market structure is the closest link — he analyzes the supply side of the LLM market, which is
where mechanism design questions become relevant. But he doesn't do mechanism design himself.

---

### School 6: Industrial Organization of AI / Economics of the AI Industry

**Key figures:** Korinek & Jai Vipra (Oxford), Rishi Bommasani et al. (Stanford HAI), scattered
IO economists (no dominant figure yet)

**Canonical papers:**
- Korinek & Vipra, "Concentrating Intelligence: Scaling and Market Structure in Artificial
  Intelligence," *Economic Policy* 40(121), pp. 225-256, Jan. 2025.
  URL: https://www.economic-policy.org/wp-content/uploads/2024/03/EcPol-2023-183.R1_Proof_hi_Korinek_Vipra.pdf
- Bommasani et al., "The Foundation Model Transparency Index," arXiv 2023. (~107 citations)
  URL: https://arxiv.org/abs/2310.12941
- "The Economics of AI Supply Chain Regulation" (Qian, Mehra & Liu, 2026) — an early attempt at
  formal IO modeling of the foundation model supply chain

**Central intellectual commitments:**
- The AI market has structural features — massive economies of scale in training, network effects
  in data, switching costs — that systematically push toward concentration
- Frontier models will tend toward monopoly or tight oligopoly; below-frontier models face intense
  competition
- Vertical integration between compute (NVIDIA, Google TPUs), foundation models (OpenAI, Anthropic,
  Google), and applications creates anticompetitive risks
- Regulatory responses: antitrust enforcement, data governance, mandatory interoperability,
  compute governance

**Assessment:**
This is the most under-developed school intellectually. The Korinek/Vipra paper is carefully argued
but is more policy analysis than formal IO theory. There is no standard IO model of the foundation
model market yet — no calibrated Cournot or Bertrand model, no formal treatment of how training data
as a production input behaves under different ownership structures. The "economics of AI chips"
literature (Wenqiang Lu, 2026) is embryonic. The field is wide open.

What *is* clear: compute is a binding constraint and is geographically concentrated (TSMC, NVIDIA);
the economics of this supply chain — market power, entry barriers, export controls as industrial
policy — is an underexplored area with real policy stakes (US-China tech competition).

**What it is good at:**
- Directly relevant to antitrust and regulation debates happening now
- Natural journals: RAND Journal of Economics, American Economic Review (IO section), Journal of
  Industrial Economics
- Could fuse with mechanism design (School 5) to ask: what auction/market structures are efficient
  for AI compute allocation?

**What it systematically misses:**
- Very little formal theory yet — mostly descriptive and policy-oriented
- Does not connect to labor market or welfare questions yet
- No empirical tradition comparable to classic IO (no datasets on foundation model production costs)

**Relation to Korinek:**
This is the third school Korinek inhabits directly. The Korinek/Vipra paper is one of the few
economics-journal papers doing real IO analysis of the AI industry. His "Intelligent Financial
System" paper with BIS coauthors (Journal of Financial Stability, 2025) extends this to financial
sector concentration. This is a place where Korinek has a near-monopoly on credible economics
work and where a student working with him could genuinely define the field.

---

## Landscape Assessment

### Where Korinek Sits and What He Bridges

Korinek is the rare figure who inhabits three schools simultaneously with publications in each:

1. **Transformative-AI school** — central figure; his and Trammell's NBER paper is the canonical
   formal statement; his new 2026 paper with Davidson on explosive growth from AI R&D automation
   is the current frontier
2. **Task/automation school** — bridge figure; has co-authored with both Acemoglu and Stiglitz
   using task-based frameworks; his "Steering Technological Progress" (with Stiglitz) is a
   contribution to this school's normative program
3. **IO of AI school** — co-founder with Vipra; the Korinek/Vipra paper is currently the
   main reference in this niche

He is **adjacent** to the empirical-effects school (his JEL paper uses and synthesizes this work but
doesn't contribute RCT evidence) and to the LLMs-as-tools school (his JEL paper IS this in practitioner
form, but Ludwig-Mullainathan do the methodological contribution). He has **no presence** in mechanism
design/market design for LLMs.

The bridging function is Korinek's real intellectual value. No one else has published simultaneously in
growth theory, normative labor economics, AI governance, and IO of AI. The risk is being spread thin;
the opportunity is being the synthesizer who can see across all these programs.

### Which School Is "Safest" for a PhD Student

**Safest (top-5 publishable, low variance):** School 3, empirical-effects. Noy/Zhang published in
*Science* as PhD students. Brynjolfsson papers go in QJE and AER. Humlum's work is Chicago Booth
standard. The methodology is RCT or natural experiment, the datasets are accessible (Danish admin data,
GitHub logs, customer support records), and the questions are clearly defined. Rising star count is
highest here. Downside: it is crowding up fast; by 2027 there will be hundreds of these papers and the
field will face a "what have we learned overall?" synthesis problem.

**Safe-ish with higher upside:** School 1, task/automation theory. The models are tractable, the
O*NET-based empirics are publishable in top journals, and you're working within a Nobel-laureate's
program. Downside: Acemoglu's framework may not adequately capture what LLMs actually do (they are
not just task automation); the theoretical conversation may stall. And Acemoglu himself is now doing
the macro extensions, leaving less space for PhD students on the theory side.

**Higher-risk, higher-upside:** School 6, IO of AI. Almost no one is here doing real economics. If
you can bring standard IO tools (dynamic oligopoly, entry and investment models, two-sided markets)
to the foundation model industry, you will own the field. The data challenges are real (training costs
are not publicly disclosed), but industry relationships or public compute/revenue data may suffice.

**High-risk, possibly very high upside:** School 2, transformative AI. The papers are in Annual Review,
NBER, Nature Communications — not AER or QJE. Mainstream macro departments remain skeptical. If AGI
arrives soon, these papers will have enormous impact; if not, they will look like educated speculation
from a distance. Career risk for a student at a non-Korinek institution is real.

**Specialist niche:** School 4 (LLMs as tools/econometrics). Ludwig-Mullainathan have closed much of
the space. A student who can extend their framework to specific data contexts (text-as-data, experimental
design) has a clear path, but it is methodological rather than substantive economics.

### Which Schools Are Growing Fastest

By citation trajectory (2023-2026):
1. School 3 (empirical effects): fastest growth, most papers, widest adoption
2. School 4 (LLMs as research tools): fast growth driven by adoption; Ludwig-Mullainathan paper is
   becoming a methodological standard
3. School 1 (task model): steady, anchored by Acemoglu/Autor's existing citation base, but LLM-specific
   papers are slower to accumulate
4. School 2 (transformative AI): moderate growth, mostly within policy/governance circles and less in
   econ departments
5. School 6 (IO of AI): small base but growing; Korinek/Vipra has traction in policy discussions
6. School 5 (mechanism design): slowest in economics terms, strongest in CS theory

Grants and hiring: Schools 3 and 4 are getting the most NBER and NSF funding for "AI and economics"
projects. The Census Bureau's research partnerships increasingly focus on School 3 questions. School 2
is funded primarily through private foundations (Open Philanthropy, GPI) and does not generate
traditional academic labor market placements at the same rate.

### Where the Theoretical Gaps Are

**The biggest gap:** Connecting micro-level RCT findings (Schools 3) to macro welfare and growth
implications (School 2). Humlum's result — widespread LLM adoption with small aggregate labor market
effects — is deeply puzzling from both frameworks. The task model (School 1) predicts visible wage
compression at least in exposed occupations; School 2 predicts either explosive growth or fast transition.
Neither framework explains "lots of adoption, small measured aggregate effect." A theorist who could
build a model of transition dynamics that explains the Humlum result while remaining consistent with the
micro productivity gains would own a major intellectual position.

**Second gap:** IO model of the foundation model market. No one has written the canonical Cournot/Bertrand/
dynamic investment model of frontier AI development with calibrated parameters. This is a tractable
theoretical problem (if you can get cost data) and directly policy-relevant.

**Third gap:** Welfare analysis under extreme labor income decline. Korinek/Juelfs (2022) sketch the
optimal planner's solution, but there is no full general equilibrium model connecting capital taxation,
redistribution, and growth dynamics when the labor share approaches zero. This is the "second half" of
the transformative-AI research program that has not been written.

**Fourth gap:** The economics of AI safety as a public good. Frontier AI development generates safety
externalities. There is no formal public economics of this — no Pigouvian tax model, no public goods
provision model — analogous to what environmental economics built for pollution. Korinek has gestured
at this in governance papers but not formalized it.

### Surprises

- Acemoglu's 2024 "Simple Macroeconomics" paper is a more direct rebuttal to the transformative-AI
  school than is widely recognized. It is essentially saying: I grant you the task-level evidence;
  here is the ceiling on aggregate effects. The debate between Acemoglu and Korinek is live and
  substantive, not just about priors.
- The Humlum (2025) paper may be the most important empirical contribution of the year and is
  underappreciated. The finding that ~25,000 workers in 11 LLM-exposed occupations show small
  labor market effects *despite* widespread adoption is a genuine puzzle that nobody has explained.
- Autor in 2025 is actually fairly optimistic about AI democratizing access to expert-level judgment —
  he's moved away from his earlier more pessimistic framing. The task school is not uniformly gloomy.
- Ludwig-Mullainathan's 2024/26 econometric framework paper is quietly becoming a methodological
  standard. The key insight (validation sample requirement; training leakage invalidates prediction
  use cases) is genuinely useful and likely to be cited in every applied LLMs-as-tools paper going
  forward.
- The mechanism design school (School 5) is almost entirely absent from economics departments —
  it lives in CS conferences. This may change, but right now it is not where economists are.

---

## Source URLs

- Acemoglu & Restrepo (2019): https://doi.org/10.3386/w25682
- Acemoglu & Restrepo (2022): https://doi.org/10.3386/w28920
- Acemoglu, "The Simple Macroeconomics of AI" (2024): https://doi.org/10.3386/w32487
- Acemoglu & Johnson, "The Wrong Kind of AI" (2019): https://doi.org/10.3386/w25682
- Autor, "The Skill Content of Recent Technological Change" (2003): http://papers.nber.org/papers/w8337.pdf
- Autor on Labor Market (interview, 2025): https://www.socialsciencespace.com/2025/06/david-autor-on-the-labor-market/
- Trammell & Korinek, "Economic Growth under Transformative AI" (2023): https://doi.org/10.3386/w31815
- Korinek research page: https://www.korinek.com/research
- Korinek, "Generative AI for Economic Research" (JEL 2023 + updates): https://www.aeaweb.org/articles?id=10.1257%2Fjel.20231736
- Korinek & Vipra, "Concentrating Intelligence" (2025): https://www.economic-policy.org/wp-content/uploads/2024/03/EcPol-2023-183.R1_Proof_hi_Korinek_Vipra.pdf
- Noy & Zhang, "Experimental Evidence on Productivity Effects of GenAI" (Science 2023): DOI in Science (closed access)
- Brynjolfsson, Li & Raymond, "Generative AI at Work" (2023): https://doi.org/10.3386/w31161
- Peng et al., "Impact of AI on Developer Productivity / Copilot" (2023): https://arxiv.org/abs/2302.06590
- Eloundou et al., "GPTs are GPTs" (2023): arXiv 2303.10130
- Humlum & Vestergaard, "Large Language Models, Small Labor Market Effects" (2025): https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5219933
- Horton, Filippas & Manning, "Homo Silicus" (2023): https://apostolos-filippas.com/papers/hs.pdf
- Ludwig, Mullainathan & Rambachan, "LLMs: An Applied Econometric Framework" (2024/26): https://arxiv.org/abs/2412.07031
- Duetting et al., "Mechanism Design for LLMs" (2024): https://arxiv.org/pdf/2310.10826
- Bommasani et al., "Foundation Model Transparency Index" (2023): arXiv 2310.12941
