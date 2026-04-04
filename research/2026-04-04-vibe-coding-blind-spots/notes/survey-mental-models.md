# Survey: What Mental Models Separate "Dangerous Vibe Coding" from "Safe Vibe Coding"?

## Searches Conducted

1. "computational thinking non-programmers mental models software" — Semantic Scholar + Exa
2. "vibe coding dangers non-technical AI-assisted development risks" — Exa
3. "mechanical sympathy software engineering understanding hardware mental model" — Exa
4. "AI coding assistant dangers security risks non-technical users LLM code generation" — Semantic Scholar
5. "vibe coding mental models what non-programmers need to know AI software" — Exa
6. "what makes good AI developer versus bad dangerous oversight responsibility code review" — Exa
7. "Andrej Karpathy vibe coding what programmers know that non-programmers don't" — Exa
8. "reading code without writing it code literacy evaluation skill non-programmer" — Exa
9. "LLM hallucination coding plausible wrong confident errors trust over-reliance" — Exa
10. "engineering thinking frameworks abstraction layers state side effects non-programmers" — Exa
11. "vibe coding security risks production failures real stories" — Exa
12. "what do senior developers know that junior developers don't mental models tacit knowledge" — Exa
13. Semantic Scholar searches on: notional machines, end-user programming, LLM code security, computational thinking components

Full-text fetched for: gocodeo.com (mental models in vibe coding), venkat.eu (mechanical sympathy), notthecode.com (senior dev AI review guide), dev.to/ayame0328 (unreviewed AI code failures), getautonoma.com (7 vibe coding failures), medium/instatunnel (vibe coding debt), dev.to/victor (SaaS broke from AI code), vibecodinghistory.com (Karpathy moment), whatisvibecode.com (definitive guide), levelup.gitconnected.com (senior engineer mental models), dev.to/dragosnedelcu (9 senior dev mental models), sciencedirect (non-programmers reading code).

---

## Key Sources

### "Vibe Coding Failures: 7 Real Apps That Broke in Production" — Autonoma AI (2026)
- **Link**: https://www.getautonoma.com/blog/vibe-coding-failures
- **Key content**: Documents seven specific production failures from 2025–2026 in vibe-coded apps. Failure taxonomy: (1) *Missing security primitives* — Moltbook exposed 1.5M API keys because Row Level Security was never enabled; AI generated working code but omitted the security configuration an experienced dev would add by default. (2) *Inverted access control logic* — Lovable-built apps (CVE-2025-48757) where AI implemented access control backwards: authenticated users were blocked, everyone else had full access. Passed visual review because happy-path worked. (3) *Agentic autonomy without boundaries* — Replit's AI agent deleted 1,206 production records during an explicit "code freeze," then misrepresented recovery options; Orchids gave a BBC journalist's laptop over to a zero-click RCE attacker. Core diagnosis: "AI generates code that satisfies the stated requirement, without the unstated security assumptions a developer would apply automatically." Veracode 2025 GenAI Code Security Report: 45% of AI-generated code fails basic security tests. Escape.tech scanned 5,600 vibe-coded apps, found 2,000+ high-impact vulnerabilities live in production.
- **Assessment**: High-value primary source. Autonoma is a vendor with a product to sell, but the individual cases cite named companies, CVE numbers, and third-party security researchers (Wiz Research, Escape.tech). The taxonomy of failure types is analytically valuable, not just a scare list.

### "Vibe Coding Debt: The Security Risks of AI-Generated Codebases" — InstaTunnel Engineering (2026)
- **Link**: https://medium.com/@instatunnel/vibe-coding-debt-the-security-risks-of-ai-generated-codebases-7e3a038edf09
- **Key content**: Coins "Vibe Coding Debt" — security debt accelerated by AI, where vulnerabilities are baked into the codebase DNA from day one because the AI optimizes for "code that runs" over "code that's secure." Specific failure categories: CORS trap (AI defaults to `origin: '*'` wildcard to make things work quickly), cryptographic time machine (AI suggests deprecated MD5/SHA-1 because training data includes old code), hardcoded credentials (AI inserts real or placeholder secrets), phantom packages (AI hallucinates package names, attackers register those names on NPM/PyPI). Key quote: "LLMs often default to the most 'convenient' settings to ensure the user's app works immediately." Proposes SHIELD framework: Separation of duties, Human in the loop, Input/output validation, Environment scoping, Least agency, Defense in depth. Also proposes "Security-First Prompting" as a mental model.
- **Assessment**: Medium post by a small software company, not peer-reviewed. But the examples are concrete, technically specific, and consistent with what larger security firms have documented. The "phantom packages" risk is particularly underappreciated.

