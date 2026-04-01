# Survey: Why Can't Evolution "Refactor" the Genome?

**Question:** What are the fundamental constraints that prevent evolution from cleaning up the genome the way a software team would refactor a codebase?

**Searches run:**
- Semantic Scholar: Lynch genome complexity drift population size; Muller's ratchet asexual accumulation; constructive neutral evolution Stoltzfus Gray; Lynch Origins Genome Architecture nonadaptive; genome streamlining Utricularia; genetic load cost selection limits; nearly neutral theory Ohta; Prochlorococcus SAR11 genome streamlining; Koonin Wolf constraints genome evolution; Palazzo Gregory junk DNA; GULO vitamin C pseudogene; human chromosome 2 fusion; pleiotropic genes vertebrate constraint; intron evolution Lynch population genetics
- Exa: why evolution cannot refactor genome; recurrent laryngeal nerve evolution; genome spaghetti code legacy code analogy; epistasis constraints fitness landscape; pleiotropy constraint genomic; evolution cannot take system offline; genomic streamlining bacteria

---

## Summary

The question "why can't evolution refactor the genome?" has a well-developed body of answers in population genetics and molecular evolution. The short answer: evolution faces at least five distinct categories of constraints, none of which software engineers deal with in the same combination. The strongest quantitative account — developed most forcefully by Michael Lynch over the past two decades — argues that the primary driver of genomic mess in eukaryotes is simply the weakness of natural selection in small-to-medium populations. When drift overwhelms selection, slightly deleterious mutations — junk insertions, redundant duplications, inefficient splice sites — accumulate not because they are useful but because selection is too weak to eliminate them. This is compounded by ratchet mechanisms, continuous-operation constraints, epistatic lock-in, and the absence of any mechanism analogous to planned downtime. There is a minority view that much apparent mess is actually functional (ENCODE; "irremediable complexity" as a specific adaptive outcome), but the weight of evidence and theoretical argument sits strongly with the nonadaptive explanation.

---

## Key Sources

### Lynch and Conery (2003), "The Origins of Genome Complexity"
- **Link**: DOI 10.1126/SCIENCE.1089370, Science 302:1401-1404 (1,611 citations)
- **Key content**: Landmark paper arguing that the genomic features distinguishing eukaryotes from prokaryotes — introns, mobile elements, reduced coding density, pseudogenes — are best explained by reduction in effective population size (Ne) and consequent weakening of purifying selection. Key mechanism: in small populations, mutations with selection coefficients less than 1/Ne behave as effectively neutral, allowing them to drift to fixation. The paper demonstrated an inverse relationship between proxies for Ne and genome complexity across the tree of life. Bacteria with huge populations (Ne ~ 10^8–10^9) have streamlined, gene-dense genomes; multicellular eukaryotes with small Ne have bloated, junky ones.
- **Assessment**: Highly credible — published in Science, 1,600+ citations, replicated broadly. The key insight is directional: genome complexity is not an achievement but a failure of selection. Limitation: critics (e.g., Vinogradov 2004) disputed some quantitative claims; more recent work (Marino et al. 2025) finds the Ne–genome size relationship is not universal across all animals.

### Lynch (2007), "The Frailty of Adaptive Hypotheses for the Origins of Organismal Complexity"
- **Link**: DOI 10.1073/pnas.0702207104, PNAS 104:8597-8604 (744 citations)
- **Key content**: The theoretical backbone. Lynch argues that "numerous aspects of genomic architecture, gene structure, and developmental pathways are difficult to explain without invoking the nonadaptive forces of genetic drift and mutation." Specifically: intron proliferation, mobile element expansion, pseudogene accumulation, and the spliceosomal machinery itself may all be drift-driven rather than selected-for. The paper introduces the critical threshold idea: selection can only "see" a mutation if its fitness effect exceeds ~1/(2Ne). Everything below that threshold is invisible to selection — it drifts at random. In humans, Ne ≈ 10^4–10^5, meaning mutations with fitness costs less than 10^-5 are effectively neutral. The vast majority of small insertions, duplications, and mobile element insertions fall in this range.
- **Assessment**: Open access (PMC1876435). Among the most important papers in 21st-century evolutionary biology. The "frailty" framework is well-supported theoretically; the empirical quantitative claims have been refined but not refuted. This paper's argument is why the "genome as spaghetti code" analogy holds: not because evolution is sloppy in some philosophical sense, but because selection is quantifiably too weak to sweep out low-cost genomic noise.

