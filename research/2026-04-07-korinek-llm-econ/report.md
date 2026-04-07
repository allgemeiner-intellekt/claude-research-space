# Korinek and the LLM × Economics frontier
### A lunch-break field guide for an MSc student

Anton Korinek (his name has two R's, no E's — Anton **Korinek**, University of
Virginia) is the person mainstream economics lets go furthest out on the
"what if AI becomes very big very fast" limb without being dismissed as a
crank. That is roughly his entire role in the field. His best-known work is
not a clever identification strategy or a landmark empirical paper; it is a
*bridge* — between the frontier AI labs, the global-priorities / longtermist
community, and the normal econ profession — and bridges, in economics, are
strangely rare. Almost no other tenured economist can walk into Brookings, the
IMF, Anthropic's advisory council, and an *Annual Review of Economics* editorial
meeting in the same week without raising eyebrows. Korinek can.

The single most important thing to understand about him is that his formal
theoretical output on AI — which is narrower than his public profile suggests —
is essentially an update of a very old Malthusian intuition: land was once the
binding constraint on growth, then labour was, and AI is the first technology
in history that could make labour itself *reproducible* and therefore no longer
binding. Everything else he has written follows from taking that thought
seriously enough to write down a model of it. Whether you find this exciting
or absurd is a good early test of whether a Korinek-style PhD would suit you.
Daron Acemoglu — the gravitational centre of mainstream labour-AI economics —
finds it absurd, and has said so, politely, in equations [1,2].

The most surprising finding of this investigation is not about Korinek at all.
It is that **Lindsey Raymond is joining MIT in 2026 as an assistant professor
with a joint appointment in Economics, EECS, and the Schwarzman College of
Computing** [5]. For a student starting a PhD in 2027, this timing borders on
the ridiculous: she will literally be spinning up her lab the year you apply,
she already has *the* defining empirical LLM-and-work paper (the call-centre
copilot study in the *QJE* [6]), and her joint appointment is the exact
institutional structure that didn't exist five years ago for someone who wants
to do both economics and LLM-native research. If you were going to take one
concrete action from this report, it would be: add her name to the top of
your list now, and watch MIT's admissions for 2027.

---

## What's actually innovative in Korinek's work

Korinek's AI-economics output splits cleanly into four tracks. Keeping them
separate matters, because the policy version of Korinek you meet in a TED
talk is doing something very different from the working-paper version.

**Track 1 — Formal growth theory under transformative AI.** This is the load-
bearing academic work. The flagship is the 2024 NBER paper *Scenarios for the
Transition to AGI* with his student Donghyun Suh [3], building on a 2023
*Annual Review of Economics* typology with Philip Trammell [4]. The machinery
is standard growth theory (task-based production, capital accumulation,
automation frontiers), but the move that makes it interesting is
embarrassingly simple: he asks what happens if the complexity of human tasks
is *bounded*. Every other labour-AI model implicitly assumes humans always
retain some comparative-advantage tail — AI automates the easy tasks, workers
climb up to harder ones, and wages rise. Korinek takes the cap seriously.
Once AI catches the top of the distribution, workers don't climb anywhere;
their wages collapse. More striking still: in his simulations, **wages can
collapse well before full automation** — roughly when around 80% of tasks are
automatable, because capital can't accumulate fast enough to keep labour
productive in the residual tasks. This is a non-obvious theoretical result
and the main reason the paper is worth reading. Small literature, only ~40
citations so far, but high per-citation weight.

**Track 2 — Normative theory of steering innovation.** With Joseph Stiglitz,
a series of papers argues that markets systematically misdirect R&D (too much
labour-replacing automation, too little labour-augmenting innovation) and that
public policy should actively *steer* technical progress rather than treat its
direction as exogenous [7]. This is interesting in the way Stiglitz papers are
usually interesting — big, synthetic, normatively ambitious, and dismissed as
"too activist" by market-friendly economists. It's not where the novel math
lives.

**Track 3 — Industrial organisation of the AI industry itself.** With Jai
Vipra, *Concentrating Intelligence* (2024, *Economic Policy*) [8] is one of
the few real economics papers on the market structure of foundation models.
Korinek and Vipra document why compute, data, and talent all push toward
oligopoly, and what the resulting rents and policy implications look like.
This track is the most *empirically uncrowded* part of his agenda. If you
wanted to write a dissertation with a Korinek-ish sensibility but on unpicked
ground, the IO of AI is probably where you'd start.

**Track 4 — Practitioner guides for economists using LLMs.** The famous *JEL*
survey paper *Generative AI for Economic Research* [9], now on its fourth
update, is a field guide — prompts, use cases, cautions — not a research
contribution. It aged surprisingly well (the categories of use are still the
right categories), but it is read as a reference, not cited as a theoretical
foundation. Treat it like the friendly handout it is.

