# Survey: Historical Technology Cadences and What They Predict for LLMs

## What I Searched

Primary search vectors:
- Moore's Law history, Dennard scaling collapse, Intel tick-tock retirement, post-Moore era (Exa + Semantic Scholar)
- Scannell et al. 2012 Eroom's Law paper (full text retrieved from lukemuehlhauser.com)
- Aviation technology plateau, Mercatus/Dourado analysis, Ammous SSRN paper
- Alfred Sloan/GM planned obsolescence history, automotive model year cadence
- Broadband speed growth slowdown data (HighSpeedInternet.com 2025 report, Telecompetitor)
- Lithium-ion battery density improvement rates (Ziegler & Trancik, MIT/RSC 2021)
- LLM scaling laws, data walls, benchmark saturation (multiple sources 2024-2026)
- Carlota Perez technological revolutions framework
- Jason Crawford/Roots of Progress S-curve analysis
- "Densing Law of LLMs" (Nature Machine Intelligence, 2025)
- AI agent time-horizon METR data (AI Digest March 2026)
- 2025 AI Year in Review (WhatLLM.org, comprehensive)

Key sources retrieved in full: Scannell 2012, Arstechnica on Intel tick-tock retirement (2016), Mercatus/Dourado on airplane speed stagnation (2016), Ammous SSRN aviation paper (2017), Empirics.org on Moore's Law death (2026), Adeaca on LLM scaling wall (2026), WhatLLM 2025 review.

---

## The Analogies in Detail

### 1. Moore's Law / Semiconductors (1965-present)

**Trajectory:**
- 1965: Gordon Moore observes transistor count doubling roughly every year; revised to every two years (1975). The "law" becomes a self-fulfilling industry coordination mechanism, not just an observation.
- 1970s-2000: Dennard scaling (1974 paper) made shrinkage essentially "free" — smaller transistors ran faster AND cooler AND cheaper simultaneously. The period 1975-2005 is the golden age: each node shrink yielded ~40% performance improvement at constant power.
- ~2004-2005: Dennard scaling collapses. CPU clock frequencies hit a wall around 3-4 GHz. Intel's Pentium 4 "Prescott" was a disaster — it ran at 90+ watts and still wasn't faster than its predecessor at lower clocks. Intel famously cancelled its planned 4 GHz parts in 2004. The industry did not publicly acknowledge this as a fundamental physics limit for several years; it was attributed to "engineering challenges" in real time.
- 2006: Industry pivots to multi-core. Intel releases the Core 2 Duo. The metric shifts from "GHz" to "cores." Progress continues but the *kind* of progress changes — you need to parallelize software to benefit.
- 2007: Intel launches "tick-tock" — alternating node shrinks and architecture refreshes on a ~2-year cadence. This preserves the *appearance* of Moore's Law even as the underlying physics is harder.
- ~2013-2016: Tick-tock itself begins failing. Moving from 22nm to 14nm takes longer than expected. Broadwell (first 14nm part) is delayed, incomplete, and rushed. Intel stretches 14nm across three generations: Broadwell, Skylake, Kaby Lake.
- 2016: Intel officially retires tick-tock in its 10-K filing, replacing it with "Process-Architecture-Optimization" (three generations per node instead of two). The Ars Technica headline: "Intel retires 'tick-tock' development model, extending the life of each process." Intel notes that each new process is "getting harder to develop and productionize" and that light-wavelength lithography (193nm UV) is producing features far smaller than the wavelength itself, requiring expensive multi-patterning tricks.
- 2017-present: Node names become marketing. "7nm" at TSMC is not the same as "7nm" at Intel. The industry invents new complexity vectors: 3D stacking (HBM memory, die stacking), chiplets, heterogeneous integration (GPU + CPU + AI accelerator in one package), specialized silicon (NPUs, TPUs). The Empirics.org 2026 analysis concludes: "Progress now depends on messy workarounds... improvements will arrive unevenly across applications."
- 2025-2026: EUV lithography (finally in high-volume production at TSMC/Samsung) has extended scaling somewhat, but each new node costs $1-2B in design costs alone. The "area bloating" paper (HPCA 2026) models that continuing current approaches from 3nm to 1.8nm will require 78-117x more chip area to match historical performance gains.

**Were insiders aware in real time?** Partially. The power wall was recognized technically around 2004-2005, but the narrative of "Moore's Law is alive, we're just moving to multi-core" was maintained for years. The full acknowledgment that the cadence itself was slowing came progressively: tick-tock stretched in 2015, officially retired in 2016, node renaming crisis ~2017-2019. There was no single moment of recognition — it was years of euphemisms ("architectural optimization," "process maturation") before the industry settled on "post-Moore era" framing.

