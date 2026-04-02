# Deep Dive: The Accommodation Mechanism — From Lewis to Epistemic Violence

## Question

How does the causal chain from Lewis's (1979) accommodation mechanism run through Stalnaker's common ground, the QUD framework, Longino's background assumptions, and Teo's epistemological violence? Where is this chain strongest, where are the weak links, and has anyone built part of it before?

---

## Investigation

### 1. Lewis (1979): The Primary Source

Lewis's "Scorekeeping in a Language Game" (Journal of Philosophical Logic, 8: 339–359) is the foundational text. The paper's TLDR from Semantic Scholar captures its central insight verbatim: "It's not as easy as you might think to say something that will be unacceptable for lack of required presuppositions, and straightway that presupposition springs into existence, making what you said acceptable after all."

The core mechanism: conversations have a *score* — a set of parameters (presuppositions, permissibility standards, salience orderings, among others) that determine what moves are permissible at any point. Like a baseball game, the score is governed by rules. But unlike baseball, the score in a language game has a distinctive property: **it adjusts automatically to make each move acceptable**. If you say something that requires a presupposition P, and P is not already part of the conversational score, P is *accommodated* — added to the score retroactively, so that what was said counts as acceptable play.

Lewis's key example: "The king of France is bald" requires the presupposition that France has a unique king. If that presupposition is absent, the statement would be unacceptable. But in practice, the presupposition *springs into existence* — interlocutors accept it into the common ground without making this acceptance explicit, without debating it, and typically without even noticing.

What makes this automatic? Lewis's answer is structural: the rules of the language game include a general accommodation rule. Because communication requires that utterances be acceptable, and because participants are cooperating to make the conversation work, presuppositions are simply absorbed unless they are explicitly rejected. The default is accommodation; rejection requires an active intervention (what von Fintel 2000 and others call the "Hey, wait a minute" test — participants can object to a presupposition if they notice it and choose to resist, but this is the exception, not the norm).

The *conversational score* includes: (a) presuppositions held in common, (b) permissibility standards (what is allowed to be said), (c) degrees of precision, (d) relative salience of possible referents. Accommodation applies primarily to the presupposition component. The score at any point in the conversation determines what subsequent moves are possible — this is the structural claim that will become important for QUD.

**Confidence: Strong.** This is from the primary text (confirmed through multiple sources including the full PDF at andrewmbailey.com/dkl/Scorekeeping_in_a_Language_Game.pdf and the UChicago teaching copy at semantics.uchicago.edu/kennedy/classes/f09/semprag1/lewis79.pdf).

---

### 2. Stalnaker (1974, 2002): Common Ground as Shared Propositional Space

Stalnaker's "Common Ground" (Linguistics and Philosophy, 2002) develops the framework that Lewis's accommodation operates within. Stalnaker defines common ground as a body of propositions mutually accepted by participants in a discourse. The formal representation is the *context set*: the set of possible worlds compatible with what is mutually accepted. Each successful assertion *restricts* the context set — worlds incompatible with the assertion are eliminated.

Stalnaker's crucial claim: speaker presupposition is a *social* attitude. To presuppose that p is to take it for granted *and* to presuppose that others take it for granted as well. This iterative structure (I know that you know that I know...) is what distinguishes common ground from individual belief. Stalnaker acknowledges that formal models often represent this as simply a set of worlds labeled "the context set," but his deeper point is that common ground is a shared social state — not a property of any individual, but of the conversational dyad (or, by extension, the discourse community).

The update mechanism: when a speaker asserts p, the context set is restricted to p-worlds. When a presupposition is accommodated, the context set is first *expanded* to include worlds consistent with the presupposition, and then the assertion is processed. This is the asymmetry: assertions narrow the common ground; accommodation *enlarges* it first before subsequent narrowing.