### Lynch (2007), "The Origins of Genome Architecture" (book)
- **Link**: Sinauer Associates (439 citations in Scholar records)
- **Key content**: Full monograph developing the population-genetic theory of genome architecture. Key synthesis: the evolution of eukaryotic genomic complexity (introns, UTRs, regulatory regions, mobile elements, pseudogenes) is primarily a byproduct of random genetic drift in populations of reduced effective size. Selection may then secondarily co-opt these features (e.g., using introns for alternative splicing), but the initial accumulation is nonadaptive.
- **Assessment**: High authority — this is the primary theoretical reference for the nonadaptive school. Not open access but widely cited. The book is comprehensive; limitations acknowledged include difficulty directly measuring Ne across deep evolutionary time.

### Gray, Lukes, Archibald, Keeling, Doolittle (2010), "Irremediable Complexity?"
- **Link**: DOI 10.1126/science.1198594, Science 330:920-921 (207 citations)
- **Key content**: Develops the concept of "constructive neutral evolution" (CNE) applied to cellular complexity. The key argument: once a gratuitous (initially neutral) component becomes entrenched in a molecular interaction — e.g., a redundant RNA editing step — compensatory changes accumulate that make the component indispensable even though it contributes nothing to fitness. The complexity then becomes "irremediable" — impossible to remove without catastrophic cost, even if it was never beneficial. The term "neutral ratchet" is central: complexity rachet-clicks upward even without selection. This is the "it has to keep running" constraint made molecular.
- **Assessment**: High credibility (Science, five major authors including Doolittle). A genuine theoretical advance over simple drift models — it explains why complexity is sticky, not just why it arises. The idea of "irremediability" is directly analogous to technical debt in software: the cost of refactoring exceeds the benefit at every individual step, even when the accumulated cost is enormous.

### Stoltzfus (1999), "On the Possibility of Constructive Neutral Evolution"
- **Link**: DOI 10.1007/PL00006540, Journal of Molecular Evolution 49:169-181 (489 citations)
- **Key content**: Original formulation of constructive neutral evolution. Stoltzfus proposes a specific mechanism: (1) a mutation arises that is initially neutral, creating a redundant component; (2) because it is neutral, it persists; (3) additional mutations arise that make the original component obligatory (e.g., through compensatory changes elsewhere); (4) the system is now more complex but no more fit. Illustrated with scrambled genes in ciliates, RNA editing, and spliceosomal splicing. The transition from self-splicing introns to spliceosome-dependent splicing is presented as a canonical example.
- **Assessment**: Foundational paper, 489 citations, peer-reviewed. The mechanism is concrete and testable. Key limitation: it is a possibility proof — demonstrating how CNE could occur, not that it is the dominant explanation for any specific case.

### Lukes, Archibald, Keeling, Doolittle, Gray (2011), "How a Neutral Evolutionary Ratchet Can Build Cellular Complexity"
- **Link**: IUBMB Life (187 citations)
- **Key content**: Empirically grounds CNE in the context of kinetoplastid RNA editing — a spectacularly baroque system of post-transcriptional modification found in trypanosomes, where mRNA sequences are extensively edited by guide RNAs before translation. This system apparently arose and became entrenched neutrally. It is now irreversible: the organism cannot simplify its genome because the editing machinery is required for basic gene expression.
- **Assessment**: Empirical demonstration of CNE in a real, extreme case. Credible, published in IUBMB Life. The kinetoplastid case is the strongest known example of "irremediable complexity" — a system so baroque it would be dismissed as engineering malpractice in any designed system.

### Marino et al. (2025), "Effective Population Size Does Not Explain Long-Term Variation in Genome Size and Transposable Element Content in Animals"
- **Link**: bioRxiv 2025 (21 citations, preprint)
- **Key content**: A recent challenge to the Lynch framework. Using 807 species across vertebrates, molluscs, and insects, the authors find no consistent relationship between proxies for Ne and TE content or genome size. Within individual clades, only weak and isolated associations emerge. Conclusion: TE dynamics are lineage-specific, and drift is not the dominant universal force driving long-term genome size evolution.
- **Assessment**: Preprint, not yet peer-reviewed final form, but 21 citations suggests it is being taken seriously. This is the most important recent challenge to the Lynch framework. Important caveat: it tests long-term patterns, and the population-genetics argument applies more cleanly to short-term fixation probabilities. The challenge does not invalidate the theoretical framework; it suggests the empirical landscape is messier than the clean theory predicts.

