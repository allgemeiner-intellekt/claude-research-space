# Deep Dive: What Do Senior Practitioners Actually Say About What Comes Next?

## Question

In 2025-2026, what do named senior practitioners at leading AI labs actually say about the status of pretraining and what the next paradigm looks like? What is the concrete list of candidate "next paradigms," who champions each, and what is the strongest argument for each?

## What Was Searched

Primary sources accessed: Ilya Sutskever's Dwarkesh Patel interview (Nov 25, 2025); Andrej Karpathy's "2025 LLM Year in Review" blog post (Dec 19, 2025), his Dwarkesh interview "AGI is Still a Decade Away" (Oct 17, 2025), and his YCombinator "Software Is Changing (Again)" keynote (Jun 2025); Dario Amodei's Dwarkesh interview "We Are Near the End of the Exponential" (Feb 13, 2026) and essay "The Adolescence of Technology" (Jan 2026); Demis Hassabis interviews with Alex Kantrowitz (Feb 20, 2026 at Davos) and the Google DeepMind podcast with Hannah Fry (Dec 2025); Yann LeCun's departure from Meta and AMI Labs founding (Nov 2025 / Mar 2026); Liang Wenfeng interview translated from Sina Finance (Feb 2025); Jeff Dean on Latent Space (Feb 12, 2026); Guillaume Lample on Latent Space (Mar 30, 2026); Sam Altman interview (Dec 22, 2025); David Silver / Richard Sutton "Welcome to the Era of Experience" (Apr 2025); Etched $500M raise news (Jan 2026); Genie 3 blog post from Google DeepMind (Aug 5, 2025); DeepSeek-R1 paper (Jan 2025).

---

## Section A: Named Practitioners — Latest 2025-2026 Statements

### 1. Ilya Sutskever — "We Are Squarely an Age of Research Company"

**Source:** Dwarkesh Patel podcast, "We're Moving from the Age of Scaling to the Age of Research," Nov 25, 2025.

This is the most consequential public statement from Sutskever since the Reuters quote that made waves in November 2024. He elaborates considerably.

On pretraining's limits: "At some point though, pre-training will run out of data. The data is very clearly finite." He does not claim pretraining is already exhausted but frames it as a hard ceiling that the field is approaching.

On what he sees as the core unsolved problem: "These models somehow just generalize dramatically worse than people. It's super obvious. That seems like a very fundamental thing." This is his diagnosis — pretraining produced impressive but brittle generalization, and the field has not cracked why human intelligence generalizes so robustly.

On the new era: "We are back to the age of research again, just with big computers." And more directly: "We are squarely an 'age of research' company." SSI, in his framing, is not a scaling company. It is a research company that happens to use large-scale compute.

On what SSI is specifically doing: "The main thing that distinguishes SSI is its technical approach. We have a different technical approach that I think is worthy." He deliberately withholds specifics. The section header from Dwarkesh's timestamp reveals he believes self-play and multi-agent are important vectors — consistent with his thinking at OpenAI, where he was a key champion of self-play as a path to superhuman capability (as in AlphaGo and early OpenAI work).

On timeline: When asked about reaching human-like learning systems, he said "I think like 5 to 20." Years.

**Assessment:** Sutskever is the strongest public voice for the view that pretraining has a fundamental architectural ceiling unrelated to data quantity. He believes generalization is the unsolved problem and that cracking it requires research-driven breakthroughs, not just scale. His bet appears to be on self-play/multi-agent approaches, though he remains deliberately opaque.

---

### 2. Andrej Karpathy — "RL Is Terrible But Better Than What Came Before; Environments Are the Real Next Thing"

**Sources:** "2025 LLM Year in Review" blog (Dec 19, 2025); Dwarkesh podcast "AGI is Still a Decade Away" (Oct 17, 2025); YCombinator keynote "Software Is Changing (Again)" (Jun 2025); X posts (Aug–Oct 2025).

Karpathy is the most candid senior practitioner in the field. He is also internally inconsistent in the right ways — he identifies genuine tensions in his own views.

**On RLVR as the 2025 paradigm shift:** In his year-in-review, Karpathy marks Reinforcement Learning from Verifiable Rewards as the most important development of 2025. "Unlike the SFT and RLHF stage, which are both relatively thin/short stages (minor finetunes computationally), RLVR involves training against objective (non-gameable) reward functions which allows for a lot longer optimization." He credits DeepSeek-R1 as the canonical demonstration. Critically: "Running RLVR turned out to offer high capability/$, which gobbled up the compute that was originally intended for pretraining."

**On benchmarks collapsing as signal:** "Training on the test set is a new art form." He no longer trusts benchmarks because RLVR creates models that are explicitly trained against verifiable environments adjacent to benchmark distributions. "His trust in benchmarks has collapsed accordingly. What does it look like to dominate every benchmark without achieving AGI? Apparently, it looks like 2025."