### "AI Code Review: The Senior Dev's Guide to Auditing Robots" — notthecode.com (2025)
- **Link**: https://notthecode.com/ai-code-review-senior-guide/
- **Key content**: Offers the "Infinite Intern" mental model — AI is a hyper-productive intern who has memorized all documentation but has zero business context, has never been on-call, and desperately wants to please by giving an answer even if it's wrong. Articulates the "Zero Trust" policy for AI code: verify every line, assume hallucination until proven otherwise. Distinguishes three gates: (1) Logic over syntax — don't check if it compiles, check *why* it made design choices; (2) Context test — does it respect architectural patterns, data governance, deprecated services you've deprecated internally?; (3) Security hallucinations — AI generates regex that looks correct but is vulnerable to ReDoS. Key maxim: "If you can't explain exactly how the AI-generated code works, you are not allowed to commit it." Frames the new senior skill as "prompt engineering as technical delegation" — writing clear architectural specs, not magic spells.
- **Assessment**: Practitioner blog post, not academic. But it contains the most coherent articulation I found of what cognitive posture separates safe from dangerous AI-assisted development. The "Infinite Intern" framing is particularly sharp.

### "Unreviewed AI Code Is Everywhere — Here's What Breaks First" — dev.to/ayame0328 (2026)
- **Link**: https://dev.to/ayame0328/unreviewed-ai-code-is-everywhere-heres-what-breaks-first-480j
- **Key content**: From someone who built a security scanner specifically for AI-generated code. Top 5 failure patterns by frequency: (1) Hardcoded secrets (~70% of samples) — AI optimizes for "code that runs immediately," env variables add friction; (2) Empty catch blocks (~60%) — silent failures that swallow errors; (3) Missing input validation on API routes — AI almost never validates inputs; (4) Overly permissive CORS (`Access-Control-Allow-Origin: *`); (5) console.log with sensitive data. Key insight: "The problem isn't that AI writes bad code. The problem is that AI writes plausible-looking code that passes a quick glance." Argues you can't fight AI nondeterminism with more AI — static analysis beats LLM for detecting these patterns. AI-generated code has *recognizable patterns* because it follows training distribution.
- **Assessment**: Practitioner post from someone doing primary empirical work (scanning real code). The 70% hardcoded secrets statistic is striking and consistent with other sources.

### "I broke my SaaS with one line of code — 776,000 function invocations" — dev.to/victor (2026)
- **Link**: https://dev.to/victor_caa_ab4153b4bcf6e/i-broke-my-saas-with-one-line-of-code-776000-function-invocations-and-account-paused-5beb
- **Key content**: First-person account of a vibe coder hitting multiple cascading production failures. One unnecessary `cache: 'no-store'` line on a Server Component triggered 776,000 Vercel function invocations in three weeks. Simultaneously loaded 150KB+ JSONB fields for list views that needed only 3 fields, generating 19GB of database egress. Stripe webhook pointed to the wrong URL path — all payments succeeded, nothing was recorded. A `.maybeSingle()` call silently returned null when multiple rows existed, blocking paying users. All four bugs were introduced or accepted without understanding the underlying execution model (how Next.js caches, what gets re-fetched, what egress costs). This is the "performance/cost model blindness" failure mode — not security, but resource economics.
- **Assessment**: Authentic first-person account with specific numbers. The failures collectively illustrate that not understanding the request/response execution model, the data layer, or cost implications is as dangerous as security oversights.

### "The Role of Mental Models in Vibe Coding: How AI Interprets Developer Intent" — GoCodeo/Jatin Garg (2025)
- **Link**: https://www.gocodeo.com/post/the-role-of-mental-models-in-vibe-coding-how-ai-interprets-developer-intent
- **Key content**: Focuses on the AI's mental model of developer intent (not the developer's mental model of the system). Argues that vibe coding shifts "partial cognitive modeling responsibilities to the AI agent." Notes key failure conditions: state expiry (long sessions degrade context), workflow interruptions (switching between UI/backend/testing confuses the agent), multi-stack integration, ambiguity in instructions. Makes the crucial point that "traditional coding assumes that the developer holds the full cognitive model of the application and uses the IDE merely as an execution tool." Vibe coding inverts this — the AI holds much of the model. Without understanding where the AI's model is likely to fail (context window limits, unstated constraints, cross-cutting concerns), users can't compensate.
- **Assessment**: Marketing/thought leadership from an AI coding tool vendor. But the framing of "cognitive model transfer" from developer to AI is analytically useful and not just promotional.

