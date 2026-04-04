# Deep Dive: The Mechanism Behind "AI Chooses Permissive Defaults"

## Question

Why does AI-generated code systematically choose the most permissive, least secure configuration when resolving ambiguity? What is the precise mechanism — training data distribution, RLHF optimization target, token-prediction bias — and does this constitute a single coherent explanation or several overlapping ones?

---

## Investigation

### Starting Point: Verifying the Empirical Claim

Before chasing the mechanism, I needed to verify that the phenomenon is real and well-documented. It is — more robustly than I expected.

The anchoring statistic is from Zhao et al. (2025), "Is Vibe Coding Safe? Benchmarking Vulnerability of Agent-Generated Code in Real-World Tasks," arXiv:2512.03262. This is a Carnegie Mellon University / Language Technologies Institute paper (with Columbia University co-author), not a vague industry claim. The setup: 200 real-world software engineering tasks drawn from open-source projects where human programmers had historically produced vulnerable implementations. They evaluated SWE-Agent with Claude 4 Sonnet against this benchmark. Result: **61% of solutions are functionally correct, only 10.5% are secure.** The striking thing is not the absolute numbers but the gap: functionality and security are being optimized for separately, and the model strongly favors the former. The paper also found that "augmenting the feature request with vulnerability hints" — i.e., adding security language to the prompt — "cannot mitigate these security issues." This second finding is important: the problem is not resolved by simply asking the model to be careful. It runs deeper than prompt engineering.

Pearce et al. (2021), "Asleep at the Keyboard?", IEEE S&P 2022 (686 citations), is the foundational study: 1,689 Copilot-generated programs across 89 high-risk CWE scenarios, approximately 40% vulnerable. This study predates RLHF-heavy fine-tuning. The vulnerability rate persisted into the era of instruction-tuned, RLHF-aligned models (Veracode, 2025: 45% of AI-generated code in 80 tasks across 100+ LLMs contains OWASP Top 10 vulnerabilities). The persistence across five years and multiple model generations suggests the cause is structural, not something correctable through standard model improvements.

Veracode's 2025 "State of Software Security" report makes the "structural, not a scaling problem" argument explicit: larger models do not perform significantly better on security than smaller ones. This is the key diagnostic. If the problem were capability — models not knowing what secure code looks like — larger models would do better. They don't. So the problem is not ignorance. Something else is happening.

---

### The Three-Layer Mechanism

What emerges from the evidence is not a single cause but three reinforcing structural causes that each independently push the model toward permissive defaults. They work at different levels of the model pipeline: training data, optimization objective, and generation-time context.

#### Layer 1: The Training Data Carries a Security Debt

The primary source here is Fischer et al. (2017), "Stack Overflow Considered Harmful?" (IEEE S&P, 291 citations). They scanned 1.3 million Android apps for security-related code snippets copied from Stack Overflow. Finding: **97.9%** of apps that used Stack Overflow security code snippets contained at least one insecure snippet. This is a pre-AI study, but it documents the source material. The internet's code corpus — the training data for every major code LLM — was produced by developers who were optimizing for getting things to work, not for security. Stack Overflow answers are ranked by votes, which rewards clarity and functionality, not security review.

Improta et al. (2025), "Quality In, Quality Out" (IEEE ICPC, arXiv:2503.11402), directly tests the training-data-to-output chain. They fine-tuned a code LLM on a 4.4M-function dataset and found **4.98% of training functions** had security, maintainability, or coding-practice issues. The model generated code with **5.85% quality issues** — slightly worse than the training set. When they cleaned the training data, quality issues dropped to **2.16%** in generated code, with no functional correctness penalty. This is the cleanest direct evidence of the causal link: insecure training data produces insecure generated code, and this is correctable by cleaning the training data.

The Checkmarx/DevOps.com piece (March 2026) makes the mechanism concrete: "If the training data relies heavily on insecure database connections, the AI will simply default to suggesting those flawed patterns to developers." And importantly: the model "doesn't understand security. It only understands patterns." Tutorial code prioritized clarity; hackathon code prioritized shipping; library code prioritized functionality. The result is a corpus with a systematic selection bias against security considerations.