**On RL being terrible long-term (the most counterintuitive position):** Despite championing RLVR as the 2025 paradigm, Karpathy says he is "bearish on reinforcement learning" long-term (X post, Aug 2025; Dwarkesh interview, Oct 2025): "Reinforcement learning is terrible. It just so happens that everything that we had before it is much worse." His technical critique: "You're sucking supervision through a straw, because you've done all this work that could be minutes of rollout and you're sucking the bits of supervision of the final reward signal through a straw, and you're broadcasting that across the entire trajectory." RL reward signals are too sparse and too noisy to efficiently teach intellectual problem-solving.

**On what comes next:** Karpathy's positive bet is on **interactive environments as training data**. "Karpathy also sees promise in training LLMs through interactive environments—digital spaces where models can act and see the consequences... The main challenge now is building a large, diverse, and high-quality set of environments, much like the text datasets used in earlier training phases." He also mentions "system prompt learning" — learning at the level of tokens/context rather than weight updates — as a direction that hasn't been properly invented yet.

**On agents being a "decade" away (not a "year"):** His Dwarkesh interview title captures his view: AGI is "still a decade away." He is "bullish on environments and agents, but bearish on reinforcement learning long-term."

**On LLM architecture / Software 3.0:** His YCombinator keynote argues LLMs are "a new kind of computer, programmable in English." He is not arguing for radical architecture replacement — he sees LLMs as a new computational substrate, with the question being how to build increasingly capable products on top of them.

**On "jagged intelligence" / ghosts vs. animals:** "We're not evolving animals. We're summoning ghosts." LLMs occupy a different region of mind-space from humans. Capability spikes coexist with embarrassing failures. This matters for how we think about future progress.

**Assessment:** Karpathy is unusual in holding a nuanced position: RLVR was a genuine and important 2025 breakthrough, but RL itself is a kludge. The real next thing is environments — building large, diverse, interactive training grounds. He is also the clearest voice saying agents are harder and further away than the industry narrative suggests.

---

### 3. Dario Amodei — "Near the End of the Exponential, But RL From Experience Is the Next Engine"

**Sources:** Dwarkesh Patel interview "We Are Near the End of the Exponential" (Feb 13, 2026, 2h22m); essay "The Adolescence of Technology" (Jan 2026).

Amodei gave his most candid interview yet in February 2026. He made two significant moves: acknowledging that the pretraining-centric exponential has limits, and naming what he believes comes next.

**On pretraining hitting limits:** "We are near the end of the exponential" — referring specifically to the mechanism of "scale up compute, add more data, get proportionally better results." He is explicit that this is running into the physical limits of available training data and diminishing marginal returns on compute scaling. This is a significant admission for a CEO whose company's business model depends on continued capability progress.

**But he does not say progress stops.** Two mechanisms he identifies for the next phase:
1. **Reinforcement learning from experience** — AI systems learning from doing things, experiencing consequences, updating from results. "Current models learn from pre-existing human text. They cannot learn from doing things, experiencing consequences, and updating based on results the way humans do. This is a fundamental limitation."
2. **Better use of synthetic data** — models generating their own training problems and solutions, verifying them through reasoning. "You can always generate more synthetic data, even if natural internet-scale data is finite."

**On the "country of geniuses in a data center":** His most striking formulation, circulated widely after the interview. Within 3-5 years, he believes AI systems will be equivalent in intellectual capacity to having a country-sized population of highly intelligent people working on problems simultaneously. He is explicit this is not a distant hypothetical.

**On recursive self-improvement:** In "The Adolescence of Technology," he describes models "writing much of the code at Anthropic" and projects this loop could mature "within 1–2 years" — AI autonomously building the next generation.

**On the economics problem:** Most candidly, Amodei admitted: "we do not know how frontier AI labs become profitable at the scale we are operating." He did not pretend this is solved.

**Assessment:** Amodei occupies an intellectually honest middle position. He acknowledges the pretraining plateau publicly — something Altman resists doing — while maintaining bullishness on the next phase driven by experience-based learning and synthetic data. His 3-5 year claim for "country of geniuses" is the boldest near-term claim he's made.

---

### 4. Demis Hassabis — "One or Two More Breakthroughs Needed; World Models + Continual Learning Are the Missing Pieces"

**Sources:** Alex Kantrowitz interview at Davos (Feb 20, 2026); Google DeepMind podcast with Hannah Fry (Dec 2025); Genie 3 blog (Aug 5, 2025).

Hassabis is the most technically precise of the lab CEOs on what remains unsolved.

**On whether scaling is hitting limits:** He pushes back on the narrative. "For us internally, we were never questioning that. Just to be clear, I think we've always been seeing great improvements... There's still plenty of headroom there, just with the techniques we already know about and tweaking and innovating on top of that." He remains more bullish on continued pretraining improvements than the other lab CEOs.

**On what AGI requires:** "I'm definitely a subscriber to the idea that maybe we need one or two more big breakthroughs before we'll get to AGI. And I think they're along the lines of things like continual learning, better memory, longer context windows... better long-term reasoning and planning."

**On continual learning as the unsolved problem:** "Figuring out how to get AI to learn continuously is a problem that 'has not been cracked yet.'" He elaborated: "You want to have something a bit deeper than that, which is, as you say, actually changes the model over time. That's what ideally you would have. And that technique has not been cracked yet."

