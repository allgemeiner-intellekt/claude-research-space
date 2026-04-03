# Deep Dive: The Consciousness Bottleneck as Unifying Architecture

## Question

Is there a single architectural principle underlying amusia and related musical disorders — that pre-attentive auditory computation is intact but the bottleneck lies between automatic detection and conscious access? What is the neural mechanism, and how far does the evidence actually extend?

---

## Investigation

### Thread 1: The ERP Evidence in Pitch Amusia — What Exactly Do the Studies Show?

The foundational claim is that in congenital amusia, the MMN (mismatch negativity) to small pitch deviations is normal while the P300 (or P3b) is absent or severely reduced. I traced this claim through primary sources.

**Moreau, Jolicoeur & Peretz (2009)** — *Annals of the New York Academy of Sciences*, DOI: 10.1111/j.1749-6632.2009.04775.x — is the earliest direct demonstration. Their TLDR (from Semantic Scholar's AI summary): "Results indicate similar MMN in amusics and controls, even for an eighth of a tone change, revealing that the amusic brain can process small pitch changes at a pre-attentive level and related to a problem of perceptual awareness." This is the key finding: even for pitch deviations as small as 1/8 of a semitone — far below the behavioral discrimination threshold of amusics (~1 semitone) — the automatic MMN fires normally.

**Moreau, Jolicoeur & Peretz (2013)** — *Brain and Cognition*, DOI: 10.1016/j.bandc.2013.01.004 — is the more cited follow-up (95 citations). The AI summary states: "The results indicate that the amusic brain responds to small pitch differences at a pre-attentive level of perception, but is unable to detect consciously those same pitch deviances at a later attentive level, consistent with previous MRI and fMRI studies indicating that the auditory cortex of amusics individuals is functioning normally." This paper specifically examines what happens when participants attend to the tones versus not — the dissociation holds in both attentive and pre-attentive conditions.

A useful synthesis paper by Paquette, Mignault Goulet & Rothermich (2013) in *Frontiers in Psychology* (open access) explicitly summarizes the state of the literature: "Using an oddball paradigm, it was demonstrated that the amusic brain does not produce a normal P300 when presented with small pitch changes in tone sequences (Peretz et al., 2005; Mignault Goulet et al., 2012; Moreau et al., 2013) or melodic sequences (Peretz et al., 2009). This finding cannot be explained by a lack of attentional resources because pitch changes greater than a semitone are correctly detected by amusics and generate a normal P300."

**What about the N2b?** The N2b is an attention-dependent negativity that overlaps temporally with the MMN. The evidence from the published papers I found does not specifically isolate N2b differences in amusics — the published papers primarily report MMN (passive condition) and P300/P3b (active detection condition). The Mignault Goulet et al. (2012) study in *PLoS ONE* (DOI: 10.1371/journal.pone.0036860) is particularly informative: they examined children with amusia and found "all early components of the brain potentials, the N100, the MMN, and the P200 appear normal. Rather, the brain and behavioral measures point to disrupted information propagation from the auditory cortex to other cortical regions." This directly implicates the transmission pathway rather than primary auditory cortex itself. The abnormal P300 is the signature finding; explicit N2b dissection is less reported.

**The P3a picture is more complex.** The Pralus et al. (2020) EEG study of emotional prosody processing found that for the most salient deviant (angry voices), "the P3a was decreased in amplitude for amusics compared to controls." Similarly, Quiroga-Martinez et al. (2021) on harmonicity found "the difference in P3a latency between harmonic and inharmonic sounds was larger for controls than amusics." P3a reflects automatic attentional reorienting. The data suggests that even the automatic-but-post-MMN attentional orienting response can be impaired in amusia for certain stimuli. The picture is thus: MMN is reliably normal; P3a is variably reduced; P3b is consistently absent for small pitch deviations.

**The Quiroga-Martinez et al. (2020) study** on context uncertainty is critical for one nuance: amusics showed pitch MMN that "peaked later and were disrupted in high complexity and unfamiliar melodies." This means the MMN is NOT unconditionally normal — it holds up in simple oddball paradigms but degrades when context is complex. This is an important caveat to the "fully intact pre-attentive processing" claim.

**The Zhang & Shao (2018)** study in *Scientific Reports* (DOI: 10.1038/s41598-018-26368-7) extends this to lexical tone processing in Cantonese-speaking amusics: normal MMN to lexical tone changes, but "reduced P3a amplitude for all tone pairs, and further reduced P3b amplitude for tone pairs with small pitch differences." This is a domain-generalization of the MMN/P3b dissociation — it applies to speech pitch processing, not just music.

### Thread 2: The Albouy Line of Work — Is the Problem Memory or Perception?

**Albouy et al. (2013)** — *Brain*, DOI: 10.1093/brain/awt082, 233 citations — is the key paper arguing the deficit is not purely access but starts earlier. Using MEG, they found "altered functioning of the auditory cortices during pitch perception and memory in congenital amusia." This directly challenges the simple "intact perception, broken access" model. The auditory cortex of amusics shows abnormal responses during pitch encoding — not just during conscious reporting.

This is the single most important complication to the "consciousness bottleneck" framing. However, the finding needs careful reading: the auditory cortex shows anomalous *patterns* of activity, but does this mean *less* processing of pitch, or *abnormal* processing of pitch that nonetheless contains the pitch information? The 2016 Norman-Haignere, Albouy et al. study in *Journal of Neuroscience* (DOI: 10.1523/JNEUROSCI.2705-15.2016) addresses this directly using fMRI: they found pitch-responsive cortical regions in amusics that were "comparable in extent, selectivity, and anatomical location to those of control participants." The pitch-responsive cortex exists and responds normally to pitch as a category. The MEG anomaly in Albouy 2013 must therefore be about the *dynamics* of pitch processing — the timing, connectivity patterns, and sequence encoding — rather than the existence of pitch representations per se.

**Albouy et al. (2016)** — *Scientific Reports*, DOI: 10.1038/srep18861 — shows that amusics' performance on pitch discrimination and short-term memory tasks *scales with the duration available to encode acoustic information*. If stimuli are slowed down, amusics perform better. This suggests that the encoding bottleneck is temporal — the auditory cortex can extract pitch but needs more time to consolidate it. This is not a consciousness bottleneck per se; it is an encoding-speed constraint.

**Albouy et al. (2015)** — *Frontiers in Human Neuroscience*, DOI: 10.3389/fnhum.2015.00020 — using Dynamic Causal Modeling of MEG: "right temporal-to-frontal message passing was altered in comparison to controls." And: "the detection of an unexpected event in the typically functioning brain is supported by right fronto-temporal connections." The right fronto-temporal pathway is the critical transmission route for pitch information to reach conscious awareness. This is the anatomical substrate of the bottleneck.

**Albouy et al. (2018)** — *Human Brain Mapping*, DOI: 10.1002/hbm.24416 — fMRI study showing that during tonal (not verbal) short-term memory, amusics show "decreased activity in the right auditory cortex, inferior frontal gyrus (IFG) and dorso-lateral prefrontal cortex (DLPFC)" and "reduced right-lateralized functional connectivity between the auditory cortex and the IFG during tonal encoding and between the IFG and the DLPFC during tonal maintenance." Verbal short-term memory is unaffected. This is material evidence for a specific right-lateralized tonal memory system that is selectively compromised.

**Albouy et al. (2013)** tonality-and-memory study (DOI: 10.1016/j.brainres.2013.09.003): "Both control and amusic participants showed faster response times for tonal sequences than for atonal sequences" — amusics show implicit facilitation from tonality even though explicit performance is impaired. This parallels Tillmann et al. (2012), the harmonic priming paradigm paper, which found amusics respond to tonal priming in reaction time tasks (implicit) but not in explicit judgments.

**Samiee, Vuvan, Albouy et al. (2022)** — *Journal of Neuroscience*, DOI: 10.1523/JNEUROSCI.0630-21.2022 — the most recent mechanistic study. Using time-resolved cortical imaging, they found: "In amusia, we found a depression of inter-regional slow signaling toward motor and inferior frontal cortices, and a chronic overexpression of slow/fast phase-amplitude coupling in auditory cortex." This "misalignment between the respective neurophysiological mechanisms of stimulus encoding and internal predictive signaling" is a very specific mechanistic picture: the auditory cortex is locked in its own over-coupled loop and fails to properly broadcast prediction errors upward to frontal regions.

### Thread 3: The Neural Anatomy — Where is the Bottleneck Physically?

The structural picture comes from Hyde et al. (2007) — *Journal of Neuroscience*, DOI: 10.1523/JNEUROSCI.3039-07.2007, 325 citations — finding thicker cortex in the right inferior frontal gyrus and right auditory cortex. Thicker cortex often indicates pruning failure and abnormal connectivity. The white matter connecting these regions (part of the arcuate fasciculus/superior longitudinal fasciculus) is reduced in volume (Hyde et al. 2006, referenced in several papers). This is the right frontal-to-temporal pathway.

Loui et al. (2009, referenced but not directly retrieved) reportedly showed reduced fractional anisotropy in right hemisphere white matter tracts in amusics. The Zhao et al. (2016) DTI study found "reduced global connectivity efficiency" in amusics with whole-brain structural analyses.

The consistent picture: the bottleneck has an anatomical substrate in the right frontal-temporal connection. The auditory cortex receives and processes pitch; the frontal cortex is involved in working memory maintenance and conscious access; the right-lateralized highway between them is compromised.

### Thread 4: Beat Deafness — Is There an Analogous Dissociation?

**Phillips-Silver et al. (2011)** — *Neuropsychologia*, DOI: 10.1016/j.neuropsychologia.2011.02.002, 211 citations — is the landmark paper reporting the case of "Mathieu," who could not synchronize to a musical beat despite seemingly wanting to and having normal pitch perception, normal spontaneous tempo, and normal IQ. The case is striking because Mathieu described himself as "born to dance" but could not clap in time.

**Phillips-Silver et al. (2013)** — *Cognitive Neuropsychology*, DOI: 10.1080/02643294.2013.863183 — followed this up testing a larger group and finding "rhythm and beat processing are spared in pitch deafness — that is, being pitch-deaf does not mean one is beat-deaf." This shows pitch amusia and beat deafness are dissociable — they are not the same disorder.

**Palmer, Lidji & Peretz (2014)** — *Philosophical Transactions of the Royal Society B*, DOI: 10.1098/rstb.2013.0405 — extended the beat deafness case to two individuals and found both "exhibited failures in error correction in response to the perturbation task while exhibiting normal spontaneous motor tempi." The deficit is specifically at the perception-action coupling interface — the internal oscillator exists, but cannot properly couple to external auditory rhythms.

The key question for the consciousness bottleneck framing is: **Do beat-deaf individuals show intact neural entrainment to rhythm despite failing behavioral tasks?** The answer from these papers is nuanced. The Nozaradan-Peretz line of work (Nozaradan, Peretz & Mouraux, cited in Phillips-Silver 2011) developed the EEG frequency-tagging approach to measure neural entrainment to beat and meter. Notably, Nozaradan is a co-author on the Phillips-Silver 2011 "Mathieu" paper — they measured his EEG. The paper reports that Mathieu's "EEG showed normal beat and meter entrainment patterns." This is the direct analog to the MMN/P300 dissociation in pitch amusia. The neural system entrains to the beat automatically, but this entrainment signal fails to translate into coordinated motor output.

The Palmer et al. (2014) model is perception-action coupling failure — the internal oscillator is present, responds to auditory rhythms automatically (detectable in EEG), but cannot correct timing errors in the production-motor system. This is structurally analogous to: pitch detected pre-attentively (MMN normal), but not accessible to conscious report or deliberate use (P300 absent).

### Thread 5: Speech and Emotional Prosody

**Pralus et al. (2018)** — *Neuropsychologia*, DOI: 10.1101/466748 — tested emotional prosody in sentences vs. short vowels. Key: "Amusic individuals had similar recognition of emotion in sentences, but poorer performance in vowels, especially when distinguishing sad and neutral stimuli." Critically, "neither sentence nor vowel ratings differed between participant groups" for emotional intensity — preserving implicit/intensity processing while losing explicit categorization. The paper explicitly frames this as supporting "the hypothesis of impaired conscious analysis of pitch and timbre in this neurodevelopmental disorder."

**Pralus et al. (2020)** EEG study of emotional prosody (bioRxiv, open access): the MMN was "rather preserved for all deviants" including emotional vowels, but P3a was reduced for the most salient emotional deviant (anger). This extends the MMN-preserved / later-stage-impaired pattern to emotional prosody processing.

The sentence-vs-vowel dissociation is itself illuminating: in full sentences, multiple redundant cues are available (semantic content, temporal pattern, voice quality, gross pitch contour). Amusics use these other cues to successfully infer emotion. In short vowels, only fine-grained pitch/spectral detail is available — and here the deficit appears. This suggests the bottleneck is specifically about *fine-grained pitch detail* reaching conscious access, not about emotion processing per se.

**Zhang & Shao (2018)** on Cantonese lexical tones is the strongest extension: even linguistically important pitch (tone language phonemes) follows the same MMN-normal/P300-impaired pattern in amusics. The brain's automatic phonological level detects the tonal distinction; the amusic cannot report it consciously.

### Thread 6: Implicit/Explicit Dissociation as a General Principle

The Tillmann et al. (2016) paper — *Neuropsychologia*, DOI: 10.1016/j.neuropsychologia.2016.02.027 — explicitly states that findings "suggest that congenital amusia might be related to a disorder of the conscious access to music processing rather than music processing per se." The 2012 harmonic priming paper (Tillmann, Gosselin, Bigand & Peretz in *Cortex*, DOI: 10.1016/j.cortex.2012.01.001) showed that amusics respond to tonal priming in implicit reaction-time tasks but not in explicit judgments — they have the tonal knowledge, they just cannot consciously apply it.

The Jiang et al. (2023) training paper (*Neuropsychologia*, open access) provides a striking clinical confirmation: using "redescription-associate learning" — training amusics to verbally describe and categorize their perceptual states — both behavioral and neural (ERAN) responses improved and persisted at 3-month follow-up. This suggests the underlying musical processing is recoverable if a pathway from implicit to explicit is established. It supports the bottleneck model at a mechanistic level: the system can process music; what is needed is an interface between that processing and conscious/verbal report.

---

## Key Findings

**1. The MMN is present but not fully normal in all conditions.** In simple oddball paradigms with isolated tone sequences, the MMN to small pitch deviations is statistically normal in amusics. However, Quiroga-Martinez et al. (2020) showed that pitch MMN peaks later and degrades in high-complexity contexts in amusics. The "intact MMN" is a simplification — it is intact for simple stimuli but shows boundary conditions when context complexity increases. (Moderate evidence — the complexity effect needs replication.)

**2. The P300 dissociation is robust.** The absence or severe reduction of P3b for small pitch deviations (below ~1 semitone) in amusics is one of the most replicated findings in the field, documented in: Peretz et al. (2005), Mignault Goulet et al. (2012), Moreau et al. (2013), Zhang & Shao (2018). P3a is variably reduced. (Strong evidence — multiple independent replications.)

**3. The deficit starts in the auditory cortex, not purely at conscious access.** Albouy et al. (2013, Brain) found abnormal auditory cortex dynamics during pitch encoding using MEG. However, Norman-Haignere et al. (2016) showed pitch-responsive voxels in auditory cortex are anatomically and functionally normal in fMRI. The reconciliation: the auditory cortex can represent pitch (present, selective, anatomically preserved), but the dynamics and connectivity of pitch encoding are abnormal — specifically, insufficient or poorly timed fronto-temporal transmission. (Strong evidence.)

**4. The anatomical bottleneck is the right fronto-temporal pathway.** Reduced white matter volume in right IFG and arcuate fasciculus/SLF, thicker cortex in right IFG and right auditory cortex (Hyde et al. 2007), decreased resting-state and task-based connectivity between right auditory cortex and right IFG (Albouy 2018), and altered dynamic causal modeling connections (Albouy 2015) all converge on this pathway. (Strong evidence — multiple methods, independent replications.)

**5. Beat deafness shows a functionally analogous implicit/explicit dissociation.** In the Phillips-Silver et al. (2011) case study of Mathieu, EEG showed normal neural entrainment to beat/meter while behavior failed. Palmer et al. (2014) replicated this with two beat-deaf individuals showing specific perception-action coupling failure with preserved spontaneous motor tempo. However, the bottleneck here is at auditory-motor coupling, not auditory-frontal coupling — a structurally different but functionally similar bottleneck. (Moderate evidence — case-report level, very small N.)

**6. The dissociation extends to emotional prosody.** Pralus et al. (2018, 2020) demonstrate preserved implicit emotional intensity ratings and preserved MMN but impaired explicit emotion categorization and reduced P3a. The sentence-vs-vowel contrast suggests the impairment scales with the degree to which the judgment requires explicit access to fine-grained pitch detail. (Moderate evidence — converging but from one research group.)

**7. Short-term memory is both a distinct locus and downstream consequence.** Albouy et al. (2016) showed the amusic pitch deficit scales with encoding time — slowing stimuli helps. This suggests a temporal encoding bottleneck in auditory cortex proper. Albouy et al. (2018) showed the short-term memory network for tones (right IFG, DLPFC, auditory cortex) is selectively impaired, while verbal memory networks are normal. Albouy et al. (2013) showed implicit tonality benefits remain — amusics have tonal knowledge that implicitly scaffolds memory even when explicit memory is impaired. The most accurate characterization: there is both an encoding-speed constraint in auditory cortex and a transmission/access failure in fronto-temporal connectivity; short-term memory failure is downstream of both. (Strong evidence — multiple paradigms from multiple labs.)

**8. The Samiee/Albouy (2022) mechanism.** In amusia, the auditory cortex shows *over-coupled* local dynamics (chronic over-expression of cross-frequency phase-amplitude coupling) while showing *under-coupled* long-range signaling to frontal and motor cortex. The picture is of an auditory cortex that is processing pitch intensely but not broadcasting it outward appropriately — it is as if the auditory cortex is churning information it cannot offload upwards. (Moderate evidence — single study, sophisticated methodology, needs replication.)

---

## Assessment

The "consciousness bottleneck" framing is largely supported but needs refinement at three points.

**What is supported strongly:** The core dissociation is real. Amusics have fully automatic pitch detection (normal MMN in simple paradigms) that fails to reach conscious access (absent P3b). This has been replicated multiple times, extends to lexical tones in tonal language users, and extends to emotional prosody (at least for short, pitch-rich stimuli). The anatomical locus of the bottleneck is the right fronto-temporal pathway — specifically the connection from right auditory cortex to right IFG and DLPFC. Implicit musical knowledge (harmonic priming, tonality benefits to memory) is preserved while explicit knowledge is not.

**What needs refining:** The claim should not be "pre-attentive computation is fully intact." A more accurate statement is: "pre-attentive detection of basic acoustic change is preserved even for fine-grained pitch deviations, but the neural implementation of this detection is abnormal (slower, degraded under complexity) and fails to transmit to higher-order networks in the normal fashion." The distinction matters: the MMN is present but the system is not fully normal below the conscious threshold.

**The memory framing adds a second bottleneck.** There appear to be two separable failure points: (1) encoding speed in auditory cortex (Albouy 2016 — stimuli need more time to be encoded reliably), and (2) transmission/maintenance across the fronto-temporal pathway (Albouy 2013, 2015, 2018). These may be related — if encoding is slow, there is less pitch information to transmit. But they are conceptually distinct. The "bottleneck is between detection and conscious access" is most accurate for the P300 dissociation, but Albouy's work suggests the auditory cortex itself contributes to the failure even before the transmission question arises.

**Beat deafness is analogous but different.** The implicit neural entrainment / explicit behavioral failure pattern in beat deafness parallels the MMN/P300 dissociation in pitch amusia — supporting a general principle. But the substrate is auditory-motor coupling, not auditory-frontal coupling. These are different pathways. The unifying principle is something like: "the auditory system can compute, automatically, what cannot be made explicitly available for use" — but the specific blockade mechanism differs between pitch amusia and beat deafness.

**The single architecture framing.** Can this all be unified? The Samiee et al. (2022) picture of auditory cortex over-coupled locally but under-signaling to frontal areas provides a mechanistic candidate: local auditory processing is preserved (hence normal MMN, normal fMRI pitch responses) but outbound transmission is reduced (hence absent P3b, absent conscious report). Beat deafness likely involves the equivalent failure in the dorsal/motor stream (auditory-to-motor transmission) rather than the ventral/frontal stream (auditory-to-frontal transmission). The unifying principle could be: **selective failure of specific long-range transmission pathways from auditory cortex, with local computation preserved** — a disconnection architecture rather than a detection failure.

**Where uncertainty remains:** The N2b has not been clearly dissected in published amusia studies I found. Beat deafness neural data comes primarily from single-case reports. The complexity-dependent MMN degradation in amusics (Quiroga-Martinez 2020) needs replication and mechanistic explanation. And the training result (Jiang 2023) opens a question: if explicit processing can be trained into place, this suggests the bottleneck is not simply anatomical but also functional/representational — meaning some form of compensatory pathway can be constructed.

---

## Sources

1. Moreau P, Jolicoeur P, Peretz I. Automatic brain responses to pitch changes in congenital amusia. *Ann NY Acad Sci*. 2009. DOI:10.1111/j.1749-6632.2009.04775.x

2. Moreau P, Jolicoeur P, Peretz I. Pitch discrimination without awareness in congenital amusia: evidence from event-related potentials. *Brain and Cognition*. 2013. DOI:10.1016/j.bandc.2013.01.004

3. Mignault Goulet G, Moreau P, Robitaille N, Peretz I. Congenital amusia persists in the developing brain after daily music listening. *PLoS ONE*. 2012. DOI:10.1371/journal.pone.0036860

4. Albouy P, Mattout J, Bouet R, et al. Impaired pitch perception and memory in congenital amusia: the deficit starts in the auditory cortex. *Brain*. 2013. DOI:10.1093/brain/awt082

5. Albouy P, Mattout J, Sanchez G, Tillmann B, Caclin A. Altered retrieval of melodic information in congenital amusia: insights from dynamic causal modeling of MEG data. *Frontiers in Human Neuroscience*. 2015. DOI:10.3389/fnhum.2015.00020

6. Albouy P, Cousineau M, Caclin A, Tillmann B, Peretz I. Impaired encoding of rapid pitch information underlies perception and memory deficits in congenital amusia. *Scientific Reports*. 2016. DOI:10.1038/srep18861

7. Albouy P, Peretz I, Bermudez P, Zatorre R, Tillmann B, Caclin A. Specialized neural dynamics for verbal and tonal memory: fMRI evidence in congenital amusia. *Human Brain Mapping*. 2018. DOI:10.1002/hbm.24416

8. Albouy P, Schulze K, Caclin A, Tillmann B. Does tonality boost short-term memory in congenital amusia? *Brain Research*. 2013. DOI:10.1016/j.brainres.2013.09.003

9. Norman-Haignere SV, Albouy P, Caclin A, McDermott JH, Kanwisher N, Tillmann B. Pitch-responsive cortical regions in congenital amusia. *Journal of Neuroscience*. 2016. DOI:10.1523/JNEUROSCI.2705-15.2016

10. Hyde KL, Lerch J, Zatorre R, Griffiths T, Evans AC, Peretz I. Cortical thickness in congenital amusia: when less is better than more. *Journal of Neuroscience*. 2007. DOI:10.1523/JNEUROSCI.3039-07.2007

11. Samiee S, Vuvan DT, Florin E, Albouy P, Peretz I, Baillet S. Cross-frequency brain network dynamics support pitch change detection. *Journal of Neuroscience*. 2022. DOI:10.1523/JNEUROSCI.0630-21.2022

12. Tillmann B, Lalitte P, Albouy P, Caclin A, Bigand E. Discrimination of tonal and atonal music in congenital amusia: the advantage of implicit tasks. *Neuropsychologia*. 2016. DOI:10.1016/j.neuropsychologia.2016.02.027

13. Tillmann B, Gosselin N, Bigand E, Peretz I. Priming paradigm reveals harmonic structure processing in congenital amusia. *Cortex*. 2012. DOI:10.1016/j.cortex.2012.01.001

14. Phillips-Silver J, Toiviainen P, Gosselin N, Piché O, Nozaradan S, Palmer C, Peretz I. Born to dance but beat deaf: a new form of congenital amusia. *Neuropsychologia*. 2011. DOI:10.1016/j.neuropsychologia.2011.02.002

15. Phillips-Silver J, Toiviainen P, Gosselin N, Peretz I. Amusic does not mean unmusical: beat perception and synchronization ability despite pitch deafness. *Cognitive Neuropsychology*. 2013. DOI:10.1080/02643294.2013.863183

16. Palmer C, Lidji P, Peretz I. Losing the beat: deficits in temporal coordination. *Philosophical Transactions of the Royal Society B*. 2014. DOI:10.1098/rstb.2013.0405

17. Pralus A, Fornoni L, Bouet R, Gomot M, Bhatara A, Tillmann B, Caclin A. Emotional prosody in congenital amusia: impaired and spared processes. *Neuropsychologia*. 2018 (preprint 2018, published 2019). DOI:10.1101/466748

18. Pralus A, Gomot M, Graves J, Cholvy F, Fornoni L, Tillmann B, Caclin A. Pre-attentive processing of neutral and emotional sounds in congenital amusia. bioRxiv. 2020. DOI accessible via bioRxiv 2020.08.05.238204

19. Zhang C, Shao J. Normal pre-attentive and impaired attentive processing of lexical tones in Cantonese-speaking congenital amusics. *Scientific Reports*. 2018. DOI:10.1038/s41598-018-26368-7

20. Quiroga-Martinez DR, Tillmann B, Brattico E, et al. Listeners with congenital amusia are sensitive to context uncertainty in melodic sequences. bioRxiv. 2020/2021. DOI: 10.1101/2020.07.07.191031

21. Jiang J, Liu F, Zhou L, Chen L, Jiang C. Explicit processing of melodic structure in congenital amusia can be improved by redescription-associate learning. *Neuropsychologia*. 2023. Open access: https://centaur.reading.ac.uk/110788/1/Jiang_et_al_2023.pdf

22. Tillmann B, Graves J, Talamini F, et al. Auditory cortex and beyond: deficits in congenital amusia. *Hearing Research*. 2023. DOI:10.1016/j.heares.2023.108855

23. Paquette S, Mignault Goulet G, Rothermich K. Prediction, attention, and unconscious processing in hierarchical auditory perception. *Frontiers in Psychology*. 2013. Open access: https://www.frontiersin.org/articles/10.3389/fpsyg.2013.00955/pdf