Stalnaker himself notes the complication for institutional or extended discourse (picked up in the SEP entry on Common Ground): as audiences scale up and become anonymous, the common ground becomes *de dicto* rather than *de re* — what participants know about what is shared becomes attenuated. The interactive feedback mechanisms that ordinarily keep accommodation in check (someone could say "Hey, wait a minute") are curtailed. This is the first formal signal that accommodation behaves differently in extended institutional discourse.

**Confidence: Strong.** The Stalnaker 2002 paper is available (UChicago teaching copy confirmed as accessible text) and secondary sources (Simons 2003 in Philosophical Studies; multiple SEP and exa_answer confirmations) provide reliable summaries.

---

### 3. The QUD Framework: Roberts, Beaver et al.

Craige Roberts (the foundational QUD framework, cited as Roberts 2012 from NASSLLI lectures, also Roberts et al. 2009) and Beaver, Roberts, Simons, Tonhauser (2017, Annual Review of Linguistics) develop the strongest formal account of how questions structure discourse.

The core QUD concepts:

**At-issue content**: propositions that directly address the current Question Under Discussion. An assertion is *relevant* if and only if its at-issue content constitutes a (partial) answer to the QUD. This is the formal relevance condition.

**Not-at-issue content**: propositions that are accepted into the common ground but do *not* directly address the QUD. Presuppositions, conventional implicatures, and other projective content are not-at-issue: they are backgrounded, taken for granted, and typically cannot be rejected by a simple "No, that's false."

The crucial structural implication: **the presuppositions of the governing QUD are doubly not-at-issue**. When a why-question Q ("Why did P happen?") governs a discourse, the presupposition of Q — namely, that P happened — is not just not-at-issue; it is *constitutive* of the QUD itself. Challenging the presupposition means challenging whether the question is even well-formed, which amounts to proposing a different question entirely. Participants who want to address the QUD must accept its presuppositions as common ground.

Roberts et al. (2009) make the relevance condition explicit: an utterance is relevant to the QUD iff it either directly answers the QUD or raises a subquestion that, when resolved, would help answer the QUD. Questioning the presupposition of the QUD does neither — it changes the subject. The QUD framework thus provides a *formal* account of why presuppositions of governing questions are structurally insulated from challenge within the ongoing discourse.

This is strengthened by the at-issue/not-at-issue distinction in Beaver et al. (2017): "discourse is analyzed in terms of the strategy of inquiry pursued by the interlocutors, and individual utterances are interpreted relative to the question being addressed." When the governing question becomes institutionalized — when a research program, for decades, takes a why-question as its organizing QUD — every utterance in that program is interpreted relative to that question. The presuppositions of the question are simply not the kind of thing that gets answered, addressed, or even raised within that discourse.

**Confidence: Strong.** The Beaver et al. (2017) abstract is directly confirmed. The Roberts et al. (2009) paper is accessible. The structural claim about QUD presuppositions being insulated is well-supported by the formal framework and is explicitly discussed in secondary literature (AnderBois 2013 QUD model lecture notes; Riester et al. 2018 annotation guidelines).

**Important nuance**: The QUD framework is primarily a theory of conversational discourse, not of disciplinary research programs. The extension from conversational QUD to institutional/research-program QUD is an *analogical* move, not a direct application. The claim that a research question functions as a QUD for an entire discipline requires additional argument (see Assessment section).

---

### 4. The Inquisitive Injustice Literature: The Bridge Already Half-Built

A significant finding: the philosophical literature has already partially constructed this chain, under the label "inquisitive injustice."

**Keiser (2021), "The 'All Lives Matter' Response: QUD-Shifting as Epistemic Injustice" (Synthese)**: Keiser shows that QUD-shifting — deliberately replacing one governing question with another — can constitute epistemic injustice. When "Black Lives Matter" raises the QUD "Do Black lives matter?", the "All Lives Matter" response shifts the QUD to "Which lives matter?" — changing the question in a way that buries the original concern. The presuppositions of the original QUD, once displaced, become invisible. This is a direct application of QUD theory to questions of power, harm, and who controls the direction of inquiry.