**On world models as the path:** Hassabis is personally working on world models and smart glasses, a combination that reveals his thesis: AI needs grounded physical understanding, not just language modeling. "A video model that can generate you 10 seconds, 20 seconds of a realistic scene—it's sort of a model of the physical world. Intuitive physics... it's steps towards having this idea of a world model—a system that can understand the world and the mechanics and the causality of the world."

**On the "infinite training loop" (SIMA + Genie strategy):** From the Dec 2025 podcast: DeepMind is converging Genie (interactive world-generator) and SIMA (generalist agent) into a loop where Genie generates environments and SIMA learns in them. "Whatever the SIMA agent is trying to learn, Genie can basically create on the fly." Genie 3, released Aug 2025, generates real-time interactive 3D worlds at 24fps at 720p — the technical substrate for this loop.

**On LeCun's position:** "I'm not a subscriber to someone like Yann LeCun, who thinks they're just some kind of dead end. I think the only debate in my mind is, are they a key component or the only component?"

**On AGI timeline:** 5-10 years from Davos 2026. More conservative than Altman/Amodei.

**Assessment:** Hassabis holds the most sophisticated technical view: LLMs are necessary but not sufficient for AGI. Continual learning and world models are the missing pieces. His lab's actual research trajectory (Genie + SIMA) is the clearest institutional bet on this view. He is the most credible champion of world models as a path to AGI — unlike LeCun, he doesn't say LLMs are dead ends; he says they need to be paired with grounded world models and continual learning.

---

### 5. Yann LeCun — "$3.5B Bet That LLMs Are a Dead End; JEPA Is the Path"

**Sources:** AMI Labs founding (Mar 2026, $1.03B raised at $3.5B valuation); MILA World Modeling Workshop keynote (Feb 4, 2026, threads.com post); V-JEPA 2 release by Meta (Jun 2025); LeWorldModel research (Mar 2026).

LeCun is the loudest and most radical critic of the prevailing paradigm.

**The departure:** He left Meta in November 2025 after 12 years, founded AMI Labs (Advanced Machine Intelligence Labs) in Paris, with Alexandre LeBrun as CEO and himself as Executive Chairman. He raised $1.03B at a $3.5B pre-product valuation — the largest seed round in European startup history.

**His core argument:** "The path to superintelligence via LLMs is complete bullshit. It's just never going to work." (November 2025 public statement.) The critique is architectural: autoregressive token prediction is categorically different from understanding. Models have processed more text than any human but lack grounded physical understanding.

**The JEPA alternative:** Joint Embedding Predictive Architecture predicts abstract representations in a learned embedding space rather than exact token sequences. Instead of predicting "the ball will hit the floor, bounce twice, roll under the couch," JEPA predicts the abstract trajectory — the direction, the energy loss — without committing to low-level detail. The research trajectory: I-JEPA (2023, CVPR), V-JEPA (2024, video), V-JEPA 2 (Jun 2025, 1.2B parameters, 1M hours of video, state-of-the-art physical reasoning), VL-JEPA (vision-language).

**His February 2026 keynote at MILA's World Modeling Workshop:** "I explain why world models need to use JEPA and not generative architectures. I also explain that a proper world model is not a video generation system." — He explicitly distinguishes his approach from DeepMind's video-generation-based world models.

**The strongest argument for his view:** A 4-year-old child has processed ~10^14 bytes of sensory data through their eyes. The entire text corpus for the largest LLMs is ~10^13 bytes. The child's data is multimodal, grounded, and interactive; the LLM's data is static text. Language covers a vanishingly small fraction of human knowledge.

**The strongest objection:** LLMs keep clearing capability bars that critics said token prediction couldn't clear. The JEPA research lineage has produced no commercial products. The gap between "interesting research direction" and "viable alternative to transformers" is measured in years and billions.

**Assessment:** LeCun's bet is the most contrarian and the most falsifiable. If LLMs continue improving toward human-level reasoning and planning over the next 5 years, AMI Labs faces serious difficulties. If LLMs plateau on tasks requiring genuine physical understanding or multi-step planning, JEPA looks prescient. The $3.5B valuation reflects investor belief that this is a serious alternative, not academic contrarianism.

---

### 6. Jeff Dean — "Distillation Is the Engine; Attending to Trillions of Tokens Is the Next Frontier"

**Source:** Latent Space podcast interview, "Owning the AI Pareto Frontier" (Feb 12, 2026).

Dean is the most infrastructure-focused perspective in this survey.

**On what comes after pretraining scaling:** He doesn't frame progress as hitting a wall. Instead: "as the models become more capable, people ask them to do more." The bottleneck is not capability but task complexity — models need to handle "much more complicated things that are going to involve generating many more tokens."

**On distillation as progress engine:** His thesis is that every frontier model enables a "Flash" model via distillation that inherits its capability at a fraction of the cost. "You have to have the frontier model in order to then distill it into your smaller model." The cascade: each generation's Pro model becomes the previous generation's Flash-equivalent. This sustains capability-at-cost progress even if frontier model training runs become harder to improve.