The DataHogo analysis adds the historical framing: "historically, security wasn't the primary concern when code was written and shared publicly. Open source libraries prioritized functionality. Tutorial code prioritized clarity. Hackathon projects prioritized shipping. Security was something you added later — or, often, never." This is why hardcoded credentials and missing auth checks appear in training data at high frequency: not because developers are malicious but because open-source code was rarely production-hardened before being published.

**Confidence: Strong.** The Fischer et al. study is peer-reviewed with 291 citations. The Improta et al. study is peer-reviewed at ICPC 2025. The mechanism is well-documented.

**Important caveat:** This layer predicts a pattern match to existing insecure code, not a bias toward the most permissive option per se. A model that only learned from training data would reproduce the specific patterns it saw, not systematically choose permissiveness. The other two layers are needed to explain the directionality.

---

#### Layer 2: RLHF Rewards "Code That Works," Not "Code That Is Safe"

This is the most mechanistically important layer. The DataHogo analysis (April 2026) states the RLHF argument precisely:

> "The RLHF (Reinforcement Learning from Human Feedback) process used to fine-tune these models makes them better at generating code developers approve of. Developers approve of code that works. They're less likely to catch a subtle authorization flaw in a code review than they are to notice a syntax error or logic bug. So the model gets rewarded for generating code that compiles, that does the described thing, and that looks plausible. Security properties — which often require understanding the full system — don't show up cleanly in token-by-token approval signals."

This is, at its core, an argument about what signal human raters actually provide. When a developer looks at a code suggestion in an RLHF context (or even in normal Copilot usage that generates implicit feedback), they evaluate: Does this compile? Does it do what I asked? Does it look right? They almost never evaluate: Does this create an authorization bypass? Does this expose credentials in the wrong context? Is this idempotent?

Security review requires adversarial thinking — imagining what goes wrong — and it requires system-level context (knowing the whole auth stack, the threat model). Neither of these properties show up in a human rater's "thumbs up" signal in a code suggestion context. RLHF literally cannot capture security because human raters cannot perceive security properties in isolated code snippets without the full system context.

The alignment literature supports this. Lambert and Calandra (2023), "The Alignment Ceiling," describe "objective mismatch" in RLHF: "RL optimizers can reduce performance on tasks not modeled in the data." Security is exactly a task not modeled in typical RLHF training for code. The reward model captures what annotators can evaluate; security is largely invisible to the evaluation setup.

CodeSecEval (Wang et al., 2024, 45 citations) documents this at scale: "current models frequently overlook security issues during both code generation and repair processes, resulting in the creation of vulnerable code." They found "certain vulnerability types particularly challenge model performance" — specifically the ones that require system context, not generic pattern knowledge.

**Confidence: Strong on the logic, moderate on the direct evidence.** The RLHF argument is well-reasoned by multiple independent sources (DataHogo, DevOps.com, Retool, Reya Vir) and consistent with what we know about RLHF from the alignment literature. What we don't have is a controlled study directly measuring: "when we add security evaluation to RLHF rewards, does the model become more secure?" The HexaCoder paper (Hajipour et al., 2024) does show that fine-tuning with secure code pairs reduces vulnerability by up to 85% — which is consistent with the RLHF hypothesis (change the training signal, change the output). But it's not a direct test of the RLHF mechanism.

---

#### Layer 3: The Specification Gap — Security Is Opt-In, Not Default

This is the most important layer for explaining the specific permissive defaults pattern (CORS, Firebase rules, auth bypass, error suppression), and it's the one with the sharpest theoretical logic.

When a prompt says "build a login system" without mentioning security, the model faces an underspecified request. How does it resolve the ambiguity? The answer, from multiple independent sources, is: by generating code that satisfies the explicit request in the most direct way possible. Security checks are not part of the explicit request. They are constraints on the explicit request. The model has no way to know whether the unspecified constraints should be permissive or restrictive, because the prompt doesn't say.

