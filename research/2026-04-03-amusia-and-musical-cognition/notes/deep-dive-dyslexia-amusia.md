# Deep Dive: The Dyslexia-Amusia Overlap — Shared Neurodevelopmental Substrate?

## Question

Is the comorbidity between congenital amusia and developmental dyslexia evidence of a shared neurodevelopmental substrate — the same disrupted mechanism expressing differently in two domains? And if so, what exactly is that substrate?

---

## Investigation

### The Comorbidity Evidence: Tracing the Primary Sources

The 25-30% figure cited in the survey (attributed to "Hoarau et al. 2024") traces back not to a single 2024 paper but to a series of studies by Manon Couvignou and colleagues. Hoarau 2024 appears to be a review that reported the figure from this prior work; the original data come from two primary studies.

**Study 1: Couvignou, Peretz & Ramus (2019), *Cognitive Neuropsychology***
This is the foundational adult study. Couvignou et al. recruited 20 adults diagnosed with dyslexia, 16 diagnosed with amusia, and matched controls. Using a battery of literacy, phonological, and musical tests:
- 6 of 20 dyslexic participants (30%) met criteria for amusia
- 4 of 16 amusic participants (25%) showed reading difficulties

The study also analyzed 18,000 participants in an online musical test database; self-reported dyslexic participants scored significantly lower on melodic skills than matched controls. The key diagnostic tool for amusia was the Montreal Battery of Evaluation of Musical Abilities (MBEA).

DOI: 10.1080/02643294.2019.1578205

**Study 2: Couvignou & Kolinsky (2021), *Neuropsychologia***
This replicated and extended the findings to children. 38 dyslexic children and 38 typically developing controls were assessed. Result: ~34% of dyslexic children were musically impaired — significantly elevated above both the population prevalence of amusia (1.5-4%) and the 5% rate in the control group. The impairment was predominantly pitch-based rather than rhythm-based, in both perception and production.

DOI: 10.1016/j.neuropsychologia.2021.107811

**Study 3: Couvignou, Tillmann, Caclin & Kolinsky (2023), *Child Neuropsychology***
This went deeper into mechanism. 15 dyslexic children with comorbid amusia (DYS+A) were compared with 15 dyslexic children without amusia (DYS-A) and typically developing controls. The central finding: **poor auditory serial-order memory** distinguished the DYS+A group. Item memory deficits and attentional deficits in the DYS+A group appeared to be secondary, likely consequences of reduced reading experience combined with weaker musical skills. Comparing the two dyslexic subgroups, the DYS-A children appear to have more effective compensatory strategies or a different developmental trajectory entirely.

DOI: 10.1080/09297049.2022.2162031

**Assessment of the comorbidity evidence:** The 25-34% figures are robust across two independent studies (one adult, one child) and one very large online dataset. All three studies come from the same research group (primarily Couvignou, collaborating with both Peretz and Kolinsky/Ramus), which is a limitation — independent replication in separate labs has not yet been done. The effect is strong enough (30x the population base rate in the overlap direction) that chance co-occurrence alone cannot explain it, but the causal mechanism remains contested within this group's own work.

---

### The Neural Substrate: Fronto-Temporal White Matter

**Amusia: right hemisphere anomalies**