**On energy as the true constraint:** He reframes compute in picojoules rather than FLOPs: moving parameters across chip regions costs "a thousand picojoules" while a multiply costs "sub one picojoule." This is why batching is essential. The next efficiency gains come from hardware co-design that minimizes data movement.

**On the next paradigm:** He identifies "attending to trillions of tokens" — through hierarchical retrieval (lightweight filter → refinement → final reasoning) as the breakthrough frontier. He envisions modular knowledge (healthcare modules, robotics modules callable alongside base models) rather than trying to put everything in a single model.

**Assessment:** Dean is not a "pretraining is dead" voice. He thinks the game is extending what current architectures can do, through better distillation, modular knowledge, and hierarchical context. His Pareto frontier metaphor is important: the field isn't just chasing capability, it's chasing capability-per-dollar simultaneously, and that game has no obvious ceiling.

---

### 7. Liang Wenfeng (DeepSeek) — "Efficiency-Led Innovation; AGI Within Our Lifetimes, Three Key Bets"

**Source:** Sina Finance interview, translated by Bing (Feb 2025).

Liang Wenfeng is the most distinctive perspective from outside the Anglosphere.

**On pretraining and scaling:** "We're optimistic. The industry's progress is still on track." He is not a scaling pessimist. But he frames the problem as one of efficiency rather than raw scale: China needed to be 4x more compute-efficient than leading US labs to achieve comparable results. The innovation mission was to close that efficiency gap.

**On what they're betting on:** "We have three key bets: Math and coding — AI's natural test bed, like Go, because it's self-contained and verifiable. Multimodal — AI must interact with the real world to reach AGI. Natural language itself — Still an open challenge."

**On open-source as strategy:** "In disruptive technology, a closed-source moat is always temporary. Even OpenAI, despite being closed-source, cannot prevent others from catching up. Instead, we build our moat through our team — our people grow through experience, accumulate deep know-how, and form a culture of innovation."

**On the efficiency-as-path thesis:** DeepSeek's R1 model (released Jan 2025) demonstrated that RL from verifiable rewards could produce o1-level reasoning at dramatically lower cost. This is the strongest empirical demonstration that the frontier is not purely a function of compute.

**Assessment:** The DeepSeek view is that efficiency-led innovation is itself a legitimate "next paradigm" — not an alternative to scaling but a way of making the current scaling game accessible without frontier compute budgets. This view has been vindicated empirically in 2025. Liang Wenfeng's position is: whoever gets to the frontier most efficiently wins, and there are many paths there.

---

### 8. Sam Altman — "Scaling Continues; Memory, Agents, and Devices Are the Product Bets"

**Source:** Alex Kantrowitz / Big Technology Podcast interview (Dec 22, 2025).

Altman is the most conspicuous absence in the "what comes after pretraining" debate — he tends not to engage with the plateau question directly.

**On scaling:** He remains implicitly bullish, characterizing a "big model release early next year" and "significant gains." He says enterprises still want more IQ.

**On what product bets matter:** Deep memory ("infinite, perfect memory"), relationships with ChatGPT, a family of AI devices with Jony Ive, and enterprise expansion. These are product bets, not architecture bets.

**On the economics:** He says OpenAI's "exponential growth puts it on track to meet its obligations" for $1.4T in infrastructure commitments on $20B annualized revenue.

**Assessment:** Altman is the most bullish and least technically specific. He is the CEO most committed to the incumbent paradigm continuing to work. The fact that he avoids the pretraining-plateau conversation is itself data: either he believes it's false, or he believes it's not in his interest to acknowledge it publicly.

---

### 9. Guillaume Lample (Mistral) — "Long-Horizon RL Infrastructure and Open Models"

**Source:** Latent Space podcast (Mar 30, 2026).

Lample's most recent public statement focuses on the technical challenges of extending RL to longer time horizons: "When you are moving towards problems where something takes hours to get the reward, your model is completely lost. You have to build new algorithms and new infrastructure that supports these extremely long trajectories."

This is a precise technical diagnosis: RLVR works well on problems with fast feedback (math, code). It breaks down on problems with delayed rewards (complex research, multi-day tasks). The next frontier of RL-based training requires new infrastructure for long-horizon trajectories.

Lample is also the clearest champion of open-source as a safety mechanism: "We really don't want to be living in a world where the smartest models are only behind closed doors, only accessible to a few companies."

---

### 10. David Silver / Richard Sutton (Google DeepMind) — "The Era of Experience"

**Source:** "Welcome to the Era of Experience" paper (Apr 2025).

Silver and Sutton — architects of AlphaGo and AlphaZero — wrote the most programmatic statement of a post-pretraining paradigm. Their argument: "A new generation of agents will acquire superhuman capabilities by learning predominantly from experience."

The thesis: current AI is limited because it learns from human-generated data. The next generation learns from doing — from direct interaction with environments, including environments that humans have never encountered. This is the AlphaGo Zero path scaled to general intelligence: start from first principles, learn through self-play against verifiable objectives.