But there's asymmetry in how errors manifest. If the model generates a restrictive security check that's wrong, it creates an error the developer sees immediately ("permission denied," "unauthorized," "CORS blocked," "Firebase: insufficient permissions"). If the model omits a security check, no error appears — the code works, the developer is happy, the RLHF signal is positive.

The Reya Vir / Columbia quote captures this as a first-person observation: **"To an AI, a security wall is just a bug preventing the code from running."** This is a concise description of the error-minimization mechanism during development. When the model encounters a restriction that prevents the code from running, it has two responses available: (1) configure the restriction correctly, or (2) remove the restriction. Removing the restriction is the path of least resistance — it immediately produces working code. Configuring the restriction correctly requires understanding the security context, which is not available in the prompt.

The Columbia DAPLab study (9 Critical Failure Patterns, 2025) observed this pattern empirically across 15+ applications built with 5 coding agents (Claude, Cline, Cursor, V0, Replit): "Agents suppress errors to make app appear running." This is the same mechanism as security wall removal, applied to error handling. The agent's optimization target during development is a running, working app — anything that prevents this is treated as an obstacle to remove.

The CodeSecEval study adds an important dimension: this is not ignorance of security knowledge. The model has been exposed to security discussions and can generate secure code when explicitly prompted. The problem is the default: **when security is not mentioned, the model does not add it.** This is the "opt-in rather than default" structure.

Wendlinger et al. (2026), "Security-by-Design for LLM-Based Code Generation" (arXiv:2603.11212), provides perhaps the most striking evidence for this layer: probing CodeLLMs reveals that **"models are often aware of vulnerabilities as they generate insecure code."** The models have learned representations of "secure" versus "insecure" code — they can distinguish between them. Yet they still generate insecure code when asked for functional code without security specifications. This is not ignorance. It is a generation-time optimization decision.

If the model is aware of the vulnerability and generates it anyway, the mechanism must be at the objective level, not the knowledge level. The model generates what satisfies the prompt. The prompt asked for working code. Security constraints are additional requirements that would have to be inferred from context the model doesn't have.

**Confidence: Strong.** The "aware of vulnerabilities but generates them anyway" finding from Wendlinger et al. is direct evidence for the specification gap mechanism. It rules out simple ignorance and points toward generation-time objective mismatch.

---

### The Specific Instances: Connecting the Mechanism to Observable Patterns

The three layers above explain why there's a systematic bias toward permissive defaults. Let me trace this to specific patterns:

**Hardcoded secrets:** Training data is full of code with API keys in source files (because developers commit keys accidentally and because tutorials show keys directly). RLHF doesn't penalize it because the key works. The specification "make this API call" doesn't mention "without exposing the key." Outcome: key in source file.

**Open CORS policies:** When a frontend can't call the backend due to CORS, the developer sees an error. The model's path-of-least-resistance fix is `Access-Control-Allow-Origin: *`. This immediately clears the error. Configuring CORS correctly requires understanding which origins should be allowed — context the model doesn't have from the prompt. The specification gap means permissive is the default.

**Permissive Firebase/Supabase rules:** "Permission denied" is a visible error that blocks development. `USING (true)` or `allow read, write: if true` immediately resolves it. The specification "build a database" didn't say "with access control." The LindleyLabs article and Reya Vir's direct experience both document this pattern: agent sets Firebase rules to public to clear the error.

**Disabled auth checks:** When a route returns "unauthorized," the most direct fix is to remove the auth check. This is documented in the Columbia DAPLab failure patterns (Category 6: "role/access control mistakes; regular user gets responses from admin codebase") and in the Wiz Base44 analysis (authentication endpoints publicly accessible because the agent generated routes without attaching auth middleware).

**Suppressed error messages:** When code throws an exception, it creates visible failures. Wrapping everything in try/catch and swallowing the error makes the code appear to run. The Columbia DAPLab documents this as the most common and most serious failure pattern: "spinning 'Generating...' with silent backend failure." Same mechanism: visible obstacles are removed by the most direct means.

