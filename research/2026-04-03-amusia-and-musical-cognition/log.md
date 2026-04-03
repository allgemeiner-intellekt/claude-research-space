# Research Log — Amusia and the Architecture of Musical Cognition

## Scoping — 2026-04-03

**User seed:** "Is tone deafness / musical talent something you're born with?"

**Why the literal question is the wrong frame:** The nature-vs-nurture binary
assumes "musicality" is a single trait with a single answer. But the cognitive
science reveals it's many dissociable capacities — pitch discrimination, rhythm,
timbral memory, motor sequencing, emotional response to harmony — with different
heritability profiles and developmental trajectories. The interesting question
isn't "born with it?" but "what is the architecture of music cognition, and
where in that architecture do genes vs. experience act?"

Congenital amusia (~4% of population) is the sharpest empirical window into this.
True tone deafness isn't just "bad at music" — it's a specific neurocognitive
condition that dissociates from general intelligence, language, and even some
aspects of musical engagement. What it breaks (and what it leaves intact) maps
the architecture.

### Research questions

1. **Is congenital amusia a broken music module or a general auditory deficit?**
   Neuroimaging shows white matter tract anomalies and reduced connectivity
   between auditory cortex and frontal regions. Is this a music-specific system,
   or general auditory processing that music happens to use? The answer has
   implications for whether "music" is a natural kind in the brain at all.

2. **The tonal language paradox: why do Mandarin speakers almost never have amusia?**
   Cross-cultural epidemiology shows dramatically different amusia prevalence
   between tonal and non-tonal language populations. Tonal language speakers also
   show much higher rates of absolute pitch. This is arguably the strongest
   evidence that music and language share deep computational machinery — and that
   what we call "musical ability" is partly a side-effect of linguistic demands.

3. **What do twin studies actually show about the heritability of musical sub-abilities?**
   The "10,000 hours" deliberate practice narrative has been substantially
   undermined by twin studies (Mosing et al. 2014 and successors). But the
   picture is more interesting than "it's genetic" — different musical
   sub-abilities have different heritability estimates, and some show strong
   gene-environment interaction (absolute pitch requires both genetic
   predisposition AND early exposure during a critical period).

4. **Where is the line between perception and production in musical ability?**
   Many amusics can perceive musical violations implicitly (measured by EEG/MMN)
   even when they can't consciously detect them. Some people with poor singing
   have normal perception. The perception-production dissociation suggests the
   architecture has at least two independent bottlenecks — and "tone deaf" in
   everyday usage conflates them.

---

## Phase 2 — Survey outcomes (2026-04-03)

Four survey agents dispatched in parallel. Key findings by question:

### Q1: Amusia module vs general deficit
- Neither "broken module" nor "general deficit" fits cleanly. The deficit is
  **pitch-specific** (not music-specific), implemented via right fronto-temporal
  network anomaly.
- Hyde et al. (2007): amusics have paradoxically *thicker* cortex in right IFG —
  consistent with failed pruning/cortical malformation, not a missing module.
- Loui et al. (2009): reduced arcuate fasciculus, but Chen et al. showed this is
  tractography-algorithm-dependent — methodological controversy unresolved.
- Moreau et al. (2013): MMN is normal in amusics — brains detect pitch changes
  pre-attentively but can't access them consciously. Key puzzle.
- **Surprise**: 25–30% bidirectional comorbidity with dyslexia (Hoarau et al. 2024),
  suggesting shared white matter developmental anomalies.

### Q2: Tonal language paradox
- **The "paradox" largely dissolves**: Nan et al. (2010) found Mandarin speakers
  have essentially the same amusia prevalence (~3.4%) as Canadians (~3.2%).
- Absolute pitch IS much more common in tonal language speakers, but AP involves
  categorical labeling, while amusia is a fine-grained discrimination failure —
  different levels of processing.
- Liu et al. (2023, Current Biology, N≈500K): tonal language speakers better at
  melody but *worse* at beat processing — a resource reallocation trade-off no
  existing theory predicted.

### Q3: Heritability of musical sub-abilities
- Mosing et al. (2014, N=10,539 Swedish twins): within MZ discordant pairs, the
  twin who practiced more (up to 20,000+ hours more) showed NO better auditory
  discrimination. Practice–ability correlation is genetic pleiotropy, not causal.
- Heritability varies by sub-ability: melody 31–61%, rhythm 41–52%, pitch
  discrimination 12–30%.
- Mosing 2024: heritability of expertise *increases* with practice — opposite of
  what deliberate practice theory predicts.
- Hambrick & Tucker-Drob 2014: gene-environment interaction — genes enable rather
  than determine. Genetic effects strongest among those who practice.
- Practice explains ~21% of variance in music performance (Macnamara meta-analysis).