Keiser's contribution to our chain: it demonstrates that controlling the QUD controls what can be said, what counts as relevant, and what is insulated from challenge. This is the mechanism in operation in real-world discourse.

**Mallory (2025/2026), "Inquisitive Injustice" (Philosophical Studies)**: This paper (published 2025, volume 2026) is the most sophisticated treatment to date. Mallory defines "inquisitive injustice" as a discursive injustice where "a speaker undergoes inquisitive injustice when" their ability to make their question the QUD is obstructed. The paper explicitly draws on formal pragmatics (Lewis, Stalnaker, Roberts), social epistemology, and critical discourse analysis.

Mallory's abstract: "The ability to control the direction of a conversation, which topics are raised, which questions are asked, and which lines of inquiry are followed, is a basic and powerful form of social control... it introduces the category of inquisitive injustice and identifies several underlying structural causes behind it."

Keywords of the Mallory paper: "Question under discussion, common ground, critical discourse analysis, testimonial injustice, discourse topics, presupposition." This paper explicitly links QUD theory to justice, and uses accommodation and common ground as part of its mechanism.

**What the inquisitive injustice literature does *not* do**: Neither Keiser nor Mallory connects to Teo's epistemological violence specifically. Neither discusses research programs or disciplinary inquiry as extended QUDs. Neither analyzes the *content* of the presuppositions (that group differences are deficits) — they focus on the *structural* injustice of who controls the QUD, not on what the QUD presupposes. This is where Teo and Longino are needed.

**Confidence: Strong for Keiser 2021; Strong for Mallory 2025/2026.** Both papers are confirmed to exist and engage with QUD+justice. Mallory is open access (PhilArchive/PhilPapers). Direct PDF content was retrieved but unreadable; the abstract and description are confirmed from multiple sources.

---

### 5. Longino (1990): Background Assumptions and Evidential Relevance

Helen Longino's *Science as Social Knowledge* (Princeton University Press, 1990; 799 citations on Semantic Scholar) develops a philosophy of science that is structurally parallel to the accommodation chain.

Longino's central claim: "Evidential relevance of data is secured instead by background assumptions" (confirmed from PhilArchive summary of secondary literature). More precisely: a piece of data D is evidence for hypothesis H only relative to some background assumption B that connects D to H. Without B, D tells us nothing about H. Background assumptions are the *linking premises* that make evidential relationships hold.

Longino's specific claim about their status: "Background assumptions are the means by which contextual values and ideology are incorporated into scientific inquiry." They are not tested alongside H — they are the framework within which H is tested. They enable the test. This means they are structurally invisible from within the normal practice of the science: you cannot simultaneously test B and use B to test H.