**What is *not* innovative, honestly.** The Malthusian framing itself is old
(Hanson, Nordhaus, Aghion have all worked similar ground). The policy writing
is advocacy, not discovery. The scenario analysis is valuable precisely
because nobody else in mainstream econ will do it, but it is not a new method.
Korinek's comparative advantage is not technique; it is *willingness to take
strange futures seriously in a journal Acemoglu will read*. That is a real
and scarce skill, but name it honestly.

**Does he take PhD students?** Yes — UVA is his primary home (he has been a
full professor there since 2021), and he currently advises around five PhD
students, with Donghyun Suh, co-author of the AGI paper, his most recent
graduate. He also launched **EconTAI** at UVA in September 2025 as a dedicated
research initiative with PhD RAs. UVA Economics sits around the 25-30 range
nationally — perfectly respectable, not top-five. If you want Korinek
specifically as your supervisor, UVA is the correct door; his Brookings,
NBER, Stanford DEL, and Anthropic affiliations are network assets, not
admissions paths.

---

## How the field is actually organised

Before meeting the other rising stars, you need the map. The LLM-economics
world is roughly six "schools" — they cite each other but don't really agree
on what the object of study *is*. Picking a supervisor is mostly picking a
school.

1. **The task-automation school** (Acemoglu, Restrepo, Autor). The oldest and
   most theoretically mature. Models AI as automating specific tasks and asks
   what that does to wage distributions. Acemoglu's 2024 *Simple Macroeconomics
   of AI* [1] is the canonical "calm down" paper: applying Hulten's theorem,
   he concludes LLM automation can contribute *at most* ~0.66% to TFP over a
   decade. This is also, transparently, a rebuttal to Korinek's school.

2. **The transformative-AI / AGI scenarios school** (Korinek, Trammell,
   Davidson, Erdil). Korinek's home. Rigorous growth theory applied to the
   long tail of AI outcomes. Publishes in *Annual Review of Economics* and
   NBER but not (yet) in top-five general-interest journals. Intellectually
   adjacent to Open Philanthropy, GovAI, and the EA-longtermist world.
   Reception from mainstream labour econ is polite scepticism.

3. **The empirical LLM-effects school** (Brynjolfsson, Raymond, Li,
   Noy & Zhang, Humlum). The safest, most publishable path. RCTs and
   administrative-data studies of what actually happens when real workers get
   real LLMs. The landmark paper is Noy & Zhang in *Science* (2023) — writers
   using ChatGPT were 37% faster and lower-skill workers gained the most [10]
   — and the most current controversy is **Humlum & Vestergaard's Danish
   puzzle**: nationwide data on 25,000 workers show large within-occupation
   productivity gains but *tiny* aggregate effects on hours and wages [11].
   That gap — "everyone's adopting it but nothing moves in the macro data" —
   is currently the most interesting unsolved problem in the whole field.

4. **LLMs-as-research-tools school** (Horton, Manning, Ludwig & Mullainathan).
   Two distinct sub-cults: Horton's *homo silicus* programme uses LLMs as
   simulated human subjects in economic experiments [12]; Ludwig–Mullainathan–
   Rambachan (forthcoming *Annual Review of Economics*) are quietly writing
   the methodological rulebook for when LLM-based text analysis is trustworthy.
   Validity is contested — if GPT-4 has memorised the Ultimatum Game
   literature, its "choices" tell you nothing about humans.

5. **Mechanism design for LLMs** (Duetting, Parkes, Mirrokni). Barely
   exists yet in economics. Lives in CS conferences. Ignore for now unless
   you're already a theorist.

6. **IO of the AI industry** (Korinek & Vipra, Bommasani). The most wide-open
   territory on the map. No calibrated structural model of the foundation-
   model market exists yet. If you want your PhD to plant a flag somewhere
   nobody has planted one, this is the place.

Korinek is unusual in that he touches 1, 2, and 6 — and writes practitioner
guides for 3 and 4. That bridging is genuinely rare, and it is also why his
work feels somehow bigger than the narrow count of his theorems would
suggest.

---

## The rising-star supervisor roster

With the schools in mind, here are the people who — unlike Acemoglu, Autor,
and Brynjolfsson — are junior enough to still be building labs and hungry for
students, and who are unambiguously working on LLMs (not "AI" in the abstract).

### Tier 1 — apply here first

**Anders Humlum** — *Chicago Booth, assistant professor (~6 years out of
Princeton)*. The strongest early-career empiricist in the field. He has
effectively a monopoly on Danish administrative data, which lets him ask
questions nobody with US data can ask, and his willingness to publish findings
that cut against the hype ("Large Language Models, Small Labor Market Effects"
was the original title) signals real intellectual independence. He is going
up for tenure around 2027–2028, which means the next 1–2 years is *exactly*
when he needs productive RAs and students. Booth has a strong econ PhD.
School 3. **Timing: ideal.** [11]