This aligns with Karpathy's "environments as next training paradigm" and is the intellectual framework behind DeepMind's Genie + SIMA "infinite training loop" strategy.

---

## Section B: Candidate Next Paradigms

### Paradigm 1: Test-Time Compute / Inference-Time Scaling as the New Axis

**Champions:** Sam Altman (OpenAI, o1/o3 bet), DeepSeek R1 team, Karpathy (acknowledges but skeptical long-term).

**The case:** OpenAI's o1 (late 2024) and o3 (early 2025) demonstrated that training models to generate longer reasoning traces — "thinking time" — produces capability gains that are distinct from training-time scaling. A new knob emerged: test-time compute. You can trade inference cost for task performance. DeepSeek-R1 showed the same approach could be replicated at dramatically lower training cost. Karpathy's year-in-review identifies this as the most important structural change of 2025: "We got a whole new knob (and associated scaling law) to control capability as a function of test-time compute by generating longer reasoning traces."

**Technical state in 2026:** Well-established for verifiable domains (math, code, logic). The open question is whether it extends to domains without clear verifiable rewards — research synthesis, strategic planning, genuine creative work.

**Strongest objection:** Karpathy's "sucking supervision through a straw" critique applies here too. The gains from RLVR/chain-of-thought are real but may be domain-bounded. A May 2025 arxiv paper ("Scaling over Scaling: Exploring Test-Time Scaling Plateau in Large Reasoning Models") found test-time scaling shows diminishing returns past a threshold. The benchmark-gaming problem is especially acute here — models trained against verifiable environments cluster around benchmark distributions.

**Confidence that this sustains 5+ years of progress:** Moderate. It's working now, but whether it generalizes beyond verifiable domains at scale is unclear.

---

### Paradigm 2: RL Environments as the New Scaling Axis

**Champions:** Karpathy (most explicitly), Silver/Sutton (theoretically), DeepMind SIMA/Genie strategy (institutionally).

**The case:** The bottleneck shifts from data to environments. Pretraining consumed internet text. RLVR consumed verifiable-reward environments (math problems, code puzzles). The next frontier is building large, diverse, interactive environments where AI can learn from consequences. Silver/Sutton's "Era of Experience" paper is the theoretical grounding. DeepMind's Genie 3 (Aug 2025) + SIMA combination is the most advanced institutional bet: Genie generates interactive 3D worlds in real time, SIMA learns in them. This creates what Hassabis called "the infinite training loop."

**Technical state in 2026:** Genie 3 generates real-time interactive worlds at 24fps/720p with consistency for "a few minutes." SIMA has been demonstrated in specific tasks within Genie-generated environments. The bottleneck now is environment quality, diversity, and the difficulty of transfer from simulated to real-world tasks. METR's evaluation environments and similar harnesses are building the evaluation infrastructure.

**Strongest case:** This is how AlphaGo Zero worked. Once you remove the human data constraint, the system can self-improve beyond any human-achievable level in the target domain. The question is whether Go-style self-play generalizes to open-ended, real-world tasks.

**Strongest objection:** The sim-to-real gap for physical tasks. For pure cognitive tasks (math, code), the "environment" is the problem itself — no simulation needed. For tasks requiring physical understanding or real-world interaction, we don't yet know how to generate sufficient variety of high-quality training environments.

**Confidence:** Strong for verifiable cognitive domains, uncertain for physical/real-world tasks.

---

### Paradigm 3: World Models / Grounded Physical Understanding

**Champions:** Demis Hassabis (Genie + SIMA strategy), Yann LeCun (JEPA), Silver/Sutton implicitly.

**The case:** Language covers a vanishingly small fraction of human knowledge. Most of what humans know — spatial relations, physical dynamics, cause and effect — was never written down. LeCun: "A human child receives approximately 10^14 bytes of sensory data through their eyes during their first four years of life. The entire text corpus for the largest LLMs is ~10^13 bytes." World models learn the underlying structure of physical reality rather than predicting tokens. Hassabis: video models exhibit "intuitive physics" understanding, and Genie 3 demonstrates this at real-time interactive resolution.

**Technical state in 2026:** V-JEPA 2 (Meta, Jun 2025) achieved state-of-the-art physical reasoning benchmarks. Genie 3 generates interactive 3D worlds in real time. Both are research systems, not production products. No JEPA-based system has been deployed at scale commercially. The gap between impressive demos and reliable physical understanding remains wide.

**Key disagreement between the two champions:** Hassabis believes LLMs are necessary components of world models (hybrid neuro-symbolic systems). LeCun believes JEPA-style architectures should replace autoregressive models entirely. This is a deep architectural disagreement.

**Strongest objection:** The strongest objection to LeCun's version is that it has produced no products. The strongest objection to Hassabis's version is that video generation models that look physically realistic are not the same as models with genuine physical understanding — Hassabis acknowledges Veo's video generation is "not physics-grade."

**Confidence:** World models are almost certainly part of what AGI looks like. Whether the path runs through JEPA-style architectures or through scaling video-LLMs remains genuinely contested.