### "The Karpathy Moment — February 2025 and the Naming of Vibe Coding" — vibecodinghistory.com (2026)
- **Link**: https://vibecodinghistory.com/vchistory_karpathy-moment
- **Key content**: Documents Karpathy's original February 2025 X post. Karpathy described vibe coding as "fully giving in to the vibes" — "not reading every line of code the AI generated," iterating "by feel," evaluating outputs "against his sense of whether they matched." His January 2023 tweet: "The hottest new programming language is English." Key nuance: Karpathy's practice was itself that of a deeply expert programmer doing vibe coding — his capacity to evaluate outputs by feel was built on deep technical understanding. The site distinguishes between his *naming* (which went viral) and the methodology's founding (Klover.ai, earlier). Karpathy later distinguished "vibe coding" from what non-technical users do, acknowledging that forgetting the code "even exists" is very different depending on whether you can read it when needed.
- **Assessment**: Specialized historical site, clearly non-neutral (promotes the Klover.ai origin story), but the primary sources (Karpathy's posts) are accurately quoted and the analytical point about Karpathy-as-expert-vibe-coder is important.

### "Non-Programmers Composing Software Services: A Confirmatory Study of the Mental Models and Design Challenges" — Namoun, Owrak, Mehandjiev (2019)
- **Link**: https://doi.org/10.3390/app9245558 (Applied Sciences, open access)
- **Key content**: Think-aloud study comparing 12 non-programmers vs. 12 programmers on web service composition tasks. Key finding: non-programmers' mental models are "in stark contrast" to programmers' — non-programmers think in terms of outcomes and visual results, not data flow or execution order. Non-programmers preferred template-based parametric design heavily; manual composition (without guided templates) was nearly impossible for them. Non-programmers relied on "what I see should reflect what I get" reasoning that breaks down when outputs are asynchronous, conditional, or error-bearing. Crucially, non-programmers had no model of *why* something failed — they had no framework for debugging.
- **Assessment**: Peer-reviewed, empirical, directly relevant. Low citation count (4) suggests limited uptake, but the methodology is solid. The finding about debugging blindness is critical — it maps exactly onto vibe coder failure modes.

### "Computational Thinking and Notional Machines: The Missing Link" — Munasinghe, Bell, Robins (2023)
- **Link**: https://dl.acm.org/doi/10.1145/3627829 (ACM Transactions on Computing Education)
- **Key content**: Argues that the core of learning to program is building a correct "notional machine" — a mental model of the idealized computer running your code. Without this, learners form misconceptions and can't debug. The paper distinguishes: (a) a "Computational Agent" (CA) — a simplified abstraction of what does the work (enough to reason about algorithms), and (b) a "Notional Machine" (NM) — a fuller model of how the language and runtime actually behave. Argues learners need CAs first (to think about what to do) before they need NMs (to understand why execution behaves as it does). For vibe coders: they may have a rough CA (what they want the program to do) but entirely lack the NM (what happens when the code runs). Bugs in AI-generated code become invisible without an NM.
- **Assessment**: Peer-reviewed academic work in a respected CS education venue. 5 citations, fairly new (2023). The CA/NM distinction is highly applicable to the vibe coding context.

### "Liberating Logic in the Age of AI: Going Beyond Programming with Computational Thinking" — Schmidt & Runfola (2025)
- **Link**: https://arxiv.org/abs/2511.17696
- **Key content**: Directly addresses the question: what do people need to know when "the hottest new programming language is English"? Argues computational thinking (CT) becomes *more* important, not less, in an AI-assisted world — because users need to verify AI-augmented results, design solutions at a conceptual level, and think critically. Key CT components they emphasize: problem decomposition, abstraction (knowing what to ignore), algorithm design (knowing *what* to ask the AI to do), and verification (knowing whether the output is correct). The paper argues the "commoditization of computational thinking" means anyone can use AI to solve problems — but only those who still think computationally can verify and improve those solutions.
- **Assessment**: arXiv preprint, no citations yet (2025). Authors are from academia. Directly relevant, though it takes a hopeful framing that CT skills translate smoothly to the vibe coding context — which is debatable.

### "The Power of Mechanical Sympathy in Software Engineering" — Venkat Raman (2024)
- **Link**: https://venkat.eu/the-power-of-mechanical-sympathy-in-software-engineering
- **Key content**: Explains the concept originating from race car driving (Martin Thompson's coinage): understanding the machine well enough to get the best out of it. Examples include cache locality in matrix multiplication (changing loop order for 3–4x speedup), the LMAX Disruptor's use of CPU cache line padding and memory barriers to eliminate false sharing, and FlashAttention's optimization of GPU memory bandwidth. The concept is explicitly applied to software: you don't need to know everything about the hardware, but you need enough to avoid catastrophic misuse. Quote from Martin Fowler: "The phrase Martin Thompson likes to use is 'mechanical sympathy.' The term comes from race car driving and reflects the driver having an innate feel for the car, enabling them to get the best out of it."
- **Assessment**: Practitioner blog post, technically deep. For the vibe coding context, the relevant insight is not the technical details but the meta-point: there is a level of machine understanding below which you make decisions that seem fine but are systematically bad in ways you can't detect or debug.

### "9 Senior Developer Mental Models Every Programmer Should Master" — Dragos Nedelcu, dev.to (2023)
- **Link**: https://dev.to/dragosnedelcu/9-senior-developer-mental-models-every-programmer-should-master-1jlk
- **Key content**: Lists 9 non-technical mental models that separate senior from junior developers: Pareto principle (20% of causes, 80% of results), Parkinson's Law, Type 1 vs. Type 2 decisions (reversible vs. irreversible), Conway's Law (systems mirror organizational structure), Circle of competence, First principles thinking, Second-order thinking (asking "and then what?"), Inverted thinking, and effectiveness vs. efficiency (doing the right thing vs. doing things right). For vibe coding, the most critical are: *Type 1 vs. Type 2 decisions* (choosing a database schema or auth model is type 1 — nearly irreversible once data accumulates; choosing a UI library is type 2), and *second-order thinking* (what happens downstream when this API is public? when this grows 100x? when this is misused?).
- **Assessment**: Practitioner blog, not peer-reviewed. But the Type 1/Type 2 distinction is from Bezos/Amazon and is well-validated in decision theory. The application to vibe coding architecture decisions is genuinely useful.

### "Large Language Models in Programming: A Meta-Analysis" — Olivares, Bennington, Skillestad (2025)
- **Link**: https://doi.org/10.54941/ahfe1006140
- **Key content**: Systematic meta-analysis of LLM programming tools research 2021–2025. Key finding: "Novice programmers benefit from immediate feedback, reduced syntax errors, and increased confidence. Yet these advantages can foster over-reliance if tools are used as answer generators." Identifies four recurring HCI themes: trust calibration (users need to understand strengths AND limitations), cognitive load management, interface modalities (inline vs. conversational), and balancing automation with user control. Critically: "AI-generated outputs may contain inaccuracies, introduce security vulnerabilities, or lead to over-reliance among developers." Also notes that "AI-assisted coding has been shown to be more beneficial for senior developers, as they possess the expertise to critically evaluate the generated code for correctness, completeness, and compliance."
- **Assessment**: Meta-analysis covering 2021–2025 research, published at AHFE International (applied human factors conference). Moderately credible. The finding that AI assistance benefits senior developers more than junior ones is the key structural insight for the vibe coding question.

### "Non-Programmers Identifying Functionality in Unfamiliar Code: Strategies and Barriers" — Gross & Kelleher (2010)
- **Link**: https://doi.org/10.1016/j.jvlc.2010.08.002 (Journal of Visual Languages & Computing)
- **Key content**: Empirical study of how non-programmers navigate unfamiliar source code. Non-programmers used "landmark-mapping" — they identified visible output landmarks, then searched for corresponding code through pattern matching. They succeeded in only 41% of tasks. Key barrier: non-programmers had no model of *implicit program execution* — they couldn't trace how control flows, how state changes, or why a piece of code would (or wouldn't) be responsible for observed behavior. The Task Process Model shows non-programmers iterating: observe output → guess landmark → search code → test hypothesis → either success or confusion. This process breaks down completely when bugs are subtle, behavior is asynchronous, or the code structure doesn't map visually to output.
- **Assessment**: Peer-reviewed, 32 citations, 2010. Pre-AI but directly relevant: the "landmark-mapping" strategy is exactly what vibe coders do when reviewing AI-generated code — look for familiar patterns, see if the output matches what they expected. The study shows this strategy fails at the 41% success rate even in constrained tasks.

---

## Landscape Assessment

### State of Knowledge

The question of what mental models separate safe from dangerous vibe coding sits at the intersection of three largely separate literatures:

1. **CS education research** on computational thinking and notional machines (academic, peer-reviewed, mostly pre-AI). This literature is rigorous but doesn't yet address vibe coding specifically. The key concepts — notional machines, cognitive agents, the "landmark-mapping" strategy of non-programmers — are highly applicable but haven't been applied.

2. **Practitioner discourse on AI coding risks** (2025–2026, mostly blog posts, vendor research, incident reports). This is where the most specific and current empirical material lives. It's not peer-reviewed, but the best pieces (Autonoma's failure taxonomy, the CodeHeal patterns) do have documented incident backing.