**What replaced Moore's Law as the driver of compute progress?**
- Multi-core (2006+)
- GPU parallelism (CUDA era, 2007+)
- Specialized accelerators: TPUs (2016), NPUs, AI ASICs
- 3D packaging and chiplets (2018+, AMD's EPYC, Apple M-series)
- Algorithm improvements (same hardware, better software)
- Domain-specific hardware: not making chips faster for everything, but making them very fast for specific tasks

**The crucial insight:** Intel kept shipping "new" CPUs every year after the physics stopped delivering automatic gains. Node renamings, "optimization" releases, incremental IPC improvements — the cadence of *releases* continued even as the cadence of *underlying performance doublings* slowed from every 2 years to never (for single-threaded performance). A Kaby Lake CPU (2017) had essentially the same single-core performance as Skylake (2015), which was barely faster than Broadwell (2014). The product refresh machinery continued; the fundamental progress had stalled.

**Assessment:** High-credibility trajectory. Primary sources: Intel 10-K filings, Ars Technica reporting, academic papers on Dennard scaling (the retrospective is documented at ResearchGate). The Dennard 30-year retrospective (IEEE 2004) is the clearest technical source. The Empirics.org piece (Jan 2026) provides a good popular synthesis.

---

### 2. Pharmaceutical R&D / Eroom's Law

**Trajectory:**
- 1950s-1960s: Golden age of drug discovery. Penicillin, corticosteroids, lithium, imipramine, first antipsychotics, first statins all emerge. R&D is relatively cheap; the "fruit" is abundant.
- 1962: Kefauver-Harris Amendment post-thalidomide forces FDA to require proof of efficacy. R&D efficiency dips.
- 1950-2010: A slow, relentless decline. The Scannell et al. 2012 paper (Nature Reviews Drug Discovery, the definitive source, read in full) documents that new FDA-approved drugs per billion US dollars of R&D spending has **halved approximately every 9 years** since 1950. In inflation-adjusted terms, the industry became ~80-fold less productive over 60 years.
- The number of new drugs per year has been broadly flat; costs have risen.
- Brief uptick in mid-1990s: FDA cleared a regulatory backlog after the 1992 Prescription Drug User Fee Act, plus HIV drugs benefited from politically-lowered regulatory hurdles. This is a brief deviation, not a reversal.
- 2011-present: Major pharma companies begin cutting R&D spending (Pfizer, Merck, AstraZeneca) in response to shareholder pressure that has priced-in the Eroom's Law trend.

**Why? Scannell's four causes:**
1. **"Better than the Beatles" problem**: Yesterday's blockbuster is today's generic. New drugs must beat metformin, statins, proton pump inhibitors — drugs that are both extremely effective AND available for pennies. The bar rises continuously. Doctors won't prescribe a new branded diabetes drug unless it's better than cheap generics.
2. **"Cautious regulator" problem**: Each drug scandal (thalidomide, Vioxx) ratchets up regulatory requirements. The ratchet rarely loosens. Documentation requirements have become absurd (Novo Nordisk's submission for two insulin drugs: if printed, it would exceed the height of the Empire State Building).
3. **"Throw money at it" tendency**: More money doesn't produce more drugs. It produces more failed trials.
4. **"Basic research-brute force" bias**: Combinatorial chemistry increased drug-like molecules synthesized per chemist by 800x; genomics identified thousands of new targets; HTS automated early screening. Yet clinical trial success rates have been flat for 50 years. The industry systematically overestimated how much upstream improvements would translate to approved drugs.

**Did the release cadence slow, or did they lower the bar?**
The number of drug approvals per year has been relatively flat (~30-50/year) while R&D spending exploded. The industry sustained the *appearance* of continuous output by:
- Pursuing "me-too" drugs (second or third entry in established classes) where the path is more predictable
- Narrowing indication scope (approval for rare diseases, which face lower bars)
- Biologics and biosimilars, which have a different risk profile
But the absolute number of genuinely novel mechanisms approved has declined. The appearance of a continuing cadence is partly illusion.

**Lessons for LLMs:**
- The "better than the Beatles" problem may already apply: new LLM releases must now beat GPT-4, Claude 3 Opus, Gemini Ultra. The back catalogue is excellent and largely free (or near-free). New models face a rising bar.
- The "basic research-brute force" bias is directly applicable: more compute, more data, more RLHF may not linearly translate to better real-world task performance.
- The "throw money at it" tendency: frontier model training costs are exploding.
- **Key difference**: pharma has a hard external validation constraint (does the drug work in humans?). LLMs have softer validation — benchmarks that saturate, use-case metrics that are harder to establish rigorously.

**Assessment:** Scannell 2012 is peer-reviewed, Nature Reviews Drug Discovery, heavily cited (13+ on Semantic Scholar, likely much more on other indexes since it's a classic). The framework is robust and has held since 2012 without major challenge to its core observation.

---

### 3. Aviation (1903-present)

**Trajectory:**
- 1903: Wright Brothers, ~6 mph
- 1920s: rapid improvement, first airlines
- 1947: Chuck Yeager breaks sound barrier (X-1)
- 1955: First FAI-recognized supersonic flight
- 1958: First Mach 2 flight
- 1969: Boeing 747 enters service — democratizes mass air travel; maximum speed ~Mach 0.85
- 1976: Concorde enters commercial service (Mach 2+, London-NY in 3.5 hours); SR-71 sets airspeed record of 2,193 mph (Mach 3.3+) — both records still stand as of 2026.
- **1973: Inflection point**. The US bans civil supersonic flight over land due to sonic boom concerns. This immediately destroys the market for the Concorde (limited to transoceanic routes) and eliminates incentives to develop next-generation supersonic transports.
- Post-1976: Effectively no progress on speed. The Concorde is retired in 2003. No replacement. Commercial aviation today cruises at ~Mach 0.85, slower than the Concorde and not meaningfully faster than 1970s jets.
- **What did aviation shift TO?** After speed stagnated: fuel efficiency (engines became dramatically more efficient; twin-engine long-haul became possible), safety (fly-by-wire, collision avoidance systems), reliability, comfort (widebody cabins, IFE), load factor optimization (revenue management algorithms), and eventually low-cost carrier models. The performance metric changed from "how fast" to "how cheaply and safely can we move passengers."
- Ammous (2017 SSRN paper) argues this represents a genuine regression: "airplanes operational today can no longer reach the speed and altitude records set four decades ago." Commercial flight times have actually *lengthened* slightly (circuitous routes, air traffic congestion) despite better engines.
- Dourado/Kotrous (Mercatus, 2016): "Speed gains fell approximately 58% in 2024" — actually this framing fits broadband better; for aviation they note "commercial flight isn't any faster — in fact, today's flights travel at less than half the Concorde's speed."

**Why did aviation stagnate?**
1. Physics limits: supersonic commercial flight faces sonic boom, fuel consumption, and heat challenges
2. Regulation: the 1973 FAA ban on civil supersonic flight over the US destroyed investment incentives
3. Economics: the Concorde was never profitable; airlines had no financial motive to invest in faster planes
4. "Good enough": Mach 0.85 gets passengers from New York to London in 7 hours. Is Mach 2 worth 3-4x the cost?
5. New entrants/new axis: the disruptive innovation in aviation post-1970s was *cheap* flight (Southwest model), not *fast* flight.

**What does this predict for LLMs?** The aviation analogy suggests a "good enough for the use case" plateau is real and can last decades. If GPT-5 level capability is adequate for 95% of enterprise use cases (coding assistance, document summarization, customer service), the pressure to build GPT-7 may become more economic than technical. The industry might shift its competitive axis from raw capability to cost (DeepSeek's $5.57M training cost vs. tens of millions), reliability, domain specificity, or safety. The LLM equivalent of Southwest Airlines may already be happening — DeepSeek, open-source models, fine-tuned specialists.

**Assessment:** Aviation stagnation is well-documented empirically. The Mercatus and SSRN papers are credible secondary analyses. The FAA supersonic ban is a historical fact. Key caveat: new supersonic entrants (Boom Supersonic, scheduled for late 2020s) may eventually break the stagnation, suggesting regulation can be undone.

---

### 4. Automotive Industry

**Trajectory:**
- 1885: Benz Patent-Motorwagen
- 1900-1930: Explosive progress. The car goes from a curiosity to a mass product. Ford's Model T (1908-1927) establishes mass production. By 1930, enclosed cars, hydraulic brakes, synchromesh transmissions, electric starters are all standard. Engine power, reliability, comfort, and speed advance dramatically.
- **~1920s inflection: Alfred Sloan's "planned obsolescence"**. By the late 1920s, most Americans who would buy a car had bought one. The market was saturating. Sloan's genius was recognizing that technical stagnation is compatible with marketing cadence. General Motors introduced annual model changes — cosmetic updates that made last year's car look dated. This required convincing customers "a car not just as a car, a transportation machine, but as an expression of your personality or your status or your desire for something new." It worked: by 1930, GM had surpassed Ford. Ford, who believed in the Model T's essential sufficiency and kept improving it, lost badly.
- 1930-2000: ~70 years of mostly cosmetic model-year cycles. The fundamental technology (internal combustion engine, independent suspension, disc brakes) was mature by the 1970s. Cars became safer, cleaner (catalytic converters, fuel injection, OBD), more comfortable, and more reliable — but the pace of fundamental performance advance slowed dramatically. A 1990 car drives essentially the same as a 1970 car at highway speeds.
- **~2010-2020: Paradigm shift driven by regulation and new entrants**. Tesla demonstrates that electric vehicles are viable and desirable. EV adoption begins. Regulatory pressure (EU 2035 combustion ban, US CAFE standards) forces the shift. Crucially, this paradigm shift was not driven by incumbents — it was forced by external pressure and new entrants.

**The lesson:** Cadence can persist on marketing/branding logic for decades after technical stagnation. Annual model years, "new and improved," press launches, brand differentiation — none of these require underlying technical progress. The appearance of continuous progress can be manufactured. The shift to EVs demonstrates that a paradigm shift, when it comes, may be driven not by the incumbents but by regulation and outsiders.

**Prediction for LLMs:** OpenAI, Anthropic, and Google may continue shipping "new model" announcements — GPT-5, 5.5, 6, Claude 5, 6 — even if the underlying improvements become marginal. Benchmark marketing will substitute for genuine capability progress. The "annual model refresh" pattern is already visible: OpenAI releases major models, then "o" variants, then "mini" variants, then new major versions. This could continue for years without fundamental advances. The paradigm shift, when it comes, may be driven by new entrants or regulatory pressure, not incumbent labs.

**Assessment:** The Sloan/GM planned obsolescence history is well-documented (Treehugger article draws on Gary Cross history of consumerism, Jamie Kitman automotive journalism). The automotive analogy is historically robust, though the underlying technological comparison to LLMs requires care — cars had a mature, well-understood physical platform that LLMs don't yet have.

---

### 5. Internet Bandwidth / Consumer Broadband

**Trajectory:**
- Early 1990s: Dial-up, 14.4-56 Kbps
- Late 1990s: DSL and cable begin, ~1-10 Mbps
- 2000s: Broadband grows rapidly; by 2010, 10-50 Mbps typical
- 2010s: Cable upgrades (DOCSIS 3.0/3.1), fiber expansion; speeds reach 100-1000 Mbps in urban areas
- 2020-2024: Rapid speed gains (pandemic drove demand for better home broadband). Average US speeds: 104 Mbps (2020) → 129 Mbps (2021) → 158 Mbps (2022) → 196 Mbps (2023) → 214 Mbps (2024).
- **2024-2025 inflection**: "Internet speed gains fell by approximately 58% in 2024, the weakest results we've seen since we began our performance tracking" — HighSpeedInternet.com. The growth rate went from 37% year-over-year (2022-2023) to 19% (2023-2024). Analysis: "We may just be seeing an adjustment in the internet needs of the average household. Customers could be simply choosing cheaper and slower internet plans."
- Key observation: 100 Mbps is "fast enough" for streaming 4K video, video conferencing, gaming. The marginal utility of going from 100 Mbps to 1 Gbps is invisible to most users. Speed growth is slowing because demand for speed is saturating.

**Parallel to LLMs:** The "good enough" plateau is real. Consumers don't upgrade from 200 Mbps to 500 Mbps because there's nothing they can do with 500 Mbps that they couldn't do with 200 Mbps. If GPT-5 can write good code, summarize documents accurately, and converse naturally — and GPT-6 does these things 15% better — the marginal utility gain may not drive adoption changes, especially if the price is higher.

**Assessment:** The broadband slowdown data from HighSpeedInternet.com (2025) is recent and concrete. It's industry market research, not peer-reviewed, but the numbers are internally consistent and methodologically straightforward.

---

### 6. Battery Energy Density (Bonus)

**Trajectory:**
- Lithium-ion batteries have improved roughly 5-8% per year in energy density since commercialization (~1991). This is steady, slow, and unspectacular — nothing like Moore's Law.
- Ziegler & Trancik (MIT, Energy & Environmental Science, 2021, peer-reviewed): using multiple historical datasets, the cost of lithium-ion batteries has declined about 97% since 1991, but the improvement follows a Wright's Law pattern (cost declines with cumulative production), not a time-based exponential. Crucially, energy density improvement is much slower than cost improvement.
- There is no "breakthrough" era in lithium-ion; progress has been steady and incremental.

**Why this matters:** Battery energy density represents a case where a technology improved importantly but slowly, without the dramatic exponential of Moore's Law, and without hitting a sharp wall. It's the "boring middle" case — important progress, just not transformational pace. If LLMs follow this pattern, you'd expect continued improvement at maybe 10-20% per year on real-world task performance, but not doublings every few months.

**Assessment:** Ziegler & Trancik (2021) is the authoritative peer-reviewed source. MIT-based, strong methodology.

---

## LLM-Specific Context (2024-2026)

**The current picture:**
- METR data (AI Digest, March 2026): AI agent "time horizons" — the length of tasks agents can complete successfully — have been doubling every 7 months from 2019-2025, and accelerating to every 4 months in 2024-2025. ChatGPT (2022) could do 30-second coding tasks; current frontier agents can handle 14+ hour tasks autonomously.
- Nature Machine Intelligence "Densing Law" (November 2025): The *capability density* of open-source LLMs (capability per unit of model parameters) doubles approximately every 3.5 months. This is a different metric from raw capability — it measures efficiency gains. Inference costs fell ~280x from 2022-2025 per WhatLLM 2025 review.
- Benchmark saturation (Brenndoerfer, March 2026): MMLU, once a meaningful benchmark, is now essentially saturated. GPT-4 scored 86.4% in early 2023; by late 2024, models exceeded 90%. New benchmarks (AIME, SWE-Bench) are needed but also saturate within 1-2 years.
- WhatLLM 2025 review: "Test-time compute: the new scaling law. Traditional scaling laws said: double parameters and data, get predictable capability gains. Those returns are diminishing. The new scaling dimension is test-time compute."
- Scaling wall discourse: Multiple sources (Adeaca, Jan 2026; Medium, Feb 2026) note the industry pivot from "bigger model = better" to test-time compute (o3-style "thinking"), specialization, and efficient inference. This structural pivot occurred without a clean public announcement — labs shifted strategy while maintaining aspirational language about frontier scaling.
- DeepSeek effect: DeepSeek V3.2 trained for $5.57M achieves comparable performance to models that cost tens of millions. Open weights at 10x lower inference cost. This is exactly the "efficiency" curve that follows capability plateaus in other industries.

---

## The Comparison: Which Analogy Is the Best Fit?

### Ranking the analogies

**1. Moore's Law / Semiconductors — the strongest structural parallel, but with crucial differences**

The structural match is nearly exact: exponential improvement driven by a single underlying physical mechanism (transistor density; in LLMs, scale × data × compute), a period where insiders maintained optimistic narrative even as the fundamental mechanism stalled, the pivot to alternative dimensions of progress (multi-core, chiplets → test-time compute, specialization), continued release cadence divorced from underlying physics.

The Intel tick-tock retirement (2016) is the clearest historical parallel to what may be happening with LLMs now: an industry formally acknowledging that its 2-year cadence no longer reflects physics, while pivoting to an "optimization" phase that maintains annual releases but delivers smaller gains. The LLM equivalent is the shift from "GPT-5 will be much bigger and better" to "we're adding reasoning, test-time compute, and agent capabilities."

**Key difference**: Moore's Law operated on *hardware*, which is capital-intensive and durable. The CPU released in 2016 is still running in 2026. LLM weights are software — they can be updated daily, deployed globally instantly, and the cost structure is fundamentally different. This means the LLM industry can *iterate faster* than semiconductor firms could, but it also means the competitive pressure is more intense and the lifecycle shorter.

**2. Automotive / Planned Obsolescence — the most dangerous pattern if it takes hold**

The Sloan model — marketing-driven annual refreshes that substitute brand differentiation for genuine technical progress — is already partially visible in AI. "GPT-4o mini," "Claude 3.5 Haiku," "o1-mini," "o3" — the model naming conventions are proliferating faster than genuine capability gaps between adjacent releases justify. The risk is that LLM releases become primarily marketing events, with benchmarks playing the role of "horsepower ratings" — technically real but practically meaningless at the margin.

The automotive lesson that the paradigm shift came from *outsiders* (Tesla) is ominous: if frontier LLM improvement genuinely plateaus, the transformative development might come from a completely different architectural approach (neurosymbolic systems, embodied AI, brain-computer interfaces) from unexpected quarters.

**3. Eroom's Law — the most alarming possibility, but structurally different**

Eroom's Law represents a case where the costs of progress rise faster than the benefits. The direct LLM analog would be: each successive doubling of frontier model capability requires exponentially more compute, data, human feedback, and capital — and produces ever-smaller gains in real-world utility. There is already evidence for this: GPT-3 → GPT-4 was a qualitative leap; GPT-4 → GPT-5 appears to be a smaller gap (as measured by capability benchmarks and user experience reports, though not by compute cost). The "throw money at it" tendency (Scannell's term) is plainly visible: Anthropic's $40B valuation, xAI's $50B round, the Stargate $500B commitment.

The "better than the Beatles" problem has an LLM analog that's underappreciated: as GPT-4 level capability becomes free (or near-free via open-source), new models must demonstrate superiority over an excellent free baseline. The value of marginal improvement shrinks. New entrants (DeepSeek, Llama) are the generic metformin to Claude Opus's branded statin.

**Key difference from pharma**: Pharma's constraint is external biological reality — drugs must work in human bodies. LLMs have no such hard external constraint; their performance ceiling on many tasks (code generation, text summarization, translation) may be much higher than current models, meaning there's more runway. But for tasks requiring genuine world-model understanding, physical embodiment, or causal reasoning, the Eroom's Law dynamic may apply.

**4. Aviation — the most instructive cautionary tale**

The aviation plateau happened when a technology was "good enough" AND when regulation removed the primary incentive (the supersonic ban). The LLM equivalent would be if: (1) current capability is sufficient for 90%+ of commercial use cases, AND (2) regulation or liability concerns reduce the incentive to push frontier capability further. Both conditions are partially in view. Enterprise AI adoption is high but "jagged intelligence" (Karpathy's term, cited in WhatLLM) means current models are already adequate for the structured tasks that drive most commercial value.

**My verdict: The Moore's Law analogy is the closest structural fit, and its later phase — the semiconductor industry's post-Dennard maneuvers — is the most instructive for what comes next.**

The LLM industry in 2024-2026 closely resembles the semiconductor industry of 2007-2016:
- A fundamental underlying mechanism (Dennard scaling; scaling laws) has begun to deliver diminishing returns
- The industry has pivoted to alternative progress vectors (multi-core; test-time compute) while maintaining marketing language about continuous progress
- Annual release cadence continues, with each release branded as significant, even as the underlying mechanism weakens
- "Node renamings" in semiconductors ≈ benchmark gaming in AI: MMLU has saturated, new benchmarks are created, models claim leadership on the new benchmarks
- The truly consequential innovation moves to *specialization* (GPUs for graphics, TPUs for inference; domain-specific fine-tuned models, reasoning-optimized models)
- Cost reduction and efficiency improvement continue even when raw performance plateaus (DeepSeek's $5.57M training ≈ "same chip on a smaller process for lower power")

However, a critical uncertainty separates LLMs from semiconductors: **whether there is a "Dennard scaling" analog that has actually broken, or whether new architectural approaches (reasoning/thinking models, o3/Claude Sonnet 4.5-style extended thinking) represent a new scaling vector with its own multi-year runway.** The METR data on agent time horizons doubling every 7 months suggests the new vector is real and robust. If so, we are more in the Moore's Law 2004-2012 phase (multi-core pivot), not the 2016+ stagnation phase.

---

## Landscape Assessment

### State of Knowledge

**What we know with confidence:**
- LLM pre-training scaling (more parameters + more data = better performance) is showing diminishing returns. The data wall is real (running out of high-quality internet text). The compute cost wall is real ($100M+ training runs are limiting the number of labs that can compete).
- Benchmark saturation is happening rapidly and systematically.
- Alternative scaling vectors exist and show promise: test-time compute (o3-style reasoning), synthetic data, agent frameworks, domain specialization.
- Efficiency (Densing Law) is improving rapidly even as frontier capability growth slows.
- The industry is in a "post-Dennard" transition that it is actively managing.

**What is contested or uncertain:**
- Whether test-time compute provides a sustained multi-year runway comparable to pre-training scaling, or whether it too hits diminishing returns within 2-3 years.
- Whether genuine AGI-level capabilities (robust causal reasoning, generalizable world models) require fundamentally different architectures, or can emerge from scaled transformers with better training.
- Whether the "good enough for the use case" plateau has arrived for enterprise. Data suggests adoption is high, but so is rate of failed deployments — models may be "good enough for demos but not good enough for production."

### Agreements Between Sources

All sources agree:
1. Pre-training scaling has hit meaningful limits (data wall, cost wall, performance wall)
2. The industry is pivoting to alternative progress vectors
3. Benchmark inflation is real and measurement is in crisis
4. Efficiency is improving even as frontier capability gains slow
5. Open-source models are converging rapidly on closed models

### Conflicts Between Sources

Key conflicts:
1. **Speed of plateau**: METR's time-horizon data (March 2026) suggests capability is still doubling every 4-7 months. Skeptics (Adeaca, AI Supremacy) argue fundamental limits are already binding. These are measuring different things (agent task length vs. raw benchmark scores), so both may be correct simultaneously.
2. **Test-time compute as new paradigm**: Some (WhatLLM 2025, AI Digest) frame it as a durable new scaling law. Others frame it as a kludge with its own ceiling.
3. **Analogy choice**: No direct source has rigorously compared the semiconductor/pharma/aviation analogies. The Liso et al. 2023 paper (Nanotechnology Materials and Devices) is the only academic paper that explicitly draws the Moore's → Eroom's Law analogy for semiconductor R&D costs, but it doesn't address LLMs.

### Gaps and Under-Explored Areas

1. **Who was aware in real time?** Historical record on semiconductor insiders' internal awareness of the Dennard collapse (vs. public messaging) is thin. This is directly relevant for understanding how LLM labs are currently perceiving their own situation.
2. **The Carlota Perez framework** (technological revolutions, installation → deployment phases) is mentioned in the survey search results but I could not retrieve substantial content. Her framework (tech bubble = installation phase; post-crash = deployment phase) might predict we are transitioning from installation (building the infrastructure) to deployment (applying it to existing industries), which has its own pattern distinct from any hardware analogy.
3. **Jason Crawford/Roots of Progress S-curve framework**: Retrieved the title of his key post ("Teasing Apart the S-Curves," 2020) but the content didn't load fully. His framework distinguishes between: (a) exhaustion of a single S-curve, (b) low-hanging fruit within a paradigm, and (c) genuine end-of-progress. This distinction is crucial but underrepresented in my survey.
4. **Regulatory analog**: The aviation stagnation was driven partly by the 1973 FAA supersonic ban. An EU AI Act, US executive orders, or liability regimes could play a similar role in LLMs — removing the incentive to push capability further. This is speculative but structurally important.
5. **"Me-too" LLMs**: The pharma parallel of me-too drugs (second or third entry in established classes, lower risk, lower innovation) may predict a proliferation of specialized/fine-tuned models serving niche use cases, which is already happening (legal AI, medical AI, code AI) but not systematically analyzed.

### Surprises

1. **The Intel tick-tock story is more direct than expected**: The specific mechanism — extending a node from two generations to three, changing the name of the cadence, maintaining annual product releases while delivering less — is almost surgically analogous to what LLM labs are doing now (extending "reasoning" capabilities via RLVF on top of an existing base model, calling it o1/o3/Claude thinking mode).

2. **Eroom's Law in semiconductors itself**: The Liso et al. 2023 paper notes that semiconductor R&D costs are now *also* following Eroom's Law — the R&D cost to advance to each new node is rising faster than the performance gain. This hasn't been widely picked up in the LLM discourse, but the implication is that even the compute side of LLM training faces Eroom-type pressures.

3. **The "Densing Law" paper (Nature, 2025)** suggests capability *per parameter* is doubling every 3.5 months — this is an efficiency story, not a capability story. It's analogous to the semiconductor industry getting more performance per watt after the power wall, not more performance per transistor. Progress continues but measured differently.

4. **Broadband speed growth deceleration in 2024** is a very concrete data point. The HighSpeedInternet.com report showing a 58% decline in speed improvement rates is recent, well-documented, and clearly driven by demand saturation ("customers choosing cheaper plans"). If LLM *usage* eventually saturates on current capability, the pressure for capability improvements will reduce.

5. **The automotive paradigm shift from outsiders is strikingly apt**: The EV revolution was driven by Tesla (outsider) + regulatory pressure (CAFE, EU bans), not by Ford/GM. The LLM paradigm shift, if it comes, may similarly be driven by outsiders (DeepSeek, or a non-transformer architecture startup) + regulatory pressure (AI safety requirements that force new approaches), not by OpenAI/Anthropic.

---

## Key Sources

### Scannell, Blanckley, Boldon & Warrington (2012)
- **Link**: https://lukemuehlhauser.com/wp-content/uploads/Scannell-Diagnosing-hte-decline-in-pharmaceutical-RD-efficiency.pdf
- **Key content**: Full text retrieved. Defines Eroom's Law: drugs per billion USD R&D halved every 9 years since 1950. Introduces "better than the Beatles," "cautious regulator," "throw money at it," and "basic research-brute force bias" as causes.
- **Assessment**: Peer-reviewed (Nature Reviews Drug Discovery), high-impact, directly applicable to LLM R&D dynamics. The four causes framework is analytically sharp and maps well to LLMs.

### Ars Technica: Intel retires "tick-tock" (2016)
- **Link**: https://arstechnica.com/information-technology/2016/03/intel-retires-tick-tock-development-model-extending-the-life-of-each-process/
- **Key content**: Intel's 10-K formally retires two-phase model; moves to three-phase PAO (Process-Architecture-Optimization). "Each new process is getting harder to develop and productionize." First detailed public confirmation that Moore's Law cadence was failing.
- **Assessment**: Primary-source journalism reporting on an SEC filing. Highly credible. The explicit parallel to current LLM lab behavior (maintaining cadence by adding an "optimization" phase) is striking.

### Dourado & Kotrous / Mercatus Center (2016)
- **Link**: https://www.mercatus.org/publications/technology-and-innovation/airplane-speeds-have-stagnated-40-years
- **Key content**: Airspeed records have stood since 1976. Commercial aviation is slower today than 1976 (vs. Concorde). Stagnation driven by regulatory ban on supersonic flight (1973) that removed R&D incentives.
- **Assessment**: Policy research paper, libertarian-leaning Mercatus. Empirical claim about speed records is factually correct and independently verifiable. Regulatory argument is well-supported.

### Ammous (2017), "Slowdown: Aviation and Modernity's Lost Dynamism"
- **Link**: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3036275
- **Key content**: Three markers of aviation slowdown: speed records unreachable, flight times not shorter (actually longer), Concorde retired without replacement. Discusses cultural and political-economic causes.
- **Assessment**: Columbia working paper; 667 downloads. Author is known for heterodox positions (Bitcoin Standard) but this aviation analysis is empirically grounded.

### Empirics.org: "Moore's Law Is Dead" (2026)
- **Link**: https://empirics.org/moores-law-is-dead/
- **Key content**: Clear popular synthesis of the end of Moore's Law. "Progress now depends on messy workarounds... improvements will arrive unevenly across applications." Covers specialization, 3D packaging, quantum/photonic as co-processors.
- **Assessment**: Popular science website, not peer-reviewed. But the empirical claims are accurate and the framing is useful.

### Nature Machine Intelligence: "Densing Law of LLMs" (2025)
- **Link**: https://www.nature.com/articles/s42256-025-01137-0
- **Key content**: Capability density (capability per parameter) of open-source LLMs doubles every 3.5 months. Parameter requirements for equivalent performance decrease exponentially.
- **Assessment**: Nature-family peer-reviewed journal. Important framing: efficiency is improving even if raw frontier capability growth slows.

### AI Digest / METR: "A New Moore's Law for AI Agents" (March 2026)
- **Link**: https://theaidigest.org/time-horizons
- **Key content**: METR research showing agent time horizons (task length completable at 50% success) doubling every 7 months 2019-2025, accelerating to every 4 months 2024-2025.
- **Assessment**: Based on METR research with described methodology (230 tasks, R²=0.83). Blog/explainer format but cites primary research. This is the most bullish evidence that LLM capability improvement is not yet plateauing on agentic tasks.

### WhatLLM.org: "2025 AI Year in Review" (Dec 2025)
- **Link**: https://whatllm.org/blog/ai-2025-year-in-review
- **Key content**: Comprehensive review. "Test-time compute is the new scaling law." 280x inference cost reduction 2022-2025. DeepSeek V3.2 at $5.57M training cost. Open-source achieves parity with proprietary at 10x lower inference cost.
- **Assessment**: Industry journalism, data-driven. Uses Stanford AI Index, McKinsey, MIT research as sources. Non-peer-reviewed but well-sourced.

### Treehugger: "How GM Invented Planned Obsolescence" (2018)
- **Link**: https://www.treehugger.com/how-planned-obsolescence-began-4856701
- **Key content**: Sloan's 1920s pivot from technical improvement to annual model refreshes driven by market saturation. Ford's resistance ("one model, good enough") cost him the market.
- **Assessment**: Popular article drawing on Gary Cross (Penn State historian) and Jamie Kitman (Automobile magazine). Not scholarly but captures the historical consensus accurately.

### Liso et al. (2023): "Semiconductors' miniaturization through time: from Moore's to Eroom's Law?"
- **Link**: Nanotechnology Materials and Devices Conference (Semantic Scholar)
- **Key content**: R&D costs for semiconductor miniaturization are themselves following Eroom's Law — rising faster than the gains. The cost to produce leading-edge nodes grows exponentially.
- **Assessment**: Conference paper, minimal citations. Interesting observation but not yet established in the literature.

### Ziegler & Trancik (2021), Energy & Environmental Science
- **Link**: https://pubs.rsc.org/en/content/articlehtml/2021/ee/d0ee02681f
- **Key content**: MIT study re-examining Li-ion battery improvement rates. Uses multiple datasets; Wright's Law (cost falls with cumulative production) fits better than Moore's Law. Energy density improvement ~5-8%/year, slow and steady.
- **Assessment**: High-quality peer-reviewed source. MIT/Santa Fe Institute. Useful as a counter-model to exponential technological improvement assumptions.

### HighSpeedInternet.com / Telecompetitor (2025)
- **Link**: https://telecompetitor.com/data-shows-broadband-providers-speed-growth-slowing-highspeedinternet-com
- **Key content**: Broadband speed improvement rate fell 58% in 2024. Average speed 214 Mbps (2024) vs 196 Mbps (2023) — 19% gain vs. 37% in the prior year.
- **Assessment**: Industry market research. Concrete data point on "good enough" demand saturation.

---

## My Position on the Best Fit Analogy

The Moore's Law / semiconductor analogy is the best structural fit for the LLM situation in 2024-2026 — but the pharma/Eroom's Law analogy is the most dangerous warning sign that deserves more attention.

Here is why the semiconductor analogy wins: the mechanism is almost identical. A single powerful scaling law (Dennard; pre-training scaling) drove exponential improvement for ~30 years (semiconductors: 1974-2004; LLMs: the GPT-2 era began serious scaling around 2018, so roughly 5-6 years). The law began failing, not suddenly but gradually. The industry maintained optimistic narratives for 3-5 years while pivoting internally to alternative progress vectors (multi-core, chiplets; test-time compute, specialization). Annual release cadence continued. Benchmark gaming (node renaming; MMLU saturation + new benchmarks) sustained the appearance of progress. The most consequential innovations shifted from "faster single-core performance" to "better performance per dollar in the right task" — exactly the story of efficient open-source models and specialized fine-tuned LLMs.

The critical question is where we are in the semiconductor timeline: 2004 (Dennard just broke, multi-core just starting, 15 more years of meaningful progress ahead) or 2016 (tick-tock retired, heading into genuine stagnation). The METR agent time-horizon data suggests we're closer to 2004 — a new scaling vector with real runway. But this should not be confused with the *old* scaling law working.

The Eroom's Law warning deserves amplification. The "better than the Beatles" problem is real and underappreciated in AI discourse: GPT-4 is the existing back catalogue, free or nearly free. Any new model must beat it on tasks that matter, while GPT-4 handles most commercial use cases adequately. This creates a rising bar effect that will eventually become as binding as regulatory ratchet in pharma. The "throw money at it" tendency is plainly visible in AI capital allocation. The "brute force-basic research bias" maps directly to the bet on scale alone. These are structural forces, not contingent ones, and they suggest the Eroom's Law dynamic is already operating even if the explicit productivity halving isn't yet visible in LLM output.

What the aviation analogy adds that the others miss: *regulation can be the inflection point that freezes the trajectory*. The 1973 supersonic ban stopped aviation speed progress more effectively than any physics limit. AI safety regulation, liability regimes, or export controls could similarly freeze LLM capability development at a specific level — not because the physics won't allow further progress, but because the regulatory environment makes developing it commercially unviable or legally risky.

What the automotive Sloan model adds: *marketing cadence can indefinitely outlast technological cadence*. Even in a genuine stagnation, the commercial machinery of model releases, press events, benchmark announcements, and ecosystem updates can continue. Users may not be able to distinguish between a genuine capability improvement and a well-marketed incremental update. This suggests the *external* cadence of LLM releases may remain high for much longer than the *internal* rate of genuine improvement warrants.