---

### Paradigm 4: Agent-as-Product Economics — The Harness Becomes the Frontier

**Champions:** Karpathy (Software 3.0 framing), Anthropic (Claude Code), Aidan Gomez / Cohere (enterprise agents, North platform).

**The case:** The model dissolves into a product. Claude Code, Cursor, Devin — these are environments that organize LLM capability into productive agentic loops. The competitive frontier is not the weights but the harness: the context engineering, the tool use, the human-in-the-loop design, the autonomy slider. Karpathy's YC keynote: LLMs are "people spirits" — stochastic simulations of humans — and the product question is how to build "partially autonomous products" that work with their capabilities while compensating for their weaknesses. His Claude Code analysis: "Anthropic shipped a CLI tool that runs locally, integrates with your specific environment, and strings together tool use and reasoning in extended problem-solving loops." This is the "localhost paradigm" — agents that live on your computer, not in the cloud.

**Technical state in 2026:** Claude Code, Cursor, and similar tools are generating real revenue and demonstrating real productivity gains for software engineering. Cohere's North platform targets enterprise workflow automation. The question is how far agentic loops extend beyond software engineering into other domains.

**Strongest case:** This is the path to value regardless of what happens to underlying models. Even if pretraining plateaus, agentic product design keeps delivering capability gains by organizing existing model capability better. Jeff Dean's "50 interns" metaphor: frontier work becomes managing parallel coding agents rather than individual model capability.

**Strongest objection:** Agents remain brittle beyond narrow, verifiable domains. Karpathy: "AGI is still a decade away." The "decade of agents" is more realistic than the "year of agents." Long-horizon agentic tasks fail in ways that are hard to predict. Lample: "When you are moving towards problems where something takes hours to get the reward, your model is completely lost."

**Confidence:** This is happening right now, in production. It's not a future bet; it's the current state of the frontier product layer. The uncertainty is about ceiling, not floor.

---

### Paradigm 5: Continual Learning / On-Line Learning / Memory

**Champions:** Demis Hassabis (most explicit), Sam Altman (memory as moat), Dario Amodei (RL from experience).

**The case:** Current models have "goldfish brains" — they can search the internet, figure things out in-context, but the underlying model doesn't change. Hassabis at Davos: "Getting AI to learn continuously is a problem that 'has not been cracked yet.'" Every major lab CEO identifies this as a missing piece. Without continual learning, AI assistants reset with every conversation. With it, a truly personalized AI that gets better at serving you over time becomes possible. Amodei frames this as the natural successor to pretraining: "AI systems learning from their own experience — not just from text about experience."

**Technical state in 2026:** There are research demonstrations (Online-LoRA, modular memory architectures) but no scalable solution at production quality. AlphaZero-style learning worked in narrow domains; the challenge is generalizing to the open-ended real world. Hassabis: "Techniques that worked in games are obviously a lot easier than the messy real world."

**Strongest case:** The business value is obvious. A model that truly personalizes over time creates switching costs that dwarf anything current AI products have. Altman identifies memory as OpenAI's "real moat."

**Strongest objection:** Catastrophic forgetting — models that update on new experience tend to lose prior knowledge. Every approach that works in narrow domains has failed to generalize cleanly. This is a fundamental problem in deep learning that has not been solved at scale.

**Confidence (as a near-term path):** Low to moderate. This is a consensus "missing piece" but no one is close to a production solution.

---

### Paradigm 6: Distillation / Efficiency-Led Progress

**Champions:** Jeff Dean (Pareto frontier framing), DeepSeek (empirical demonstration), Liang Wenfeng.

**The case:** Frontier capability improvement need not come only from larger training runs. Every large model enables smaller, cheaper models via distillation. This cascade sustains "capability per dollar" improvements even when absolute frontier capability gains slow. DeepSeek demonstrated this empirically: o1-level reasoning at a fraction of the cost, through careful RL training and efficient architecture. Jeff Dean: "You have to have the frontier model in order to then distill it into your smaller model." The Flash models that power Gmail, YouTube, and Search derive from this cascade.

**Technical state in 2026:** Etched raised $500M for an inference-only ASIC (Sohu) claiming 10-20x better performance-per-watt than Nvidia H100. The hardware efficiency race is running in parallel with the software/architecture race. Purpose-built inference silicon is becoming a serious investment category.

**Strongest case:** This is how most users actually experience AI capability improvements — not through frontier model access, but through frontier-level capability becoming cheap enough to deploy at scale. The "Flash vs. Pro" dynamic is the product economy of AI.

**Strongest objection:** Distillation is not a source of new capability, only a mechanism for distributing existing capability more efficiently. If the frontier model doesn't improve, distillation cannot create new knowledge. It sustains the economic expansion of AI, not the capability expansion.

**Confidence:** This is happening reliably. It sustains the deployment frontier even when the capability frontier slows. It does not replace the capability frontier.

---

### Paradigm 7: Neuromorphic / Analog / New Hardware Substrates