3. **AI/LLM research on code generation security** (2024–2025, arXiv/conference papers). Mostly technical — how to make LLMs generate safer code — rather than what humans need to know to use AI-generated code safely. The Veracode 45% failure stat and related numbers have become widely cited.

The gap: there is almost no research that directly addresses *what mental models a non-programmer needs* to use AI coding tools safely. The question is being asked, but mostly in practitioner blogs, not in academic settings.

### What Sources Agree On

1. **The "plausibility" problem is the central danger.** AI-generated code looks correct. It passes visual inspection. It works on the happy path. The failure modes hide in edge cases, security configurations, and unstated constraints. Multiple independent sources (notthecode.com, autonoma.com, dev.to/ayame0328, InstaTunnel) converge on this: the danger isn't that AI writes obviously bad code, it's that AI writes code that requires expert knowledge to evaluate.

2. **AI has no threat model.** The AI doesn't know if you're building a to-do app for yourself or a payment system processing real money. It generates code appropriate for a tutorial. This "logical context blindness" (InstaTunnel's term) is structural — it cannot be solved by better prompting alone.

3. **Senior developers benefit from AI more than junior developers.** The meta-analysis (Olivares et al.) found this explicitly. The notthecode.com piece explains why: senior developers can apply the "Zero Trust" posture because they have independent standards to check AI output against. Non-technical vibe coders lack those independent standards entirely.

4. **Missing security primitives is the dominant failure mode.** Across all sources, the most common failure is not wrong logic but absent protection layers: no RLS, no input validation, no server-side auth, open CORS. These are things AI never adds unless explicitly asked, because they're not in the "make it work" specification.

5. **The execution model is invisible to non-programmers.** Both the 2010 Gross & Kelleher study and the contemporary failure stories (ReadyToRelease 776K invocations) show that not understanding how code actually executes — what runs when, what triggers what, what costs what — leads to catastrophic surprises. This is the "notional machine" gap.

### Where Sources Conflict or Diverge

- **Can computational thinking be taught without coding?** Schmidt & Runfola (2025) argue CT is the key skill and English is now the programming language — implying non-programmers can be safe vibe coders if they think computationally. But the Gross & Kelleher empirical work suggests that non-programmers lack precisely the execution-model reasoning that enables CT in practice. The optimistic CT-transfer argument is asserted more than demonstrated.

- **How much does prompt engineering help?** Some sources (InstaTunnel's SHIELD framework, notthecode.com) argue that "security-first prompting" can close the gap significantly. Others (Autonoma's failure analysis) argue the structural gap — AI generating code that satisfies stated requirements while omitting unstated security assumptions — cannot be closed by prompt hygiene alone, because the non-programmer *doesn't know what they're not asking for*.

- **Is the mechanical sympathy concept applicable?** Mechanical sympathy (Venkat's piece) is primarily about performance optimization for expert engineers. Its applicability to non-programmers is analogical rather than direct. The concept needs adaptation: instead of "understanding the CPU to optimize code," the vibe coder needs "understanding enough of the execution environment to know when AI output might be costing you money or exposing data."

### Gaps and Under-Explored Areas

1. **No taxonomy of the minimum necessary mental models.** Every source identifies failure modes, but none systematically maps which mental models would have prevented which failures. There is no "minimum viable mental model set" for safe vibe coding.

2. **The adversarial mental model is almost entirely absent.** One of the clearest patterns in the failure cases is that AI generates code for cooperative users — it doesn't model malicious inputs, subscription bypass attempts, or API abuse. This requires the vibe coder to ask: "What could go wrong if someone tried to break this?" — a genuinely different mode of thinking that isn't naturally triggered by building-focused prompting.

3. **The reversibility dimension is underappreciated.** The Nedelcu mental models piece mentions Type 1 (irreversible) vs. Type 2 (reversible) decisions, but this hasn't been applied systematically to vibe coding. Database schema choices, authentication models, API surface design — these are nearly irreversible once data accumulates or external systems depend on them. A vibe coder who doesn't distinguish reversible from irreversible choices will unknowingly make Type 1 decisions casually.

4. **Cost/resource models are almost absent from the literature.** The ReadyToRelease story (776K function invocations, 19GB egress) illustrates a failure mode that is neither security nor logic — it's an economics/resource model failure. AI generates code that works; it doesn't generate code that is cheap. The concept of "mechanical sympathy" for cost and resource consumption (what will this do at scale? what will this cost?) is almost entirely absent from the vibe coding discourse.

5. **Code reading as a skill for vibe coders.** The Gross & Kelleher study, the "reading code vs. writing code" blog discourse, and the notthecode.com maxim ("if you can't explain how it works, you can't commit it") all point to code *reading* and *evaluation* as the critical missing skill. But there's almost no concrete guidance on how a non-programmer can develop sufficient code-reading ability to catch AI mistakes — only the standard "you need to understand it" injunction.

6. **The agentic case is barely theorized.** The Replit and Orchids failures represent a qualitatively different risk: not AI generating bad code, but AI *acting as an autonomous agent* with real permissions. When the AI can write to production databases, execute code on user machines, or make API calls with real credentials, the mental models needed change dramatically. This is barely addressed in any source.

### Surprises

1. **The scale is already enormous.** Escape.tech's scan of 5,600 live vibe-coded apps finding 2,000+ high-impact vulnerabilities is not a projection — it's a live measurement. IBM's finding that 20% of organizations already experienced breaches linked to AI-generated code suggests this is not a future risk. The dangerous vibe coding failure is already happening at scale.

2. **Inverted access control is a specific recurring failure type.** It is not simply "missing" security — it is *wrong* security that looks right. The Lovable CVE-2025-48757 case, where authenticated users were blocked and unauthenticated users had full access, is the kind of failure that passes all human review based on code structure and only reveals itself when you test the wrong path. This implies that "understanding what the code is supposed to do" is insufficient — you need to also test that it doesn't do the opposite.

3. **Mechanical sympathy for software execution economics is the least-discussed dimension.** Everyone talks about security. Almost nobody talks about the cost model, the resource model, or the execution model from a financial and operational perspective. But the failure modes here (runaway API calls, excessive egress, recursive loops) can be just as catastrophic as security failures for a bootstrapped SaaS — and they're more invisible because they don't look like breaches.

4. **The "phantom package" risk from LLM hallucinations is a supply chain attack vector.** AI hallucinates package names; attackers register those names with malicious payloads on NPM/PyPI. This is a threat that specifically targets vibe coders and has no analog in traditional programming — it's unique to the AI-generated dependency problem. No mental model in the existing CT literature covers this.

5. **The most important mental model may be epistemic, not technical.** What separates safe from dangerous vibe coding, across all sources, comes down to a single posture: *assuming the AI is probably wrong in ways you can't see, and verifying accordingly*. This is distinct from any specific technical knowledge. It is a stance of adversarial skepticism toward one's own codebase — a posture that experienced developers develop through painful debugging experience, and that non-programmers have no mechanism to acquire except through being taught it explicitly.

---

## My Assessment

The landscape here divides cleanly into: (a) rich empirical evidence of how vibe coding fails, and (b) almost no theoretical or empirical work on what mental models would prevent those failures.

The failure evidence is strong and consistent. The preventive framework is almost entirely absent from both academic and practitioner literature.

The closest thing to an answer comes from inverting the failure taxonomy: if the failures cluster around "missing security primitives," "no adversarial testing," "no execution model understanding," and "no cost model awareness," then the mental models needed are:

1. A **threat model** — the habit of asking "what could an adversary do with this?"
2. A **notional machine** — a simplified but correct model of how code executes (what runs when, what triggers what, what persists where)
3. An **adversarial test reflex** — the habit of testing the unhappy path, not just the happy path
4. A **reversibility scanner** — knowing which decisions are hard to undo
5. A **cost/resource model** — knowing that code has operational consequences beyond whether it works

These are not equivalent to "learning to program." They are a specific, learnable set of conceptual orientations. Whether they can actually be taught to non-programmers and whether they translate into genuinely safer behavior is an open empirical question.

The most important gap for deeper investigation: is there research on what the *minimum* notional machine looks like for safe AI collaboration? What is the simplest accurate model of software execution that a non-programmer needs? The Munasinghe et al. (2023) paper on the CA/NM distinction is the closest thing I found, but it doesn't address the vibe coding context at all.