### Q4: Perception vs production dissociation
- Clean three-level dissociation established: (1) perceptual encoding,
  (2) auditory-motor translation ("inverse model"), (3) motor execution.
- Most lay "tone deafness" is level-2 failure — pitch heard correctly but
  sensorimotor mapping to vocal commands impoverished.
- ~17% of people are poor-pitch singers, but the great majority hear pitch
  normally (Pfordresher & Brown 2007, Wise & Sloboda 2008).
- **Gap**: production-only poor-pitch singers have never been neuroimaged
  systematically.

### Cross-cutting threads emerging
- The implicit/explicit dissociation (Q1) connects to the perception/production
  split (Q4) — both suggest conscious access is a separate bottleneck from
  computation.
- The tonal language melody/rhythm trade-off (Q2) connects to the sub-ability
  heritability differences (Q3) — musicality is genuinely multi-dimensional.
- The amusia-dyslexia comorbidity (Q1) and the fronto-temporal white matter
  story deserve deeper investigation.

Review agent dispatched to evaluate coverage and assign deep dives.

## Review round 1 verdict: CONTINUE

Three deep-dive assignments:
1. Consciousness bottleneck as unifying architecture
2. Amusia prevalence methodology across tonal/non-tonal populations
3. Dyslexia-amusia overlap and shared neurodevelopmental substrate

---

## Phase 4 — Deep dive outcomes (2026-04-03)

### Deep dive 1: Consciousness bottleneck
- The MMN dissociation is real but overstated — basic acoustic change detection is
  intact, but pre-attentive processing degrades under ecological complexity
  (Quiroga-Martinez 2020).
- P300 (especially P3b) absence is the most robust ERP marker.
- Albouy's MEG/fMRI work reveals two failure points: (1) encoding speed in
  auditory cortex, (2) fronto-temporal transmission. Short-term memory failure
  is downstream of both.
- Beat deafness shows analogous dissociation — normal neural entrainment but
  failed auditory-motor coupling (dorsal stream), vs amusia's ventral/frontal
  stream failure. **Unifying principle: selective long-range transmission failure
  from auditory cortex, not detection failure.**
- Implicit tonal knowledge (harmonic priming, tonality RT effects) remains intact
  in amusics — "consciousness bottleneck" more accurate than "memory bottleneck."

### Deep dive 2: Prevalence methodology
- **The "tonal language paradox" is methodologically unsound.** The most cited
  contrast (4% Western vs 3.4% Mandarin) uses different instruments (Distorted
  Tunes Test vs MBEA).
- Nan et al. (2010) using SAME instrument found 3.4% Mandarin vs 3.2% Canadian —
  essentially identical. No paradox when instrument is controlled.
- Peretz & Vuvan's 1.5% uses a stricter multi-gate criterion, not comparable
  to MBEA-based estimates.
- Liu et al. 2023 (N≈500K) measured mean performance, not prevalence.
- **No study has administered the same instrument with same fixed cutoffs to
  large matched tonal/non-tonal samples in a single design.** Key missing experiment.

### Deep dive 3: Dyslexia-amusia overlap
- The 25-30% comorbidity traces to Couvignou et al. (2019, 2021) — single
  research group, not yet independently replicated.
- **Mirror-image hemispheric story**: amusics have thicker right IFG + reduced
  right AF; dyslexics have thicker left angular/supramarginal + reduced left
  temporoparietal WM. Same structural logic, opposite hemispheres.
- Dyslexia candidate gene KIAA0319L knockout in mice produces auditory processing
  deficits — suggests dyslexia susceptibility genes may affect music-relevant
  auditory development more broadly than recognized.
- The failed pruning / cortical malformation hypothesis is well-characterized
  for dyslexia (DCDC2/DYX1C1/KIAA0319 — ciliary function, neuronal migration)
  but entirely uncharacterized for amusia. **Key missing piece: which gene/pathway
  disrupts right fronto-temporal development in amusics?**

Review round 2 dispatched.

## Review round 2 verdict: SATISFIED

Reviewer confirmed material is sufficient for report writing. Central thesis:
the consciousness bottleneck / disconnection architecture unifies all four
questions. Two tensions to manage in writing (Albouy auditory cortex complication,
small-N beat deafness evidence).

---

## Phase 5 — Report written (2026-04-03)

Report synthesizes across all four questions with the consciousness bottleneck
as central thesis. Key argument: amusia is not a broken module but a disconnected
one — the auditory cortex computes pitch normally at an automatic level, but the
right fronto-temporal pathway fails to transmit this information to conscious
access. Extended to show: most "tone deaf" people aren't (perception vs production
split), practice doesn't change the perceptual substrate (twin evidence), the
tonal language "paradox" dissolves methodologically, and amusia belongs to a family
of fronto-temporal disconnection syndromes alongside dyslexia.