**Champions:** Etched (transformer ASIC), Groq, Cerebras, Lightmatter. No senior lab researcher is publicly championing this as the next paradigm.

**The case:** GPUs were not designed for transformer inference. Purpose-built silicon can deliver order-of-magnitude improvements in performance per watt. Etched's Sohu, built on TSMC 4nm, claims 10-20x better performance per watt than Nvidia H100 for inference-only workloads. If inference costs fall by 10x, the economic dynamics of deployment change fundamentally.

**Technical state in 2026:** Etched raised $500M in Jan 2026 at $5B valuation. Claims are impressive but independent benchmarks are pending. Groq has shipped inference chips with demonstrated latency advantages. None of these companies has yet demonstrated frontier training capability — they are inference-focused.

**Strongest objection:** Transformer-only ASICs are a hardware bet that the transformer architecture continues to dominate. If next-paradigm architectures differ substantially from transformers, the ASIC bet fails. The flexibility of GPUs is not a bug; it's a hedge against architectural evolution.

**Confidence (as frontier training paradigm):** Low. As an inference efficiency play, moderately credible.

---

### Paradigm 8: Brain-Inspired / Predictive Coding

**Champion:** Yann LeCun (from a distance — his JEPA work is related but distinct).

**Technical state:** There is active academic research in predictive coding as an alternative to backpropagation. The strongest result is that it is significantly less mature than any of the other paradigms listed. No major lab is betting institutional resources on it.

**Confidence:** Speculative. Not discussed by any of the named practitioners surveyed.

---

### Paradigm 9: Mixture of Experts / Sparse Models

**Status:** MoE is already deployed (GPT-4, Gemini, Mixtral). It is not so much a future paradigm as a current architectural choice that offers better compute efficiency. Geminit Ultra uses MoE. Mistral's Mixtral models are MoE. The efficiency gains are real but the architecture is already mainstream.

**Assessment:** MoE is part of the current paradigm, not the next one. It is a tool for extending pretraining efficiency, not a replacement paradigm.

---

## Section C: Synthesis

### The View From 2026: What Does the Field Actually Believe?

Across 10+ named senior practitioners, a surprisingly coherent picture emerges — with one major fault line.

**The emerging consensus:**

1. **Pretraining at its current form has an approaching ceiling.** Sutskever says so explicitly. Amodei acknowledges it carefully. Hassabis hints at it while remaining more bullish than others. Even Altman's product pivots (memory, agents, devices) implicitly acknowledge that raw IQ gains are not the product story anymore. Liang Wenfeng is the outlier in remaining bullish on scaling progress.

2. **RLVR was the 2025 breakthrough and has a near-term wall.** Karpathy documents it as the clear 2025 paradigm shift. But the same practitioner is "bearish on RL long-term" because it works by sucking supervision through a straw and is most effective in verifiable domains. The wall of RLVR is the wall of verifiable environments — and most of what matters (research, strategy, genuine discovery) does not have a clear verifiable reward signal.

3. **Environments / experience / continual learning is where everyone points as the next major thing.** Karpathy says "interactive environments as the next major training paradigm." Silver and Sutton write "the era of experience." Hassabis describes the "infinite training loop" using Genie + SIMA. Amodei says "RL from experience." This is the strongest field-wide signal: the pretraining-on-human-data paradigm gives way to learning-from-doing, with AI-generated environments replacing internet text as the training substrate.

4. **The agent product layer is the commercial frontier right now.** Independently of paradigm debates, Claude Code, Cursor, and agentic workflows are generating real value. This is the practical "what comes next" that matters for the next 1-3 years regardless of research outcomes.

**The major fault line:**

LeCun vs. everyone else. LeCun says LLMs are architecturally dead ends and JEPA is the path. Hassabis says LLMs are necessary components of future AGI systems — the debate is only about whether they're sufficient. Sutskever says the generalization problem is real but proposes research-driven solutions that don't require abandoning LLMs. No one except LeCun is betting on a clean break from the transformer / LLM paradigm.

**Who has the most credible champion + realistic chance?**

**Most credible, highest confidence (3-5 years):**
1. **RL Environments / Experience-Based Learning** — Championed by Karpathy, Silver, Sutton, Hassabis (institutionally via SIMA+Genie), and validated by the DeepSeek R1 demonstration that verifiable-reward RL scales. The constraint is environment breadth, not fundamental feasibility. This is the consensus successor to pretraining-on-human-data.

2. **Agent-as-product / harness-first development** — Happening now, in production, generating real revenue. The most near-term safe bet. The ceiling is unclear; the floor is already visible.

3. **Continual learning / memory** — The most universally identified "missing piece" across all practitioners. No one has cracked it. When it gets cracked — whether in 2 years or 10 — it will be a genuine step-change.

**Credible but contested (5-10 years):**
4. **World models (Hassabis/DeepMind version)** — Most technically serious institutional bet. Genie 3 is the most advanced demonstration. The claim that video generation can ground physical understanding is plausible but not proven.

5. **JEPA / LeCun's world models** — The most contrarian bet with the most funding ($3.5B valuation). If LLMs plateau on physical/planning tasks, this looks prescient. Still no commercial product.