**Lindsey Raymond** — *MIT, incoming assistant professor 2026, joint
appointment Economics / EECS / Schwarzman College of Computing*. I said it
above: this is the luckiest structural alignment in the whole field for
someone starting in 2027. Her *Generative AI at Work* (with Brynjolfsson and
Li) is the most important empirical paper on LLMs and real workplaces to
date [6]. The joint appointment is the first of its kind. Apply to MIT
Economics. **Timing: extraordinary.** [5]

**John Horton** — *MIT Sloan, newly tenured 2023*. The person whose research
agenda is most *his own* — nobody else invented "homo silicus", and whether
it works or not is one of the real open questions in the field. Experimental,
computational, methodologically brave. Supervises through the Sloan
Management PhD programme (which is econ-adjacent and places students in
good econ departments). School 4. [12]

### Tier 2 — strong, depending on what you want to do

**Lukas Althoff** — *Stanford Economics, assistant professor (~4–5 years
out)*. A surprise. Primarily known as a labour/economic-history economist
(he has a QJE paper on Jim Crow), but he has recently pivoted into AI with
a structural general-equilibrium model of task-level effects — a full
quantitative macro model with a public GitHub repo [13]. Very few people in
the field have that level of structural econometrics chops pointed at LLMs.
Stanford Econ. School 1/6. Early, uncrowded, Stanford.

**Pascual Restrepo** — *Yale, associate professor*. Acemoglu's former student
and co-builder of the entire task-based automation framework. If you want to
do *theory* on the economics of automation — the actual math, not empirics —
this is the strongest option below Acemoglu himself. Less LLM-specific than
the tier 1 names; he thinks in abstractions. School 1, drifting toward 2.

**Daniel Rock** — *Wharton OID, assistant professor*. The measurement-and-
exposure person. Co-authored *GPTs are GPTs* (the 80%-of-workers-are-exposed
paper [14]). Wharton is elite. AI2050 Early Career Fellow. Good fit if you
love large-scale data, taxonomies of work, and labour-market measurement.

### Tier 3 — worth a conversation

**Kevin Bryan** (Toronto Rotman) — innovation theory and AI governance, more
IO-flavoured, strong Canadian option. **Andrey Fradkin** (BU Questrom) —
tenured but currently on leave at Amazon; better as a committee member.
**Emma Harrington** (UVA) — flagged in your original list, but her research
is actually on remote work, not LLMs; tangential.

### Watch list — not supervisors yet

**Benjamin Manning** (MIT Sloan PhD) and **Shakked Noy** (MIT Economics PhD)
are both advanced PhD students whose job-market placements in 2025–2026 will
matter. If either lands at a good department, they become top-tier targets
for a 2027+ PhD cohort. Noy's *Science* paper and Manning's Horton
collaborations already put them ahead of most of the junior field.

### Do not bother for this purpose

**Tyna Eloundou** is at OpenAI, not a university — not a PhD supervisor.
**Sarah Eichmeyer** (on your original list) is actually at Bocconi and works
on health and political economy, not LLMs; the name was a dead end. The big
names — Acemoglu, Brynjolfsson, Autor, Mullainathan — will technically
supervise students, but you should assume roughly 20 minutes of their
attention per semester.

---

## A concrete recommendation

If I had to condense this report into one actionable line: **Humlum now,
Raymond next, Korinek as a bridge**. Apply to Booth for 2027 entry with
Humlum as a named interest; monitor MIT's 2027 admissions cycle for Raymond's
new group; consider UVA only if Korinek's *particular* scenario-analysis
sensibility is exactly what you want to do — because that is what you will
get there, and not the more publishable mainstream empirical work that would
get you placed in a top-ten department after graduation.