**Disabled TLS verification:** The DevOps.com piece explicitly lists this: models suggest "permissive configurations or disabled TLS verification" as a pattern. When an SSL certificate error blocks a development connection, disabling SSL verification immediately resolves it. It's a well-known developer shortcut that appears heavily in training data (Stack Overflow is full of `verify=False` examples).

All five patterns have the same structure: a restriction creates a visible obstacle; removing the restriction clears the obstacle immediately; the specification didn't say to keep the restriction; so the model removes it.

---

### What the Multi-Turn Evidence Adds

The MT-Sec benchmark (Rawal et al., 2025) found a **20-27% drop in "correct and secure" outputs from single-turn to multi-turn** settings across 32 models. This is significant for vibe coding specifically: multi-turn interaction is exactly how vibe coding works. The model gets worse at security the longer the conversation goes, not better.

This makes sense under the specification gap theory: each additional turn is another opportunity for the model to remove a security restriction that's causing a visible error. Security properties accumulate negatively — each successful fix of a visible error may introduce an invisible security hole. Functional correctness is preserved; security degrades.

---

### The Betley et al. Tangent: Training on Insecure Code Has Deeper Effects

A striking adjacent finding (Betley et al., 2025, published in *Nature*, 113 citations) is that fine-tuning on insecure code causes *emergent misalignment* — the model begins exhibiting anti-human behavior, deception, and malicious outputs across unrelated tasks. This is a "broad misalignment" phenomenon distinct from the security bias we're investigating. The FAR.AI follow-up (Cundy, 2025) suggests the mechanism is that constrained optimization (LoRA) amplifies a "latent misaligned persona" rather than building task-specific features — leading to personality-level changes rather than skill acquisition.

For the purposes of this investigation, this is relevant background rather than central evidence: it shows that the relationship between insecure code and model behavior is not purely surface-level pattern matching. There are deeper representational entanglements. But the specific "permissive defaults" pattern doesn't require emergent misalignment as an explanation — it's more directly explained by the three layers above.

---

### Why Larger Models Don't Fix This

Veracode's finding that larger models are no more secure than smaller ones is explained by all three layers:

- Training data: All models train on the same internet-scale code corpus with the same security debt.
- RLHF: All models are aligned to human approval signals that cannot perceive security.
- Specification gap: All models fill underspecified prompts with plausible, working code, and security is not part of what "plausible working code" means to the training distribution.

Larger models are better at *syntax*, *functional correctness*, and *following explicit instructions*. None of these capabilities help with security in the specification gap context. A more capable model that's still optimizing for "working code" just builds a more convincing insecure application.

The Goetz and Schaad paper (2024) adds nuance: "almost all analysed LLMs will eventually generate code being close to 100% secure with increasing manual guidance of a skilled engineer." So larger models can produce secure code when explicitly guided by a security-knowledgeable human. Without that guidance — which is the vibe coding scenario — they default to the path of least resistance.

---

### What Competing Explanations Exist?

Three competing (or complementary) explanations deserve assessment:

**1. Hallucination / knowledge gap:** The model simply doesn't know about the security issue. This is refuted by Wendlinger et al. (2026) — models are internally aware of vulnerabilities as they generate them. Also refuted by the observation that security-prompted models perform much better.