**The synthetic view:** The most likely "next paradigm" is not a single replacement architecture but a stack: LLMs (or LLM descendants) as the language/reasoning layer, combined with world model grounding for physical understanding, with continual learning enabling genuine personalization and improvement over time, all organized into agentic product harnesses that make the capabilities economically useful. This is essentially Hassabis's picture, and it is the most internally consistent across the practitioner statements surveyed.

---

## Open Gaps

1. **Sutskever's actual technical approach at SSI remains opaque.** He says it is different and worthy, mentions self-play and multi-agent, but will not specify. Tracking SSI's first model release — whenever it happens — will be the key datapoint.

2. **Whether test-time compute scaling has a ceiling that's already visible.** The "Scaling over Scaling" paper found plateau effects. More empirical work needed.

3. **The RL-for-long-horizon problem is a real unsolved technical challenge.** Lample's specific diagnosis — "when the reward is hours away, the model is lost" — points to infrastructure and algorithmic work that is underway but not solved. Tracking METR evaluations and Anthropic's harness work here.

4. **China's perspective beyond DeepSeek.** Liang Wenfeng's interview is one data point. The broader Chinese lab ecosystem (Zhipu, Moonshot, ByteDance) has not been covered here in depth.

5. **What Noam Shazeer is doing at Google.** He returned to Google from Character.AI in late 2024. His architectural views (he is one of the key figures behind sparse MoE at scale) and what he's working on at Google in 2025-2026 would be valuable context.

6. **Whether V-JEPA 2 / AMI Labs produces a commercial product within 2 years.** LeCun's bet becomes falsifiable if AMI Labs can ship something demonstrably better than LLMs on physical/planning tasks. Or it becomes falsifiable if LLMs clear those bars first.

---

## Sources (Primary)

- Ilya Sutskever, Dwarkesh Patel podcast: https://www.dwarkesh.com/i/179924094/straight-shotting-superintelligence (Nov 25, 2025)
- Andrej Karpathy, "2025 LLM Year in Review": https://karpathy.bearblog.dev/year-in-review-2025/ (Dec 19, 2025)
- Andrej Karpathy, Dwarkesh podcast: https://www.dwarkesh.com/i/176425744/rl-is-terrible (Oct 17, 2025)
- Andrej Karpathy, YC AI Startup School: https://www.youtube.com/watch?v=LCEmiRjPEtQ (Jun 19, 2025)
- Andrej Karpathy / The Decoder (bearish on RL): https://the-decoder.com/ai-researcher-andrej-karpathy-says-hes-bearish-on-reinforcement-learning-for-llm-training (Aug 30, 2025)
- Dario Amodei, Dwarkesh podcast: https://www.youtube.com/watch?v=n1E9IZfvGMA (Feb 13, 2026)
- Dario Amodei, "The Adolescence of Technology": https://darioamodei.com/essay/the-adolescence-of-technology (Jan 2026)
- Demis Hassabis, Alex Kantrowitz / Big Technology Podcast at Davos: https://www.vktr.com/digital-experience/inside-google-deepminds-ai-strategy-an-interview-with-ceo-demis-hassabis/ (Feb 20, 2026)
- Demis Hassabis, Google DeepMind podcast (world models / infinite training loop): https://www.humanoidsdaily.com/feed/deepmind-ceo-demis-hassabis-world-models-and-infinite-training-loops-are-the-keys-to-agi (Dec 20, 2025)
- Yann LeCun / AMI Labs: https://www.roborhythms.com/yann-lecun-ami-labs-world-models/ (Mar 20, 2026); https://algeriatech.news/yann-lecun-jepa-world-models-future-ai-2026/ (Mar 4, 2026)
- Jeff Dean, Latent Space: https://www.latent.space/p/jeffdean (Feb 12, 2026)
- Liang Wenfeng (translated): https://medium.com/@bingqian/inside-deepseek-an-interview-with-founder-liang-wenfeng-on-ai-disruption-and-agi-4c5db26091c2 (Feb 2, 2025)
- Guillaume Lample, Latent Space: https://singularitymoments.com/content/guillaume-lample-latent-space-we-really-dont-want-to-be-living-in-a-world-w/ (Mar 30, 2026)
- Sam Altman / Big Technology: https://www.vktr.com/digital-experience/i-spoke-with-sam-altman-what-openais-future-actually-looks-like/ (Dec 22, 2025)
- David Silver / Richard Sutton, "Welcome to the Era of Experience": https://theaiinnovator.com/welcome-to-the-era-of-experience/ (Apr 2025)
- Google DeepMind, Genie 3: https://deepmind.google/en/blog/genie-3-a-new-frontier-for-world-models/ (Aug 5, 2025)
- DeepSeek-R1 paper: https://arxiv.org/abs/2501.12948v2 (Jan 2025)
- Etched $500M raise: https://ai2.work/technology/etcheds-500-million-raise-a-blueprint-for-enterprise-ai-inference-in-2026/ (Jan 15, 2026)