The harder meta-question — which camp? — probably comes down to temperament.
School 3 (empirical LLM effects) is the safest bet for a top-five-journal
career and will feel the most like "real economics" as you learned it in your
MSc. School 2 (Korinek's camp) is the most intellectually exciting if you are
willing to accept that the work will be read more by policymakers and
longtermists than by labour economists, and that some of your papers will be
dismissed as speculative by people whose respect you were raised to want.
School 6 (IO of the AI industry) is where an ambitious student could, in
principle, define a research agenda from scratch — at the cost of having
almost no senior mentors. Pick the trade-off that matches how you want to
spend a decade of your life.

One last note on Korinek specifically. The tension between him and Acemoglu
is not just a disagreement about AI capabilities. It is a disagreement about
what economics is *for*. Acemoglu's view is that economics should model what
we can see and measure, and that writing papers about AGI transitions is
essentially science fiction. Korinek's view is that if transformative AI is
even a 10% possibility within the careers of today's policymakers, refusing
to model it is professional negligence. Both men are completely serious.
Neither can be refuted by the other until the future actually happens.

If that argument makes you feel something, you have already chosen a side.

---

## Open questions

These are the specific threads this report could not fully resolve, each
sharp enough to be its own future research task in this repo:

1. **The Humlum puzzle.** Why do Danish administrative data show such muted
   aggregate labour-market effects despite widespread ChatGPT adoption? Is
   this a slow-diffusion story, a measurement story, or a ceiling-on-gains
   story? This is the most important unsolved empirical question in the
   field right now, and nobody has a good answer.

2. **Has anyone actually *validated* homo silicus?** Horton's simulated-agent
   programme rests on the claim that LLMs reproduce human experimental
   behaviour well enough to be useful. What is the current state of the
   evidence — and does it survive once you restrict to experimental protocols
   published after GPT-4's training cutoff?

3. **Korinek's UVA PhD cohort.** Where are his recent students actually
   placing? Donghyun Suh is the only name that surfaced. A study of the last
   3–5 years of UVA econ placements from Korinek's advisees would tell you
   far more about the UVA-vs-Booth-vs-MIT decision than any abstract ranking.

4. **The econometric-textbook version of the Ludwig–Mullainathan–Rambachan
   rules.** These are reportedly becoming the methodological standard for
   LLM-assisted empirical economics, but I did not read the draft itself.
   What exactly do they say, and how binding are the constraints on working
   applied papers?

5. **A structural IO model of the foundation-model market.** Korinek & Vipra
   is descriptive; nobody has written the calibrated model. What are the
   obstacles — data, identification, or just nobody has done it yet? This is
   genuinely the most tractable "plant your flag" dissertation topic I came
   across.

---

## Sources

1. Acemoglu, D. (2024). *The Simple Macroeconomics of AI*. NBER Working Paper
   32487. https://www.nber.org/papers/w32487
2. Acemoglu, D. & Restrepo, P. (2019). *Automation and New Tasks: How
   Technology Displaces and Reinstates Labor*. *Journal of Economic
   Perspectives* 33(2).
3. Korinek, A. & Suh, D. (2024). *Scenarios for the Transition to AGI*. NBER
   Working Paper 32255. https://www.nber.org/papers/w32255
4. Korinek, A. & Trammell, P. (2023). *Economic Growth under Transformative
   AI*. *Annual Review of Economics* 15.
5. Raymond, L. Academic homepage and Stanford DEL profile.
   https://www.lindseyrraymond.com/ ·
   https://digitaleconomy.stanford.edu/person/lindsey-raymond/
6. Brynjolfsson, E., Li, D. & Raymond, L. (2025). *Generative AI at Work*.
   *Quarterly Journal of Economics*, forthcoming.
7. Korinek, A. & Stiglitz, J. (2025). *Steering Technological Progress*.
   Working paper.
8. Korinek, A. & Vipra, J. (2025). *Concentrating Intelligence: Scaling and
   Market Structure in Artificial Intelligence*. *Economic Policy*.
9. Korinek, A. (2023, updated 2025). *Generative AI for Economic Research:
   Use Cases and Implications for Economists*. *Journal of Economic
   Literature* 61(4). https://www.aeaweb.org/articles?id=10.1257/jel.20231736
10. Noy, S. & Zhang, W. (2023). *Experimental Evidence on the Productivity
    Effects of Generative Artificial Intelligence*. *Science* 381.
11. Humlum, A. & Vestergaard, E. (2025). *Still Waters, Rapid Currents: Early
    Labor Market Transformation under Generative AI*. NBER WP 33777. Earlier
    version: *Large Language Models, Small Labor Market Effects*. BFI Working
    Paper. https://www.andershumlum.com/research
12. Horton, J. J. (2023). *Large Language Models as Simulated Economic
    Agents: What Can We Learn from Homo Silicus?* NBER WP 31122.
13. Althoff, L. & Reichardt, H. (2026). *Task-Specific Technical Change and
    Comparative Advantage*. Working paper. https://lukasalthoff.com/ ·
    https://github.com/lukasalthoff/ai_labor_markets
14. Eloundou, T., Manning, S., Mishkin, P. & Rock, D. (2023). *GPTs are GPTs:
    An Early Look at the Labor Market Impact Potential of Large Language
    Models*. arXiv:2303.10130.
15. Korinek, A. Academic homepage: http://korinek.com/
16. Korinek, A. *EconTAI* initiative, University of Virginia, launched
    September 2025.