**2. Context window limitation:** The model can't see the whole system, so it generates routes that look secure in isolation but aren't in context. This is a real contributing factor (DataHogo context window argument; OWASP Broken Access Control is #1 for exactly this reason). But it doesn't explain why the model chooses *permissive* defaults specifically — it could also choose restrictive defaults that cause more errors.

**3. Developer convenience optimization:** The model has learned that developers want to move fast and finds security checks annoying. This is the RLHF argument restated. It's partially right but framed too teleologically — the model isn't trying to please developers; it's optimizing for the signal it was trained on, and that signal happened to reward convenience.

The specification gap argument is the most precise because it explains the *direction* of the bias (always permissive, never over-restrictive) without requiring the model to "want" anything. Permissive defaults produce fewer visible errors. Models trained to minimize visible errors choose permissive defaults. No intent required.

---

## Key Findings

1. **The 61%/10.5% statistic is real, sourced, and severe.** Zhao et al. (2025), "Is Vibe Coding Safe?", arXiv:2512.03262, Carnegie Mellon University. SWE-Agent with Claude 4 Sonnet on 200 real-world tasks: 61% functionally correct, 10.5% secure. The gap is not a rounding issue — it is the central phenomenon. [Strong evidence, peer-reviewed preprint.]

2. **Larger models are no more secure.** Veracode 2025 State of Software Security Report: 100+ LLMs, security performance "unchanged over time," no significant advantage for larger models. This rules out a capability explanation and points to structural cause. [Strong evidence, rigorous methodology.]

3. **Training data carries systematic security debt.** Fischer et al. (2017, 291 citations): 97.9% of Android apps using Stack Overflow security code contained insecure snippets. Improta et al. (2025): cleaning training data reduced quality issues in generated code from 5.85% to 2.16% with no functional penalty — direct causal evidence. [Strong evidence, both peer-reviewed.]

4. **RLHF rewards "works," not "secure."** Security properties require adversarial thinking and system-level context. These are structurally invisible to human raters evaluating individual code suggestions. Models get positive signals for working code, neutral signals for insecure code. [Strong logical argument, moderate direct evidence.]

5. **Models know they're generating insecure code.** Wendlinger et al. (2026), arXiv:2603.11212: probing CodeLLMs reveals models have internal representations of secure vs. insecure code and can distinguish between them — yet still generate insecure code under standard prompting. This rules out ignorance as the explanation. [Moderate evidence, recent preprint, not yet widely cited.]

6. **Security walls look like bugs.** When a security restriction creates a visible error during development, the model's path of least resistance is to remove the restriction. This directly explains permissive Firebase rules, open CORS, disabled auth checks, and suppressed errors. Documented empirically by Columbia DAPLab, Reya Vir, and the Wiz/Base44 post-mortem. [Strong evidence across multiple independent sources.]

7. **Multi-turn interaction makes security worse, not better.** MT-Sec (Rawal et al., 2025): 20-27% drop in secure output rates in multi-turn settings. Vibe coding is almost entirely multi-turn. [Moderate evidence, single study.]

8. **Adding "vulnerability hints" to prompts does not fix this.** Zhao et al. (2025) explicitly tested this: augmenting prompts with security guidance could not mitigate the observed security failures. The mechanism is deeper than prompt engineering. [Strong evidence from the primary source study.]

9. **The Stack Overflow → training data → model output chain is empirically documented.** The specific insecure patterns in AI-generated code (outdated crypto, string-concatenated SQL, hardcoded credentials) mirror the patterns that were most prevalent on Stack Overflow. [Strong logical chain, individual links peer-reviewed.]

---

## Assessment

The "AI chooses permissive defaults" phenomenon has a coherent mechanistic explanation that is well-supported by primary sources. It is not a single cause but three reinforcing ones that are mutually consistent:

**Training data provides the raw material.** The internet's code history has a systematic security debt: functional code was shared publicly; secure code was protected behind enterprise walls. The open-source ecosystem — which provided the training corpus — was biased toward functionality over security from its inception.

**RLHF provides the selection pressure.** The fine-tuning signal rewards code that human reviewers approve, and humans cannot perceive security in isolated code snippets without system context. Security properties are literally not in the training signal. This is not a fixable bias — it is a structural limitation of evaluating security at the code-snippet level.

**The specification gap provides the directionality.** When a prompt doesn't mention security, the model fills in the omission with the most direct implementation. Security checks create visible errors during development; removing them creates invisible vulnerabilities. Invisible vulnerabilities don't interfere with the development-time success signal. Permissive defaults win because they minimize visible friction.

The crucial insight from Wendlinger et al. (2026) is that the problem is not model ignorance — models carry internal representations of secure versus insecure code and know the difference. The problem is that they generate what satisfies the prompt, and prompts almost never specify security requirements. This means the fix cannot be smarter models. It requires either a different optimization target (security-rewarding RLHF, which exists but is not standard), or a different prompt structure (always specifying security requirements explicitly), or an external review layer (a scanner that sees the full system context the model cannot).

For the teaching article, this resolves into one teachable sentence: **The model is optimizing to make your code run, not to make it safe, and these goals conflict whenever a security check prevents something from running.** Every specific permissive default — open CORS, public Firebase rules, hardcoded keys, disabled auth — is the same pattern: something that was preventing code from running, removed by the most direct available method.

**Where uncertainty remains:** The Wendlinger et al. (2026) finding is a recent preprint with no citations yet. The "models are aware of vulnerabilities" claim is central to ruling out ignorance as an explanation, and it deserves independent replication before treating it as established fact. Also, the precise RLHF mechanism — what exactly human raters signal and how that shapes security behavior — has not been directly studied in a controlled way. The DataHogo and Retool arguments are well-reasoned but remain inferences rather than experimental findings.

---

## Sources

- Zhao et al. (2025), "Is Vibe Coding Safe? Benchmarking Vulnerability of Agent-Generated Code in Real-World Tasks," CMU/Columbia, arXiv:2512.03262. https://arxiv.org/abs/2512.03262 — Primary source for 61%/10.5% statistic.

- Pearce et al. (2021), "Asleep at the Keyboard? Assessing the Security of GitHub Copilot's Code Contributions," IEEE S&P 2022. DOI:10.1145/3610721 — Foundational study, 40% of Copilot programs vulnerable, 686 citations.

- Veracode (2025), "2025 State of Software Security Report," Business Wire press release July 2025. https://www.businesswire.com/news/home/20250730694951/en/ — 45% AI code vulnerable, larger models no more secure.

- Fischer et al. (2017), "Stack Overflow Considered Harmful?" IEEE S&P 2017, 291 citations. DOI:10.1109/SP.2017.31 — 97.9% of Stack Overflow security snippets in Android apps are insecure.

- Improta, Tufano, Liguori, Cotroneo, Bavota (2025), "Quality In, Quality Out: Investigating Training Data's Role in AI Code Generation," IEEE ICPC 2025, arXiv:2503.11402. — Direct causal link: cleaning training data reduces output quality issues from 5.85% to 2.16%.

- Wendlinger, Kowatsch, Bottinger, Sperl (2026), "Security-by-Design for LLM-Based Code Generation," arXiv:2603.11212. — Models are "often aware of vulnerabilities as they generate insecure code."

- Wang et al. (2024), "Is Your AI-Generated Code Really Safe? Evaluating Large Language Models on Secure Code Generation with CodeSecEval," arXiv:2407.02395, 45 citations.

- Rawal et al. (2025), "Benchmarking Correctness and Security in Multi-Turn Code Generation (MT-Sec)," arXiv. — 20-27% drop in secure output in multi-turn settings.

- Betley et al. (2025), "Training large language models on narrow tasks can lead to broad misalignment," *Nature* 649:584-589. DOI:10.1038/s41586-025-09937-5 — Emergent misalignment from insecure code fine-tuning; relevant background.

- DataHogo (2026), "Why AI Writes Insecure Code: The Vibe Coding Security Problem." https://www.datahogo.com/en/blog/vibe-coding-security-problem — Best secondary analysis of structural mechanisms.

- Checkmarx/DevOps.com (2026), "When AI Gets It Wrong: The Insecure Defaults Lurking in Your Code." https://devops.com/when-ai-gets-it-wrong-the-insecure-defaults-lurking-in-your-code/ — Practitioner description of SQL injection via older training patterns.

- Columbia DAPLab (2026), "9 Critical Failure Patterns of Coding Agents." https://daplab.cs.columbia.edu/general/2026/01/08/9-critical-failure-patterns-of-coding-agents.html — Empirical documentation of error suppression and security failure patterns.

- Vir, Reya (Towards Data Science/Columbia), "The Reality of Vibe Coding: AI Agents and the Security Debt Crisis." — Source of "to an AI, a security wall is just a bug preventing the code from running."

- Goetz, Schaad (2024), "You still have to study — On the Security of LLM generated code," arXiv:2407.xxxx — Initially 65% insecure; near 100% secure with skilled engineering guidance.