### Drouin, Godin, Page (2011), "The Genetics of Vitamin C Loss in Vertebrates"
- **Link**: Current Genomics (303 citations)
- **Key content**: Reviews the loss of GULO (L-gulonolactone oxidase), the terminal enzyme in vitamin C biosynthesis, across vertebrate lineages. Primates, guinea pigs, some bats, and teleost fish independently lost GULO through pseudogenization. The human GULO pseudogene retains ~28 exons but contains accumulated mutations preventing functional expression. The pattern — loss is irreversible, mutation accumulation continues in pseudogenes — is a textbook example of genomic legacy code: the "instructions" for an old capability persist as corrupted, nonfunctional text.
- **Assessment**: High-quality review, 303 citations. The GULO case is valuable because it is well-characterized and shows the one-way directionality of genomic decay: once selection for a gene relaxes, accumulation of disabling mutations is rapid and permanent in practice. There is no recovery pathway absent strong selection pressure.
- **Note**: A 2025 paper (Chen et al.) suggests GULO loss may not be entirely neutral — ascorbate deficiency appears to protect against schistosomiasis — a genuine complication for the simple "neutral loss" narrative. This is a useful reminder that what looks like dead legacy code may occasionally have unexpected interactions.

### Poszewiecka et al. (2022), "Revised Time Estimation of the Ancestral Human Chromosome 2 Fusion"
- **Link**: BMC Genomics (13 citations)
- **Key content**: Analyzes the fusion of two ancestral primate chromosomes that created human chromosome 2, placing the event at ~0.9 Mya (revised from earlier estimates of up to 4.5 Mya). The fusion site contains inverted telomeric repeats and a vestigial centromere — molecular fossils of the chromosome's ancestry. This is physical evidence of a large-scale genomic restructuring event that left visible scar tissue in the human genome.
- **Assessment**: Peer-reviewed, quantitative; the fusion itself is uncontested science (supported by multiple independent lines of evidence). The creationist challenge paper (Tomkins 2018) cited in search results does not meet scientific standards and is not credible.

### Jiang et al. (2024/2025), "Incomplete Lineage Sorting of Segmental Duplications Defines the Human Chromosome 2 Fusion Site"
- **Link**: bioRxiv/Cell Genomics (6 citations)
- **Key content**: High-resolution characterization of the chromosome 2 fusion site, showing that multiple segmental duplications arose before divergence of African great apes, with CRISPR experiments suggesting the fusion site has functional regulatory consequences. This complicates the "pure legacy" view slightly — the fusion, though originally a structural accident, may now have functional entanglement.
- **Assessment**: Recent, high quality. Illustrates the "irremediability" problem: old accidents become functionally integrated over time, making retrospective cleanup impossible even if it were theoretically desirable.

### Hu et al. (2017), "Constrained Vertebrate Evolution by Pleiotropic Genes"
- **Link**: Nature Ecology and Evolution (DOI 10.1038/s41559-017-0318-0)
- **Key content**: Demonstrates empirically that vertebrate mid-embryonic transcriptomes are conserved because the genes expressed at that stage are "pleiotropically" recruited to many other developmental contexts. High pleiotropy correlates directly with evolutionary conservation and developmental essentiality. The "developmental hourglass" — conservation at mid-embryogenesis despite divergence at early and late stages — is explained by pleiotropic constraint rather than special optimization.
- **Assessment**: Nature publication, rigorous comparative transcriptomics across 8 chordates. Highly relevant: this is the "can't refactor the central modules" constraint. Genes expressed during vertebrate organogenesis are wired into so many downstream pathways that any change ripples unpredictably through development. This is the biological analogue of deeply coupled legacy code where a "simple" refactoring breaks dozens of downstream dependencies.