The hormones-aggression example (confirmed as central to Longino's account): studies correlating hormone levels with aggressive behavior require background assumptions linking hormones to behavior in a particular causal way. The assumption is not tested by the data — it is what makes the data relevant. If you question the background assumption, you are questioning whether the data is evidence at all, not just whether H is true.

Crucially: Longino argues that background assumptions can be exposed and criticized — but only through *trans-disciplinary* criticism, from outside the practices that take B for granted. Within a research program that has accommodated B into its operating framework, B is effectively invisible.

**The connection to accommodation**: Longino does *not* use Lewis's terminology. She does not frame background assumptions as accommodated presuppositions. There is no citation of Lewis, Stalnaker, or any philosophy of language in the primary account. However, the structural parallel is exact:

- Lewis: presuppositions spring into existence automatically, making utterances acceptable
- Longino: background assumptions are incorporated into scientific inquiry as its enabling framework
- Lewis: once accommodated, presuppositions are part of the conversational score and shape what moves are permissible
- Longino: once incorporated, background assumptions shape what counts as evidence, which hypotheses are testable, what data is relevant

The connection between "accommodated presupposition" (Lewis) and "background assumption" (Longino) is a *philosophical interpretation* the essay would be making, not an explicit claim in the literature. It is a strong and defensible interpretation, but it needs to be flagged as the essay's own synthesis.

**Has anyone made this connection explicitly?** The search did not find any paper that cites both Lewis/accommodation and Longino/background assumptions in the same argument. The inquisitive injustice literature does not engage with Longino. The philosophy of science literature that engages with Longino does not use accommodation theory. This connection is the essay's original contribution.

**Confidence: Strong for Longino's own claims; Moderate for the Lewis-Longino bridging claim (it is solid philosophically but needs to be marked as original synthesis).

---

### 6. Teo (2008, 2010, 2011): Epistemological Violence

Teo's cluster of papers defines epistemological violence within psychology:

**Teo (2008)** "From Speculation to Epistemological Violence in Psychology" (Theory & Psychology 18: 47–67): EV is introduced as a term for "interpretations that construct the 'Other' as problematic or inferior, with implicit or explicit negative consequences for the 'Other,' even when empirical results allow for meaningful, equally compelling, alternative interpretations." Key mechanism: **underdetermination**. The same data can support multiple interpretations. When researchers consistently choose the interpretation that pathologizes or inferiorizes the Other, and present this as objective knowledge, they commit EV.

Teo's apparatus is hermeneutic (he draws on Gadamer, Heidegger, and the hermeneutic tradition) and critical-theoretical (he cites Frankfurt School and critical psychology). He does *not* cite philosophy of language in the analytic tradition. There is no mention of Lewis, Stalnaker, QUD, Frege, or speech act theory. His framework is phenomenological-hermeneutic, not formal-pragmatic.

**Teo (2010)** "What is Epistemological Violence in the Empirical Social Sciences?" (Social and Personality Psychology Compass): This paper clarifies that EV "refers to the interpretation of social-scientific data on the Other and is produced when empirical data are interpreted as showing the [Other as deficient]." The mechanism involves: (1) naive empiricist philosophy that fails to recognize the interpretive latitude in data; (2) underdetermination — data never fully determines interpretation; (3) researchers exercise this latitude in ways that harm. EV is located primarily in the *interpretation of results*, not in the framing of research questions.

**Teo (2011)** "Empirical Race Psychology and the Hermeneutics of Epistemological Violence" (Human Studies 34: 237–255): extends the account, focusing on race psychology's history. Here Teo discusses the "hermeneutic deficit" — psychology's failure to recognize the interpretive nature of its own practice. He connects this to Gadamer's hermeneutics.

**The gap between Teo and the accommodation chain**: Teo's mechanism operates at the *interpretation* stage (what do we make of this data?) rather than at the *question-framing* stage (what question do we ask?). He does not analyze how the initial formulation of a research question as "Why does group X underperform?" already presupposes deficit. The presuppositional framing of the question is prior to the interpretive speculation Teo analyzes.

This is a genuine gap in Teo's account: he identifies the harm (inferiorizing interpretation) and its occasion (underdetermination), but does not trace back to how the question itself, by being accommodated into the common ground of the discipline, makes certain interpretations the "natural" or "obvious" ones from the start. The accommodation chain provides exactly this prior mechanism.

**Compatibility**: Despite operating at different points, Teo's account and the accommodation chain are compatible and mutually reinforcing. Accommodation explains *why* certain background assumptions (that group differences reflect deficits) become part of the disciplinary common ground, making them invisible. Once invisible, they function as what Longino calls background assumptions — enabling evidential relationships. Then, when data is interpreted, the Teo mechanism kicks in: underdetermination means multiple interpretations are possible, but researchers "naturally" choose the deficit interpretation because it is already baked into the common ground they are working within.

**Confidence: Strong for Teo's own definitions; Strong for the gap identification; Moderate for the compatibility claim (it is a synthesis, not a direct connection Teo makes).

---

### 7. Building the Chain Explicitly

**The full chain**:

**Step 1 — Accommodation (Lewis 1979)**: When a why-question is posed — "Why does group X perform differently from group Y?" — it carries presuppositions: (a) that the difference exists and is stable, (b) that it requires causal explanation, (c) implicitly, that the difference reflects something about group X rather than about the measurement, the comparison group, or the social context. These presuppositions are not asserted; they are carried. When researchers take up this question as a research program, they accommodate its presuppositions into the conversational (or disciplinary) common ground. The accommodation is automatic in Lewis's sense: no one votes to accept these presuppositions; they spring into existence as the question is taken up.

**Step 2 — Common Ground Update (Stalnaker 1974, 2002)**: Once accommodated, the presuppositions become part of the common ground. In Stalnaker's terms, the context set is updated to exclude worlds in which the presuppositions fail. For a discipline, the "context set" is the space of possibilities the field takes seriously — its background ontology, so to speak. A research program that has accommodated "group X has a cognitive/biological deficit" as a presupposition now operates in a context where this is simply taken for granted, not tested.

**Step 3 — QUD Governance (Roberts 2012, Beaver et al. 2017)**: The why-question becomes the QUD governing the research program. Under QUD theory, all relevant contributions are interpreted as (partial) answers to this question. The presuppositions of the QUD — that there is a real difference to explain, that it is traceable to group X's properties — are not-at-issue. They cannot be "answered" because they are not themselves the question; they are the conditions under which the question is well-formed. A researcher who challenges these presuppositions is not contributing an answer — they are challenging whether the question should be asked at all, which is effectively changing the subject. Within the discourse framed by the QUD, the presuppositions are structurally off-topic.

**Step 4 — Background Assumptions (Longino 1990)**: The accommodated presuppositions function as Longino's background assumptions: they determine what counts as evidence. If group-X-deficit is a background assumption, then data showing group differences is automatically read as evidence for the deficit hypothesis. Data showing environmental or structural factors would be evidence for alternative interpretations, but only if there were a background assumption connecting the data to those alternatives. The deficit assumption is already in the common ground; the structural assumption is not. This asymmetry — built into the disciplinary infrastructure — is what makes data systematically confirm the dominant interpretation.

**Step 5 — Epistemological Violence (Teo 2008, 2010)**: Researchers now interpret data under underdetermination, choosing among equally available interpretations. But the interpretive landscape is not level. The accommodated presuppositions have pre-loaded the common ground with the deficit framing. The "natural" interpretation is the one consistent with what has already been accommodated. Teo is right that underdetermination creates the opening for EV — but the accommodation chain explains *why* the harmful interpretation is consistently chosen: it is not wilful malice (usually) but the operation of pre-loaded common ground. Researchers are not freely choosing among interpretations; they are working within a presuppositional framework that has shaped what interpretations even appear available.

**Where the chain is strongest**:
- Steps 1–3 are tight: Lewis → Stalnaker → QUD is a well-established chain within philosophy of language. The mechanics are precise and the literature is rich.
- Step 3–4 (QUD → Longino) is philosophically strong but is the essay's synthesis; no one has explicitly connected these frameworks.
- Step 4–5 (Longino → Teo) is compatible but operates at different levels; Teo does not draw on philosophy of science in the Longinoan tradition.

**Where the chain is weak**:

**Weak link 1 — Scaling from conversation to institution**: Lewis's accommodation theory is a theory of conversational dynamics, not disciplinary dynamics. The claim that a research question functions like a QUD for an entire field, and that presuppositions are accommodated at the disciplinary level, requires an extension of the theory beyond its original scope. The Stalnaker 2002 paper notes the difficulty here (common ground becomes attenuated in large anonymous audiences). This needs to be addressed explicitly — the essay should acknowledge this and offer reasons why the extension is nonetheless plausible (iterative conference discourse, textbook transmission, grant-writing practices as repeated speech acts).

**Weak link 2 — Teo's hermeneutic framework vs. formal pragmatics**: Teo works in a phenomenological-hermeneutic tradition that is not obviously compatible with the formal pragmatics framework (Lewis/Stalnaker/Roberts). He does not cite this literature and would likely not accept his account as a downstream consequence of accommodation. The connection is synthetic: it requires showing that the two frameworks are describing the same phenomenon at different levels of abstraction. This is defensible but requires argument.

**Weak link 3 — Why-questions specifically**: The formal claim that why-questions presuppose their embedded proposition (that P happened) is well-established (confirmed by Bromberger 2004 and the Cambridge "Presupposition, Attention, and Why-Questions" chapter by Adler). But the additional claim that why-questions presuppose a *particular causal structure* (that the cause lies with the group rather than with the environment or measurement) is a substantive philosophical claim that requires more support. The presupposition of "Why does X underperform?" is formally just "X underperforms," not "X underperforms due to something about X." The deficit-location component of the presupposition is less formal and more pragmatic.

---

## Key Findings

1. **Lewis (1979) provides the mechanism**: presuppositions spring into existence automatically when utterances require them; the conversational score is updated without explicit negotiation. (Strong evidence — primary text confirmed)

2. **Stalnaker (2002) formalizes common ground**: it is a social/public attitude, represented as a context set, updated by assertions. Stalnaker himself notes scaling difficulties with large/anonymous audiences. (Strong evidence)

3. **QUD framework (Roberts 2012, Beaver et al. 2017) provides the insulation mechanism**: presuppositions of the governing QUD are not-at-issue; they cannot be challenged within the discourse framed by the QUD without changing the question entirely. This is the strongest link in the chain for explaining why presuppositions become invisible once a research program is constituted. (Strong evidence — the formal claim is well-supported; the application to research programs requires analogical extension)

4. **Inquisitive injustice (Keiser 2021; Mallory 2025/2026)**: an existing philosophical literature directly connects QUD theory to epistemic injustice and social harm. This partially builds the Lewis→Stalnaker→QUD→harm chain, but does not engage with Longino or Teo. (Strong evidence — confirmed papers in Synthese and Philosophical Studies)

5. **Longino (1990) provides the epistemology-of-science counterpart**: background assumptions determine what counts as evidence; they are invisible from within normal science; they are the means by which values are incorporated into inquiry. Structural parallel to accommodation but no explicit connection in Longino. (Strong evidence for Longino's claims; Moderate for the Lewis-Longino bridge)

6. **Teo (2008, 2010)**: EV is located in interpretive choices under underdetermination; draws on hermeneutic tradition, not formal pragmatics; does not analyze research question framing. Compatible with the accommodation chain but the chain provides a *prior* mechanism that Teo's account lacks. No philosophy of language citations in Teo. (Strong evidence for the gap; Moderate for compatibility)

7. **No one has built this full chain**: the accommodation literature (Lewis, Stalnaker, Roberts) does not engage with Longino or Teo; Teo does not engage with formal pragmatics; Longino does not use accommodation theory; Mallory/Keiser connect QUD to justice but not to research programs or EV. The full chain is the essay's original synthesis. (Strong evidence that it is original; Moderate confidence in the chain's soundness as philosophy)

---

## Assessment

The causal chain — Lewis accommodation → common ground update → QUD governance → background assumptions → epistemological violence — is philosophically defensible and will be compelling to an analytically-trained reader. It connects genuinely independent literatures that have not previously been linked. Its strongest segments are Steps 1–3 (the formal pragmatics chain is well-established) and the identification of Teo's gap (that his account lacks a mechanism for why the harmful interpretation is structurally pre-selected).

The chain's weak links are identifiable and honest:

(a) The scaling problem: accommodation theory is for conversations; the essay claims it applies to research programs. This is not a fatal weakness — disciplinary discourse is constituted by repeated speech acts (paper abstracts, grant proposals, textbook introductions) that accumulate into something like a disciplinary common ground. The "Hey, wait a minute" mechanism does operate in science (peer review), but it operates within a discourse already shaped by prior accommodation, not neutrally.

(b) The Teo incompatibility: Teo's framework is hermeneutic, not formal-pragmatic. The essay should not claim Teo *relies* on accommodation theory. The correct claim is: accommodation theory explains a *prior* moment in the production of EV that Teo's account leaves untheorized. This is a strengthening move, not a derivation.

(c) The additional deficit-location presupposition: The claim that "Why does X underperform?" presupposes not just the underperformance but that its cause lies with X is philosophically important but less formal than Lewis's framework can directly support. It is better supported pragmatically (via Gricean relevance: asking why X does something carries an implicature that the explanation will be about X) than semantically (as a pure presupposition).

The overall judgment: **the chain is strong enough to be philosophically credible**, provided the essay (1) explicitly marks the Lewis-Longino bridging move as synthetic, (2) addresses the scaling problem directly, (3) treats Teo's account as complementary rather than derivable. The inquisitive injustice literature (especially Mallory 2025/2026) shows that the philosophical community has independently arrived at related conclusions using the same tools — this corroborates that the approach is sound.

---

## Sources

- Lewis, D. (1979). Scorekeeping in a language game. *Journal of Philosophical Logic*, 8, 339–359. DOI:10.1007/BF00258436. [Full text: andrewmbailey.com/dkl/Scorekeeping_in_a_Language_Game.pdf]
- Stalnaker, R. (2002). Common ground. *Linguistics and Philosophy*, 25, 701–721. DOI:10.1023/A:1020867916902. [Text: semantics.uchicago.edu/kennedy/classes/f07/pragmatics/stalnaker02.pdf]
- Simons, M. (2003). Presupposition and accommodation: Understanding the Stalnakerian picture. *Philosophical Studies*, 112, 251–278. DOI:10.1023/A:1023004203043.
- Roberts, C. (2012). Information structure in discourse: Towards an integrated formal theory of pragmatics. *Semantics and Pragmatics*, 5 (1996/2012). [NASSLLI lectures: nasslli2012.com/files/courses/roberts-lecture-4.pdf]
- Roberts, C., Beaver, D., Simons, M., & Tonhauser, J. (2009). Presupposition, conventional implicature, and beyond. [semantics.uchicago.edu/kennedy/classes/f09/semprag1/robertsetal09.pdf]
- Beaver, D., Roberts, C., Simons, M., & Tonhauser, J. (2017). Questions under discussion: Where information structure meets projective content. *Annual Review of Linguistics*, 3, 265–284. DOI:10.1146/annurev-linguistics-011516-033952.
- Longino, H. (1990). *Science as Social Knowledge: Values and Objectivity in Scientific Inquiry*. Princeton University Press. DOI:10.2307/3341230.
- Teo, T. (2008). From speculation to epistemological violence in psychology: A critical-hermeneutic reconstruction. *Theory & Psychology*, 18(1), 47–67. DOI:10.1177/0959354307086922. [Open access: yorku.ca/tteo/Teo2008EpiVio.pdf]
- Teo, T. (2010). What is epistemological violence in the empirical social sciences? *Social and Personality Psychology Compass*, 4(5), 295–303. DOI:10.1111/j.1751-9004.2010.00265.x.
- Teo, T. (2011). Empirical race psychology and the hermeneutics of epistemological violence. *Human Studies*, 34, 237–255. DOI:10.1007/s10746-011-9179-8. [Open access: yorku.ca/tteo/Teo2011HumanStu.pdf]
- Keiser, J. (2021). The "All Lives Matter" response: QUD-shifting as epistemic injustice. *Synthese*. DOI:10.1007/s11229-021-03171-y.
- Mallory, F. (2025/2026). Inquisitive injustice. *Philosophical Studies*, 183, 143–163. DOI:10.1007/s11098-025-02428-3. [Open access: philarchive.org/archive/MALIIX]
- von Fintel, K. (2000). What is presupposition accommodation, again? *Philosophical Perspectives*, 22. [web.mit.edu/fintel/fintel-2000-accomm.pdf]
- Adler, J. (2008). Presupposition, attention, and why-questions. In *Reasoning*. Cambridge University Press. DOI:10.1017/CBO9780511814273.