Hyde et al. (2006), *Brain*, used voxel-based morphometry and found reduced white matter in the right inferior frontal gyrus (IFG) in amusics. In the same region, gray matter was paradoxically *increased*. This set up a puzzle that Hyde et al. (2007), *Journal of Neuroscience*, resolved with cortical thickness measures. Using surface-based morphometry in 21 amusics vs. 26 controls, they found:
- Thicker cortex in the right IFG (pars opercularis/triangularis region)
- Thicker cortex in the right auditory cortex (Heschl's gyrus/planum temporale region)

Hyde et al. (2007) explicitly interpret this as evidence of **cortical malformation — specifically, failed neuronal migration** during development. The logic: normally, cortical thickness decreases postnatally as pruning and myelination refine connectivity. Thicker cortex = less pruning = residual disorganized neurons that failed to complete normal lamination. The associated white matter reduction in the right IFG suggests that the frontotemporal pathway (auditory cortex → IFG) is structurally compromised, leaving the gray matter nodal regions abnormally thick but poorly connected.

DOI: 10.1523/JNEUROSCI.3039-07.2007

The arcuate fasciculus (AF) connection is crucial here. The Chen, Kumar, Williamson et al. study (51 citations, no year in database but cited widely as ~2015) found that detection of the AF in congenital amusia depends on the tractography algorithm used — with probabilistic methods finding an AF in most amusics, while deterministic methods sometimes fail to detect it. The TLDR finding is that amusics appear to have a structurally present but abnormal right AF. This complicates earlier reports claiming amusics simply "lack" the right AF.

**Dyslexia: left hemisphere anomalies**

The dyslexia literature presents a contrasting picture. The landmark postmortem work by Galaburda, Sherman, Rosen et al. (1985), *Annals of Neurology*, examined four consecutive dyslexic brains and found **cortical ectopias** — focal collections of neurons displaced into layer I of the cortex, and microgyria in the left hemisphere, predominantly in the perisylvian language regions (inferior frontal, superior temporal, inferior parietal). These are the most direct primary evidence for cortical malformation in dyslexia.

DOI: 10.1002/ANA.410180210

More recent neuroimaging converges. The Chinese dyslexia study by Su, Zhao, et al. (2018) found **reduced FA in the left AF-direct segment** correlating with phonological processing deficits, and reduced FA in the left ILF correlating with morphological processing. The key point: dyslexia primarily disrupts the *left* arcuate fasciculus and the left fronto-temporal pathway — the exact same type of tract but in the opposite hemisphere from amusia.

DCDC2 polymorphism work (Darki et al. 2014, *Journal of Neuroscience*) showed that a variant in the dyslexia candidate gene DCDC2 is associated with thicker cortex in the *left* angular and supramarginal gyri and lower left temporoparietal white matter volume. Notably, this is a thicker-cortex/lower-white-matter trade-off structurally analogous to what Hyde et al. found in the right hemisphere in amusia — just lateralized.

DOI: 10.1523/JNEUROSCI.1216-14.2014

---

### The Mirror-Image Question

Is this a mirror-image story (left disruption → reading, right disruption → music) or genuine overlap?

The evidence supports **both**, and that is the interesting part.

**Evidence for the mirror-image story:**
- Dyslexia: left fronto-temporal white matter reduction, left IFG anomalies, left temporal lobe ectopias
- Amusia: right fronto-temporal white matter reduction, right IFG thickness anomaly, right auditory cortex thickness anomaly
- The Albouy et al. (2018) fMRI study shows this cleanly: amusics show disrupted right fronto-temporal connectivity during tonal memory, while their left-hemisphere verbal memory network is intact. Controls show the reverse pattern (tonal > verbal for right fronto-temporal engagement)
- This suggests the underlying mechanism — failure of normal myelination/pruning of a fronto-temporal arc — affects the same class of tract but in hemisphere-specific ways depending on which developmental pathway was disrupted

**Evidence against a purely mirror-image story:**
- If it were a clean mirror, you would not expect comorbidity — disruption in one hemisphere would not imply disruption in the other. Yet 30% of dyslexics have amusia and 25% of amusics have reading problems
- The Couvignou 2023 finding that *auditory serial-order memory* specifically underlies the comorbid phenotype points to a domain-general auditory processing resource that is bilateral and not hemisphere-specific
- Fronto-temporal networks are not cleanly lateralized in early development; a common early disruption could affect both

**Reconciliation:** The most parsimonious interpretation is that these conditions share an early-developmental vulnerability to fronto-temporal pathway anomalies (reduced white matter, cortical thickness increases, ectopias), but that the phenotypic outcome (reading vs. music) is determined by *which hemisphere* is most affected. In some individuals both are affected — that is the comorbid group. The shared substrate is the biological mechanism (possibly neuronal migration, possibly pruning of fronto-temporal tracts), not a single anatomical locus.

---

### The Genetics Question

**Amusia genetics:** Peretz, Cummings & Dubé (2007), *American Journal of Human Genetics*, conducted the definitive family-aggregation study. First-degree relatives of amusics showed significantly elevated rates of the pitch deficit. The pitch disorder "has a hereditary component." The TLDR notes this confirms the hereditary nature of pitch-specific (not time-specific) impairment. Heritability estimates from twin studies place musicality broadly at ~50-80%, though amusia specifically has not been studied in large twin cohorts. Linkage work points to chromosome 4 loci for singing and music perception, and chromosome 8q for absolute pitch and music perception (Mandal & Karmakar 2021; Gingras et al. 2015 *Phil Trans B*).

**Dyslexia genetics:** The three best-characterized susceptibility genes — DYX1C1, DCDC2, KIAA0319 — all affect neuronal migration and ciliary function during cortical development. The mechanisms are now understood in considerable detail: DCDC2 and DYX1C1 interact physically; KIAA0319 and its homolog KIAA0319L affect auditory brainstem function when knocked out together (Guidi et al. 2017 showed auditory gap-in-noise detection deficits). These genes primarily affect left temporoparietal white matter development — the DCDC2 polymorphism study shows this precisely (left angular gyrus cortical thickness, left temporoparietal white matter volume).

**Is there genetic overlap between amusia and dyslexia?** This is the most important question and the most under-studied. The direct answer is: no study has tested whether dyslexia candidate genes (DYX1C1, DCDC2, KIAA0319) predict music perception, or whether amusia chromosome 4 loci predict reading. This is a genuine gap in the literature.

However, the circumstantial case for overlap is suggestive:
- DCDC2 affects cortical pruning/ciliary function in developing fronto-temporal regions bilaterally
- Ciliary function during cortical migration is a general developmental mechanism, not hemisphere-specific
- The Guidi et al. 2017 finding that KIAA0319L knockout specifically affects auditory processing (gap-in-noise detection) — not just phonological-linguistic processing — hints that these genes may affect a broader auditory cortical development pathway that serves both music and language
- Chromosome 4 loci for musicality overlap chromosomal regions that have been examined in several neurodevelopmental conditions, though no specific alleles shared with dyslexia loci have been identified

The AVPR1A gene (chromosome 12q), linked to music perception and memory in population studies, is worth noting — it is also involved in social cognition and has been studied in autism-spectrum conditions. But no dyslexia connection has been established.

---

### The "Failed Pruning" Hypothesis

Hyde et al. (2007) explicitly propose cortical malformation as the mechanism in amusia. Thicker cortex + reduced white matter = failed synaptic/axonal pruning during early postnatal development, leaving a cortex with too many disorganized neurons and too-sparse long-range connectivity.

The parallel in dyslexia is well-supported but takes a slightly different form. Galaburda's postmortem ectopias are developmental malformations — not pruning failures per se but failures of neurons to stop migrating (they overshoot into layer I). However, the outcome is similar: disorganized cortical columns, disrupted lamination, and associated reductions in white matter connecting that region to others. The DCDC2 ciliary function work (Bieder et al. 2023) shows these genes affect centrosomal/cytoskeletal function during migration, and their interaction with each other affects the timing and completion of cortical layer formation.

The two mechanisms (failed migration vs. failed pruning) may not be fully distinct — cortical malformations during migration alter the subsequent trajectory of synaptic pruning and myelination in the same region. A neuron that ends up in the wrong layer will both disorganize the local columnar structure and fail to form appropriate long-range connections that would normally be pruned and refined.

**Key asymmetry:** In dyslexia, the malformations are predominantly left hemisphere and have been localized to perisylvian language cortex. In amusia, the cortical thickness anomalies are right hemisphere. Both affect the IFG (left in dyslexia, right in amusia) — the IFG is a critical node in both the speech production network (left IFG/Broca's area) and the musical pitch memory network (right IFG). The parallel structural pathology in homologous regions of opposite hemispheres is among the most striking neuroanatomical correspondences in the literature.

---

### Amusia and Specific Language Impairment

The survey asked about amusia-SLI overlap. The picture here is more indirect. SLI shares with dyslexia a phonological processing deficit and elevated heritability but differs in having primary spoken language disruption. Marshall et al. (2009) explicitly studied the link between prosody and language skills in children with SLI and/or dyslexia, finding that prosodic processing weaknesses (pitch-based intonation perception) were shared across both conditions. Since amusia is a pitch-perception deficit, and prosody uses pitch, there is a pathway here. However, direct studies measuring amusia rates in SLI populations have not been conducted with the same rigor as the Couvignou dyslexia work. This remains a genuine gap.

---

## Key Findings

1. **The 25-30% comorbidity figures originate from Couvignou, Peretz & Ramus (2019) and Couvignou & Kolinsky (2021)**, not from a single 2024 meta-analysis. The 2024 Hoarau paper appears to be a review citing this work. The figures come from two independent samples (adults and children) from the same research group. Independent replication by other labs has not been published. **Confidence: strong for the basic comorbidity finding; moderate for the specific percentages given single-group origin.**

2. **The shared cognitive mechanism for comorbidity is auditory serial-order memory** (Couvignou et al. 2023). Dyslexic children with comorbid amusia specifically fail at maintaining the serial order of auditory sequences — a deficit that is not reducible to phonological awareness or pitch perception alone. This is a domain-general auditory working memory capacity with implications for both reading (phoneme sequencing) and music (melodic contour). **Confidence: moderate — one study, needs replication.**

3. **Hyde et al. (2007) found thicker right IFG and right auditory cortex in amusics**, interpreted as cortical malformation from failed neuronal migration. This is a primary source with 325 citations. The effect size is meaningful and has been replicated in the structural morphology literature. **Confidence: strong.**

4. **Galaburda et al. (1985) found left-hemisphere cortical ectopias in dyslexia** — focal migration anomalies in perisylvian cortex. This postmortem evidence is foundational (1306 citations) but limited to 4 cases. Neuroimaging evidence since then (white matter reductions in left AF, left temporoparietal region) converges on the same left-hemisphere fronto-temporal locus. **Confidence: strong for left-hemisphere involvement; moderate for the specific "ectopia" account given the postmortem sample size.**

5. **Both conditions affect the arcuate fasciculus** — left AF in dyslexia (reduced FA correlating with phonological deficits), right AF in amusia (structurally present but anomalous depending on tractography method). This is a true homology: the same class of tract, the same structural anomaly pattern, in mirror hemispheres. **Confidence: strong for dyslexia (multiple DTI studies); moderate for amusia (tractography method dependence is a real problem).**

6. **The "failed pruning" / cortical malformation mechanism is consistent across both conditions** but affects different hemispheres. In amusia: thicker cortex + reduced white matter in right IFG/auditory cortex. In dyslexia: thicker cortex (from DCDC2 variant) + reduced white matter in left angular/supramarginal gyrus. The DCDC2 ciliary/migration gene mechanism in dyslexia is well-characterized; the specific genes underlying cortical malformation in amusia are unknown. **Confidence: strong for the parallel structural pattern; speculative for shared genetic mechanism.**

7. **No direct genetic overlap between amusia candidate loci and dyslexia candidate genes has been established.** The amusia chromosome 4 loci and dyslexia genes DYX1C1, DCDC2, KIAA0319 have not been tested in cross-phenotype analyses. This is a gap, not a finding. **Confidence: strong that this gap exists; purely speculative otherwise.**

8. **The KIAA0319L knockout mouse shows auditory processing deficits (gap-in-noise detection)** independent of cortical migration, suggesting these dyslexia candidate genes affect auditory processing more broadly than just phonological reading circuits. This is potentially the most important underappreciated finding: dyslexia genes may affect music-relevant auditory cortical development too. **Confidence: moderate — animal model data only.**

---

## Assessment

The dyslexia-amusia comorbidity is real and the rate (25-34%) is far too high for coincidence. Three possible explanations exist, and the evidence now supports all three operating simultaneously:

**1. Mirror-image lateralization of the same developmental mechanism.** The strongest explanation: a developmental vulnerability in fronto-temporal white matter formation (reduced myelination, cortical malformation, failed pruning) affects both hemispheres in some individuals. When primarily left, you get dyslexia. When primarily right, amusia. When bilateral, comorbidity. The structural neuroimaging evidence makes this interpretation nearly compulsory — the same anatomical relationship (thick cortex + reduced white matter in IFG + AF anomaly) appears in opposite hemispheres in each condition.

**2. A shared domain-general auditory processing bottleneck.** Pitch and phoneme processing both depend on precise temporal coding in auditory cortex and working memory for auditory sequences. Couvignou et al. (2023) identified auditory serial-order memory as the specific shared impairment in comorbid children. This is not a lateralized explanation — it is a bilateral capacity that, when disrupted, degrades both music and language acquisition.

**3. Possible genetic pleiotropy.** The developmental genes for dyslexia (especially DCDC2 and KIAA0319L) have broader effects on auditory cortical development than the reading-focused literature acknowledges. The KIAA0319L auditory knockout finding is a genuine prompt to test whether these genes predict music perception independently of reading. This has not been done.

**The key limitation:** No study has yet examined neural or genetic overlap directly in the same participants. What we have is convergent evidence from separate literatures pointing toward the same mechanisms. The research needed — a study testing dyslexia candidate gene variants against music perception phenotypes, or a neuroimaging study directly comparing amusia and dyslexia structural anomalies within the same scan protocol — has not been published.

**On the domain-specificity question:** The comorbidity evidence is a significant challenge to strong modularity claims. If amusia were a pure deficit in a music-specific module with no connection to language-relevant systems, the 30% co-occurrence with dyslexia would be mysterious. The mirror-image hypothesis does not require abandoning modularity — the right and left fronto-temporal systems could both be domain-specialized but vulnerable to the same class of developmental disruption. But the serial-order memory finding points toward a shared pre-modular level of processing, which is harder to reconcile with strong modularity.

**The "failed pruning" framing is productive but incomplete.** What failed to prune in the right IFG in amusics, and why? The dyslexia field has partial answers for the left hemisphere (ciliary dysfunction, DCDC2/DYX1C1 migration anomalies). The amusia field has no equivalent genetic mechanism. Identifying whether the same or a parallel developmental pathway is disrupted in the right hemisphere in amusia is the central unanswered question.

---

## Sources

1. Couvignou, Peretz & Ramus (2019). Comorbidity and cognitive overlap between developmental dyslexia and congenital amusia. *Cognitive Neuropsychology*, 36, 1-17. DOI: 10.1080/02643294.2019.1578205

2. Couvignou & Kolinsky (2021). Comorbidity and cognitive overlap between developmental dyslexia and congenital amusia in children. *Neuropsychologia*, 107811. DOI: 10.1016/j.neuropsychologia.2021.107811

3. Couvignou, Tillmann, Caclin & Kolinsky (2023). Do developmental dyslexia and congenital amusia share underlying impairments? *Child Neuropsychology*, 29, 1294-1340. DOI: 10.1080/09297049.2022.2162031

4. Hyde et al. (2007). Cortical Thickness in Congenital Amusia: When Less Is Better Than More. *Journal of Neuroscience*, 27(47), 13028-13032. DOI: 10.1523/JNEUROSCI.3039-07.2007

5. Hyde et al. (2006). Morphometry of the amusic brain: a two-site study. *Brain*, 129(10), 2562-2570. DOI: 10.1093/brain/awl204

6. Galaburda, Sherman, Rosen, Aboitiz & Geschwind (1985). Developmental dyslexia: Four consecutive patients with cortical anomalies. *Annals of Neurology*, 18. DOI: 10.1002/ANA.410180210

7. Chen, Kumar, Williamson, Scholz, Griffiths & Stewart (n.d.). Detection of the Arcuate Fasciculus in Congenital Amusia Depends on the Tractography Algorithm. (51 citations; Semantic Scholar CorpusId: 1155687)

8. Albouy et al. (2018). Specialized neural dynamics for verbal and tonal memory: fMRI evidence in congenital amusia. *Human Brain Mapping*. DOI: 10.1002/hbm.24416

9. Su, Zhao et al. (2018). Alterations in white matter pathways underlying phonological and morphological processing in Chinese developmental dyslexia. *Developmental Cognitive Neuroscience*. DOI: 10.1016/j.dcn.2018.04.002

10. Darki, Peyrard-Janvid, Matsson, Kere & Klingberg (2014). DCDC2 Polymorphism Is Associated with Left Temporoparietal Gray and White Matter Structures during Development. *Journal of Neuroscience*, 34, 14455-14462. DOI: 10.1523/JNEUROSCI.1216-14.2014

11. Guidi et al. (2017). Knockout Mice for Dyslexia Susceptibility Gene Homologs KIAA0319 and KIAA0319L have Unaffected Neuronal Migration but Display Abnormal Auditory Processing. *Cerebral Cortex*, 27(12), 5831-. DOI: 10.1093/cercor/bhx269

12. Peretz, Cummings & Dubé (2007). The genetics of congenital amusia (tone deafness): a family-aggregation study. *American Journal of Human Genetics*, 81(3), 582-588. DOI: 10.1086/521337

13. Gingras, Honing, Peretz, Trainor & Fisher (2015). Defining the biological bases of individual differences in musicality. *Philosophical Transactions of the Royal Society B*, 370. DOI: 10.1098/rstb.2014.0092

14. Marshall & Harcourt-Brown, Ramus & van der Lely (2009). The link between prosody and language skills in children with specific language impairment (SLI) and/or dyslexia. *International Journal of Language and Communication Disorders*.