### Koonin and Wolf (2010), "Constraints and Plasticity in Genome and Molecular-Phenome Evolution"
- **Link**: DOI 10.1038/nrg2810, Nature Reviews Genetics 11:487-498 (169 citations)
- **Key content**: Comprehensive review of the forces constraining vs. permitting evolution. Key points: (1) universal constraints exist (genetic code, core metabolic enzymes, spliceosome core) that are effectively frozen by function and epistasis; (2) much of the genome, however, shows high plasticity and evolves rapidly; (3) the relationship between constraint and function is non-trivial — some highly constrained elements have unknown function. The authors note that evolutionary constraints arise from both functional requirements and from epistatic entanglement (where changes require compensatory changes elsewhere).
- **Assessment**: High-quality review from major researchers (Koonin is one of the most cited evolutionary biologists). The framework of "constraints vs. plasticity" is useful: not all genomic "mess" is equally frozen. Some legacy code is immovable; some is neutral drift that could theoretically be purged.

### Grote et al. (2012), "Streamlining and Core Genome Conservation among Highly Divergent Members of the SAR11 Clade"
- **Link**: mBio (278 citations)
- **Key content**: SAR11 (Pelagibacterales) — the most abundant marine bacteria on Earth — have among the smallest free-living bacterial genomes (~1.3 Mb). These genomes are streamlined: high coding density, few regulatory elements, minimal noncoding DNA. The streamlining is ancestral, consistent across the entire clade, and attributed to strong selection for efficient replication in nutrient-limited open ocean environments. Large population sizes (Ne ~ 10^10) mean selection is highly effective at purging genomic waste.
- **Assessment**: Peer-reviewed, 278 citations. SAR11 is one of the strongest positive examples of "evolutionary refactoring done right" — it shows that genome cleanup IS possible when the conditions are right: huge populations, stable selection environment, and strong metabolic cost per base. The contrast with multicellular eukaryotes (Ne ~ 10^4–10^5, much lower cost per base) is the key variable.

### Carretero-Paulet et al. (2015), "High Gene Family Turnover Rates and Gene Space Adaptation in the Compact Genome of Utricularia gibba"
- **Link**: Molecular Biology and Evolution 32:1284 (50 citations)
- **Key content**: Utricularia gibba (bladderwort) has one of the smallest angiosperm genomes (~82 Mb), despite three rounds of whole-genome duplication, and contains essentially no junk DNA — intergenic regions are nearly absent. Yet it is phenotypically complex (carnivory, no roots, complex trapping mechanism). The genome is packed with functional genes, with loss of noncoding DNA achieved through high rates of small deletions. The mechanism appears to involve positive selection for genome compactness rather than just drift.
- **Assessment**: 50 citations, Mol Biol Evol — credible. U. gibba is the plant equivalent of the "counterexample" — an organism that genuinely refactored its genome. Key question: why did this succeed here? The U. reniformis comparison (a related terrestrial species with 304 Mb) shows that this is lineage-specific, probably driven by specific metabolic pressures (carnivory in nutrient-poor aquatic environments, selection against phosphorus-heavy DNA).

### Luiselli et al. (2024), "Genome Streamlining: Effect of Mutation Rate and Population Size on Genome Size Reduction"
- **Link**: bioRxiv 2024 (8 citations)
- **Key content**: Computational modeling showing that both increased Ne and increased mutation rate can produce genome streamlining, but with different resulting structures. Under high Ne, noncoding sequences are lost but coding size is maintained (like SAR11). Under high mutation rate, both coding and noncoding sequences are lost (like endosymbiotic bacteria). Key finding: genome size and coding density are determined by the interaction of Ne and mutation rate (N × μ).
- **Assessment**: Preprint but internally consistent. Adds nuance to the Lynch framework: it is not only Ne that matters but the interaction of multiple parameters. Streamlining requires either very large Ne or very high mutation rate — neither condition holds for large multicellular eukaryotes.

### Bastian, Enard, Lartillot (2025), "Empirical Validation of the Nearly Neutral Theory at Divergence and Population Genomic Scale Using 144 Placental Mammals Genomes"
- **Link**: bioRxiv 2025 (1 citation, preprint)
- **Key content**: Tests Ohta's nearly neutral theory in 144 placental mammal genomes simultaneously at micro- and macro-evolutionary scales. Finds consistent negative correlations between Ne (measured by heterozygosity) and the ratio of nonsynonymous to synonymous substitutions (πN/πS and dN/dS), confirming that smaller populations accumulate more slightly deleterious mutations. This is direct empirical validation, in mammals specifically, of the theoretical framework Lynch uses.
- **Assessment**: Preprint, recent (2025), but methodologically strong. This type of cross-scale test is exactly what the theory predicts. For the "genome refactoring" question, this confirms: human Ne is low enough that a substantial fraction of slightly deleterious insertions are invisible to selection and will accumulate indefinitely.

### Colnaghi, Lane, Pomiankowski (2020), "Genome Expansion in Early Eukaryotes Drove the Transition from Lateral Gene Transfer to Meiotic Sex"
- **Link**: bioRxiv 2020 (18 citations)
- **Key content**: Models why sex evolved, arguing that as eukaryotic genomes expanded (relative to prokaryotes), lateral gene transfer (LGT) became insufficient to counter Muller's ratchet, creating selective pressure for meiotic sex with full-genome recombination. Key finding: without sex, larger genomes accumulate deleterious mutations at rates sufficient to cause extinction (Muller's ratchet scales badly with genome size). Sex is, in part, a genome-maintenance strategy.
- **Assessment**: Interesting theoretical work with 18 citations. For the refactoring question: this shows that sexual reproduction evolved partly to manage genomic decay — it is evolution's partial solution to the ratchet problem. But it is a partial solution: sex can purge deleterious alleles but cannot reorganize genome architecture or remove embedded legacy elements.

---

## Landscape Assessment

### State of Knowledge

The question of why evolution can't refactor genomes is well-studied and has a dominant theoretical paradigm:

**Constraint 1: Drift beats selection for small-effect mutations.** This is Lynch's central argument. For large multicellular eukaryotes with Ne in the range of 10^4–10^5, any mutation with fitness effect |s| < 1/Ne ≈ 10^-5 is effectively neutral and drifts at random. Most insertions of mobile elements, most duplications, most slightly inefficient intron splice sites fall in this category. Selection cannot purge them — not because evolution is lazy but because the physics of finite populations prevents it.

**Constraint 2: The Muller's ratchet / neutral ratchet dynamic.** Asexual lineages ratchet-click toward genomic decay over time. Sexual reproduction partially counters this through recombination, but it cannot undo structural features like duplications, transposable element insertions, or pseudogene accumulation that have become embedded in chromosomal context. The "irremediable complexity" concept (Gray et al. 2010) formalizes this: once neutral complexity becomes entangled in functional interactions, removal requires many compensatory changes — the cost exceeds the benefit even when the overall "mess" is high.

**Constraint 3: It has to keep running.** Evolution cannot take the organism offline for maintenance. Every proposed "cleanup" mutation must maintain sufficient fitness at every intermediate step. This is the biological version of the impossibility of a "big rewrite" in software engineering. In a complex genome with pervasive epistasis (where genes interact non-additively), any simplifying mutation has unpredictable effects on other pathways. The pleiotropic constraint (Hu et al. 2017) shows this empirically: the most deeply entrenched genomic elements are those that have accumulated the most downstream dependencies. Refactoring them is not merely difficult — each step creates new dependencies.

**Constraint 4: Genetic load limits.** Selection can only act on a finite number of loci simultaneously. Haldane's dilemma (reformulated in modern terms): the cost of selection at any locus is paid in reduced reproductive success. A diploid population can sustain selection on perhaps a few hundred loci at most before the "genetic load" from selection deaths causes population collapse. A human genome has ~20,000 genes plus vast regulatory regions — selection cannot simultaneously optimize all of them. This means "genomic cleanup" at many loci is literally impossible to achieve by selection, even in principle, regardless of population size.

**Constraint 5: Loss of function is easy; gain of cleanup is hard.** Mutations that disable a gene are common; mutations that cleanly remove a gene and all its regulatory context are vanishingly rare. Mobile elements leave behind regulatory "scars" that interact with nearby genes. Pseudogenes may retain partial regulatory roles. Complete removal of genomic legacy requires not one mutation but a specific coordinated series of deletions — effectively requiring directed mutagenesis that evolution cannot perform.

### Agreements Between Sources

- Drift-based explanations for genomic complexity are now mainstream in population genetics (Lynch 2003, 2007; Koonin & Wolf 2010; Bastian et al. 2025).
- Sexual reproduction partially but incompletely addresses genomic decay (Colnaghi et al. 2020).
- Genome streamlining is observed in bacteria with large Ne and in specialized plant lineages (SAR11, Prochlorococcus, Utricularia), confirming the population-genetic predictions — cleanup IS possible under the right conditions.
- Pleiotropic entanglement is real and measurable (Hu et al. 2017), and explains why deeply embedded genomic features resist change.
- CNE and irremediable complexity (Gray et al. 2010; Stoltzfus 1999) explain why neutral complexity becomes permanent.

### Conflicts Between Sources

- The degree to which the Lynch framework (Ne × genomic complexity) is quantitatively accurate across all taxa is contested. Marino et al. (2025) find no universal relationship. The theory may be correct in direction but imprecise in magnitude.
- Whether GULO loss (and similar pseudogenization events) are truly neutral vs. adaptive is actively debated (Drouin et al. 2011 say mostly neutral; Chen et al. 2025 suggest parasite protection benefit). This matters for whether "legacy code" in the genome is truly neutral debris or has hidden functionality.
- The ENCODE controversy (Palazzo & Gregory 2014 argue 80% functional is inflated) is unresolved — how much of the "junk" is genuinely inert vs. co-opted regulatory material remains debated.

### Gaps and Under-Explored Areas

- **Quantitative theory of irremediability**: The CNE framework is conceptually strong but lacks a precise quantitative theory of when neutral complexity becomes locked in vs. when it can still be removed. A rigorous population-genetic model of the transition from "removable drift-noise" to "entrenched irremediable complexity" would be valuable.

- **The recurrent laryngeal nerve case**: Surprisingly sparse in peer-reviewed literature as a focused case study. Most discussions are in popular science books (Dawkins, Coyne) or lecture series. The Acta Palaeontologica Polonica paper ("A Monument of Inefficiency") exists but was inaccessible. This is a gap in the academic literature for such a well-known example.

- **Comparison of genomic "refactoring" success cases**: Utricularia gibba, SAR11, endosymbionts — these are listed but rarely compared systematically in a single study asking "what conditions permit cleanup?" The answer (large Ne, stable environment, high metabolic cost per base, perhaps specific deletion machinery) deserves more direct synthesis.

- **Fitness landscape topology and genomic cleanup**: The epistasis/fitness landscape literature (Kvitek & Sherlock 2011; recent theoretical work) is mostly about protein evolution, not genome architecture. The question of whether genome architecture sits in deep fitness valleys (preventing cleanup) or on neutral plateaus (drift-accessible cleanup) is not well-characterized empirically.

- **The "running system" constraint as a formal concept in biology**: Software engineers have formalized zero-downtime refactoring as a design problem. Evolutionary biologists have discussed it informally but there is no precise biological equivalent of "strangler fig" pattern constraints or "technical debt accumulation rates." This may be a novel framing worth developing.

### Surprises

1. **GULO loss may not be neutral**: The 2025 discovery that ascorbate deficiency protects against schistosomiasis (Chen et al.) means one of the textbook "broken gene" examples may have a fitness justification. This complicates the "dead code" analogy — some dead-looking code may be doing something unexpected elsewhere in the system.

2. **The Marino et al. (2025) challenge to Lynch**: A dataset of 807 animal species found no consistent Ne–genome size relationship. The Lynch framework is theoretically strong but may be empirically messier than the clean narrative suggests. This suggests the real world involves significant lineage-specific variation that simple drift models don't capture.

3. **Chromosome 2 fusion has functional consequences**: The 2025 CRISPR experiment (Jiang et al.) showed that deleting the human chromosome 2 fusion site alters gene expression in neural progenitor cells. A structural legacy of a chromosomal accident from ~0.9 Mya has been integrated into current regulatory function. This is perhaps the most vivid demonstration of "irremediability" — the accident is now load-bearing.

4. **SAR11 demonstrates total genome housekeeping is possible**: The world's most abundant bacterium achieved near-perfect genome streamlining (>96% coding) over evolutionary time. This proves evolution CAN clean a genome — under the right conditions. The fact that human cells cannot achieve this is purely a function of population size differences of several orders of magnitude, not of any fundamental impossibility.
