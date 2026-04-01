# The Genome as Spaghetti Code

The human genome is, by any software engineer's standard, a catastrophe. Roughly 90% of its 3.2 billion base pairs serve no known function. Half the sequence consists of dead transposable elements — the molecular equivalent of old malware, quarantined but never deleted. The average gene is 95% intron: 27 kilobases of sequence that gets transcribed, spliced out, and thrown away for every 1.3 kilobases that actually encodes protein. Regulatory elements that control a gene's expression can sit a million base pairs away, buried inside the introns of an entirely unrelated gene, communicating with their target through a three-dimensional chromatin folding infrastructure that is invisible in the linear sequence. And the splicing machinery responsible for removing all those introns — a 300-protein, 5-RNA monster called the spliceosome — exists not because it's a good solution, but because a neutral evolutionary ratchet locked it in over a billion years ago, and now it cannot be removed without killing the organism. If a junior developer submitted this codebase for review, they would be fired.

But here is the surprise: the most interesting thing about the genome-as-spaghetti-code analogy is not where it holds. It's where it breaks. The genome is worse than spaghetti code in some respects — its complexity is literally irremediable, a word that no software system deserves — and alien to software in others. It rewrites itself at runtime. It inherits its execution state across generations. Its architecture facilitates future adaptation in ways no designed system achieves. The analogy illuminates real features of genomic organization, but its failure points reveal something deeper about the difference between systems that are designed and systems that evolve.

## How much is junk?

The empirical foundation for the spaghetti code analogy rests on a single question: how much of the genome is doing anything? The answer has been one of the most contentious debates in modern biology, and it hinges on what you mean by "doing anything."

In 2012, the ENCODE consortium announced that 80% of the human genome is "functional," based on evidence that most of it shows some form of biochemical activity — transcription, protein binding, chromatin modification — in at least one of 147 cell types tested [1]. The headline generated enormous media coverage and was widely interpreted as the death of "junk DNA." It was also, by the lead scientist's own admission on the day of publication, a PR decision. Ewan Birney wrote on his blog that using a "very strict, classical definition" of function — sequences with actual DNA-protein contacts plus exons — the figure was 9%. His personal comfort zone was 10–20%. "We use the bigger number," he wrote, "because it brings home the impact of this work to a much wider audience" [2].

The evolutionary biology community responded with controlled fury. Dan Graur's rebuttal, memorably titled "On the Immortality of Television Sets," argued that ENCODE had conflated biochemical activity with biological function — the difference between a television set that is turned on and one that is doing something useful [3]. The core evolutionary argument is quantitative and hard to dismiss: given the human mutation rate (~1.2 × 10⁻⁸ per base pair per generation) and realistic estimates of selection strength, natural selection cannot maintain more than about 10–15% of the genome in a functional state. If 80% were functional, the mutational load would crush human fertility [4]. Comparative genomics — aligning the human genome against other mammals to identify sequences preserved by purifying selection — converges on 8.2% as the fraction under detectable evolutionary constraint [5]. ENCODE's own 2020 update quietly catalogued 926,535 "candidate cis-regulatory elements" covering 7.9% of the genome, a dramatic retreat from the 80% headline [6].

The best current estimate is that roughly 8–15% of the human genome is functional in the evolutionary sense: about 1.5% protein-coding, with the rest comprising regulatory elements, structural sequences, and functional non-coding RNAs. The remaining 85–92% is a mixture of dead transposable elements (50–69% of the total genome by the most sensitive detection methods [7]), pseudogenes, and non-functional intronic and intergenic sequence. Some of this has been "exapted" — co-opted for new regulatory functions — but the exapted fraction appears to be a small minority of the total transposon-derived content.

In software terms: at least 85% of the codebase is dead code, commented-out functions, and remnants of old libraries that were imported, used briefly, and never cleaned up.

## The spliceosome: a case study in irremediable complexity

If you want to understand why the genome looks like spaghetti code, the spliceosome is the place to start. It is the single clearest example of how evolutionary processes produce complexity that is not just unnecessary but actively impossible to simplify — what the molecular evolutionists Ford Doolittle and Michael Gray have called "irremediable complexity" [8].

The story begins with group II introns, self-splicing RNA elements found in bacteria and in the mitochondria and chloroplasts of eukaryotes. A group II intron is a ribozyme — an RNA molecule that catalyzes its own removal from a precursor transcript. It folds into a six-domain structure, positions its flanking exons through Watson-Crick base pairing, and executes a precise two-step chemical reaction: the 2'-OH of a conserved adenosine attacks the 5' splice site, forming a lariat intermediate, and then the freed exon attacks the 3' splice site, joining the exons and releasing the lariat. No proteins are strictly required. The intron is a self-contained module: it takes input, processes it, and returns output with no external dependencies [9, 10].

The human spliceosome performs the identical chemistry — the same two-step transesterification, the same lariat intermediate, the same catalytic mechanism. But instead of doing it alone, it requires approximately 300 distinct proteins and 5 small nuclear RNAs (snRNAs), organized into five subcomplexes that assemble de novo on every intron, progress through at least seven conformational states, and are disassembled afterward [11, 12]. The five snRNAs are fragments of the ancestral group II intron: U6 snRNA is structurally equivalent to the catalytic Domain V, and U2 snRNA reconstitutes the Domain VI branch point. Philip Sharp called this "five easy pieces" — the ancestral intron, broken into five trans-acting RNA modules [13]. The largest and most conserved spliceosomal protein, Prp8, has a reverse-transcriptase-like domain that is structurally closer to the group II intron's own encoded maturase protein than to any other known enzyme, confirmed at 1.2-ångström crystal structure resolution [14]. The ancestry is not in doubt.

So how did a self-contained function become dependent on a 300-component framework? The mechanism is constructive neutral evolution (CNE), first formalized by Arlin Stoltzfus in 1999 [15] and applied to the spliceosome by Gray, Lukeš, Doolittle, and colleagues [8, 16, 17]. The logic is a ratchet:

1. Group II introns invaded the early eukaryotic genome, likely during the mitochondrial endosymbiosis. Trans-acting factors — proteins and RNA fragments that could help introns splice — arose and spread, initially as gratuitous helpers.
2. Once these helpers were present, mutations that degraded the intron's own self-splicing capability were no longer lethal. They were "presuppressed" — neutral because the external machinery compensated. Such mutations are far more common than mutations that improve self-splicing, so the introns gradually lost their independence.
3. Now the helpers are essential. Removing any one of them kills the organism, because the introns can no longer splice themselves. Additional proteins accreted into the complex for the same reason: each one presuppressed further degradation of the system's intrinsic capability, locking in another dependency.

The result is a machine that does exactly what a self-splicing intron does — removes an intron and joins exons — but requires 300 proteins to do it. "We are proposing that the complexity we observe is an evolutionary ratchet," Gray et al. write. "Once the complexity originates, it is irremediable, because eliminating any component would be lethal" [8].

The software analogy is precise. The intron was a pure function with no external dependencies. The maturase was a helper library. The snRNAs were modules that fragmented out of the original function. Once each component of the original function's self-sufficiency degraded — because the framework was there to compensate — the framework became mandatory. Now the framework cannot be removed. Nobody designed it. It accreted, one neutral dependency at a time, and each step made reversal slightly less likely. After a billion years of ratcheting, the spring is broken: spliceosomal introns have degenerated so far beyond the group II intron consensus that they cannot self-splice even in principle.

The scale of the resulting overhead is staggering. Introns constitute about 25% of the human genome — roughly 800 megabases, or four to five times the total sequence that actually encodes protein. The average human gene has eight introns totaling ~27 kilobases, compared to ~1.3 kilobases of coding sequence. Every nucleotide of every intron must be transcribed into RNA by RNA polymerase, at a cost of ~2 ATP per nucleotide, and then the resulting intronic RNA is discarded as a lariat. Lynch and Marinov estimate that a typical 5-kilobase intron complement raises the transcriptional ATP cost per gene by about 87% [18]. For the human average intron load, the cost premium is substantially higher. The cell is spending the majority of its transcriptional energy budget producing RNA that will be immediately thrown away — processed by a 300-protein machine that exists only because evolution could not take the system offline to refactor it.

## Action at a distance: configuration files buried in the wrong module

If the spliceosome is the genome's most baroque internal dependency, long-range enhancers are its most disorienting architectural feature. They are the genomic equivalent of a configuration file buried inside an unrelated module that controls the behavior of a function in a completely different part of the codebase — and if someone edits one character in that config file, it breaks a feature that seems totally unconnected.

The canonical example is the ZRS (Zone of Polarizing Activity Regulatory Sequence) and its target gene, Sonic Hedgehog (SHH). SHH is a signaling molecule that patterns limb development: it is expressed in a small cluster of cells called the zone of polarizing activity in the posterior limb bud, where it diffuses as a morphogen gradient that tells developing digits what position they're in. The regulatory element that activates SHH in the limb — the ZRS — sits approximately one million base pairs upstream of SHH on the linear chromosome. It is located inside intron 5 of LMBR1, a gene encoding a membrane protein with no known relationship to limb development [19].

The ZRS is not near SHH. It is not in a gene desert. It is inside another gene entirely, and it controls SHH's expression from a distance of one megabase. The evidence is direct: in transgenic mice, the ZRS sequence alone drives reporter gene expression specifically in the ZPA. Delete the ZRS, and SHH goes silent in the limb.

The clinical consequences are vivid. Single nucleotide substitutions in the ZRS — changes of one base pair in 3.2 billion — cause preaxial polydactyly: extra fingers on the thumb side of the hand [20, 21]. Multiple unrelated families across different populations carry different point mutations at different positions within the ZRS, all producing the same class of phenotype. One documented case shows a dosage effect: heterozygous carriers of a ZRS mutation get extra thumbs; the one homozygous individual reported developed Werner mesomelic syndrome, a severe multi-bone defect across the entire forearm and lower leg [22]. Even Hemingway's famous polydactylous cats carry ZRS point mutations [23]. One base pair, one million bases from the gene it controls, inside an unrelated gene — and it gives you extra fingers.

The mechanism that allows this is chromatin loop extrusion. The cohesin protein complex loads onto chromatin and translocates along the DNA, extruding loops, until it encounters CTCF boundary elements that define topologically associating domains (TADs). Within a TAD, distant sequences are brought into physical proximity by these loops. The ZRS and SHH sit within the same TAD; cohesin-mediated looping brings them together in three-dimensional nuclear space despite their one-megabase linear separation. Deplete cohesin in developing mouse limb buds, and the ZRS-SHH contact is lost, and SHH transcription collapses [24]. A 2025 paper identified specific sequence motifs in the ZRS — [C/T]AATTA homeodomain-binding sites — that are required for the enhancer to function at long range; mutate them, and the enhancer still works at short range but loses its ability to reach SHH across the megabase gap [25].

The ZRS/SHH system is toward the extreme but not an outlier. SOX9, a gene critical for craniofacial and skeletal development, is regulated by enhancer clusters more than 1.25 megabases away; disruptions cause Pierre Robin sequence, a birth defect involving jaw malformation, cleft palate, and airway obstruction [26]. Perhaps 10–20% of developmental regulator genes have key enhancers at distances exceeding 500 kilobases [27]. But the most instructive example for the spaghetti code analogy may be the FTO/IRX3 obesity case, which demonstrates not just action at a distance but active misdirection.

For years, genome-wide association studies identified variants in introns of the FTO gene as the strongest common genetic risk factor for obesity. Researchers spent years studying FTO function, generating hundreds of papers. In 2014, Smemo and colleagues demonstrated that this entire line of research was aimed at the wrong gene [28]. The obesity-associated variants in FTO introns are actually long-range regulatory elements that contact the promoter of IRX3, a homeobox gene located ~500 kilobases away. FTO is essentially serving as genomic parking space for regulatory sequences that belong, functionally, to IRX3's regulatory landscape. Mice lacking Irx3 are 25–30% lighter than wild-type controls. The gene in which the variants sit has nothing to do with their function — a fact that years of research failed to detect because the genomic architecture is, in software terms, undocumented spaghetti.

When TAD boundaries are disrupted — by chromosomal rearrangements, deletions, or mutations in CTCF binding sites — the consequences are a genomic version of namespace collapse. Enhancers that were scoped to one gene gain access to neighboring genes, a phenomenon called "enhancer adoption." Lupiañez and colleagues showed that rearrangements disrupting TAD boundaries near the EPHA4 locus cause a family of limb malformations by mis-wiring enhancers to wrong targets [29]. The regulatory logic of the genome depends on physical module boundaries maintained by protein infrastructure. The source code is meaningless without the runtime.

## Why evolution can't refactor

A software team facing a codebase this messy would refactor it. Evolution cannot. The reasons are quantitative, not philosophical, and they illuminate a fundamental difference between designed and evolved systems.

The dominant framework, developed by Michael Lynch over the past two decades, identifies effective population size (Ne) as the key variable [30, 31]. In a population of finite size, natural selection can only "see" a mutation if its fitness effect exceeds approximately 1/(2Ne). For humans, with an effective population size of roughly 10,000–100,000, this means mutations with fitness costs below about 10⁻⁵ are effectively invisible to selection. They drift at random — fixed or lost by chance, not by fitness. The vast majority of transposable element insertions, pseudogene accumulations, intron expansions, and low-impact regulatory noise fall below this threshold. Selection cannot purge them. Not because evolution is lazy, but because the physics of finite populations prevents it.

This is not a fringe view. A 2025 study validating the nearly neutral theory across 144 placental mammal genomes confirmed the prediction: species with smaller effective population sizes accumulate more slightly deleterious mutations [32]. The organisms that have successfully streamlined their genomes — SAR11 bacteria, the most abundant marine organism on Earth, with >96% coding density; the carnivorous plant *Utricularia gibba*, with an 82-megabase genome despite three rounds of whole-genome duplication — all have either very large effective population sizes or intense metabolic selection pressure for compactness [33, 34]. Cleanup works when the conditions permit. For large multicellular eukaryotes with small populations, the conditions do not permit.

But drift is only the first constraint. The second is what Stoltzfus and Gray call the neutral ratchet: once neutral complexity becomes entangled in functional interactions — once compensatory mutations have accumulated that depend on the "junk" being there — removing it is no longer neutral. It's lethal. The spliceosome is the canonical example, but the principle extends broadly. The kinetoplastid RNA editing system in trypanosomes is a 70-protein machine that laboriously edits thousands of mRNA sites by inserting and deleting uridines — a task that would be unnecessary if the genome simply encoded the correct sequences. But the editing machinery is now essential; the organism cannot simplify its genome because the editing system is the only thing keeping its genes functional [16]. This is irremediable complexity: the cost of the refactoring exceeds the cost of carrying the debt, at every individual step, even when the accumulated debt is enormous.

The third constraint is that evolution cannot take the system offline. Every intermediate step in any proposed "cleanup" must maintain a viable organism. Deeply pleiotropic genes — those wired into many downstream pathways — are measurably frozen by their entanglement. Hu and colleagues showed empirically that the most conserved vertebrate genes are precisely those with the highest pleiotropy: they interact with so many other genes that any change ripples unpredictably through development [35]. This is the biological equivalent of discovering that the function you want to refactor is called by thirty other modules, none of which have tests.

The fourth constraint is purely arithmetic: selection can only act on a finite number of loci simultaneously. Purging one slightly deleterious insertion requires that carriers without it outreproduce carriers with it. Doing this at thousands of loci simultaneously requires unrealistic fertility differentials — the population would collapse under the "cost of selection" long before the genome was cleaned up. And the fifth is an asymmetry between breaking and fixing: mutations that disable a gene are common; mutations that cleanly excise an entire transposon insertion, along with any regulatory scars it left, require a precise series of coordinated deletions that evolution has no mechanism to produce.

The result: a codebase that accumulates technical debt faster than it can pay it down, in a system that cannot be taken offline for maintenance, whose central modules are too deeply coupled to safely modify. In software, this is a failing project. In biology, this is every complex organism that has ever lived.

## Where the analogy breaks — and why it matters

Everything above makes the genome look like badly maintained software. But the analogy fails in ways that are more interesting than where it succeeds, and the failure points reveal something important about what life actually is.

**The genome doesn't specify the organism.** Software specifies its output: the same code, run in the same environment, produces the same result. The genome does not work this way. The same genotype produces radically different phenotypes in different environments, different cell types, and different developmental stages. A liver cell and a neuron have identical DNA; they are as different as two organisms. The genome provides molecular resources — proteins, RNAs, regulatory elements — that cells use in a context-dependent developmental process. It is more like a recipe than a blueprint, more like a vocabulary than a program [36, 37]. Lewontin made this point for decades: the genome is "a necessary but not sufficient cause" of the organism, like saying a spark plug is the program of a car engine [38].

**The context is inseparable from the code.** In software, you can describe a program independently of the hardware it runs on. In biology, you cannot. The chromatin state — which nucleosomes are tightly packed, which are open, which histones carry which chemical modifications, which regions of the chromosome are physically close in three-dimensional space — is not separate from the "code." It is constitutive of what the sequence does. The same enhancer, in two different chromatin contexts, activates different genes or no genes at all. The "runtime environment" is part of the program, and it varies by cell type, developmental stage, and environmental history. Recent work on transcription factor condensates — liquid-like droplets of proteins that form at active regulatory sites — suggests the regulatory logic is not even digital but analog: combinatorial, concentration-dependent, and stochastic [39].

**Epigenetic inheritance violates the deployment model.** Heritable changes in phenotype occur without any change to the DNA sequence. Methylation patterns, chromatin states, and non-coding RNAs can be transmitted from parent to offspring, altering gene expression across generations [40]. This is as if the runtime state of a program — not its source code — were inherited by all future deployments. There is no software equivalent.

**The genome rewrites itself.** Transposable elements are not just dead code; they are self-replicating elements that can — and do — move within the genome, insert into new locations, and create new regulatory patterns [41]. Under stress, transposon activity increases, effectively accelerating genomic self-modification in response to environmental challenge [42]. In software, code that rewrites its own source at runtime would be considered catastrophically dangerous. In biology, it is a major source of evolutionary innovation. About 8% of the human genome consists of endogenous retroviruses — the permanent integration of viral code into the host genome, some of which has been co-opted for essential functions including placental development [43].

**The genome is structured for evolvability.** Gerhart and Kirschner's theory of facilitated variation argues that the genome's architecture — conserved developmental toolkits, modular signaling pathways, degenerate (non-identical but overlapping) regulatory mechanisms — channels random mutations into phenotypically viable directions [44]. This is not intelligent design; it is the result of natural selection operating on the genome's own architecture over evolutionary time. Organisms whose genomes were structured to produce viable variation when mutated were more likely to adapt and survive. The genome is not "messy on purpose," but its apparent messiness — the redundancy, the modularity, the many overlapping pathways to the same functional outcome — may be what makes it evolvable. Software that achieved this would be remarkable; no designed system has ever evolved the capacity to evolve.

**The direction of causation is wrong.** Denis Noble has argued, with specific molecular evidence, that the cell controls DNA rather than the other way around [45]. The genome's own error rate in replication would produce hundreds of thousands of mistakes per cell division; it is the cell's repair machinery that achieves the actual fidelity. The cell decides which genes to express, when, and how — using the genome as a resource, not executing it as a program. This reversal of the usual metaphor — DNA as passive storage medium managed by the cell, rather than active program running the cell — is not a philosophical preference. It is an empirical claim about where causal control sits in the molecular hierarchy.

## The punchline

Is the human genome spaghetti code? Yes — emphatically, measurably, at multiple levels of organization. It has dead code (pseudogenes), copy-pasted malware (transposable elements), functions that depend on a 300-protein framework that nobody designed (the spliceosome), configuration files buried in unrelated modules (the ZRS inside LMBR1), and action-at-a-distance dependencies mediated by runtime infrastructure invisible in the source (chromatin looping). It accumulated this mess for the same reason software accumulates technical debt: because each individual mess was too small to be worth cleaning up, because the system could never be taken offline, and because the central modules were too deeply coupled to safely refactor.

But the genome is not *just* spaghetti code, and the ways it exceeds the analogy are where the deepest insight lies. Software spaghetti can always, in principle, be refactored. Genomic complexity is irremediable — locked in by evolutionary ratchets that have no reverse gear. Software has a fixed relationship between source and behavior; the genome's behavior depends on a three-dimensional, cell-type-specific, environmentally responsive execution context that is itself heritable. Software doesn't rewrite itself in response to stress; the genome does, and some of its most important innovations came from exactly this process. And no software system has ever evolved the capacity to evolve — to be structured such that random modifications are channeled into viable new functions.

The metaphor is useful, but its limits are the message. The genome is not a badly written program. It is what you get when a self-modifying, context-dependent, environmentally responsive information system runs for four billion years with no designer, no documentation, no test suite, and no downtime. The surprise is not that it's messy. The surprise is that it works at all — and that its mess is, in ways we are only beginning to understand, part of how it works.

---

## Sources

[1] ENCODE Project Consortium. "An Integrated Encyclopedia of DNA Elements in the Human Genome." *Nature* 489:57–74 (2012). https://doi.org/10.1038/nature11247

[2] Birney, E. "ENCODE: My Own Thoughts." Blog post, September 5, 2012. https://ewanbirney.com/2012/09/encode-my-own-thoughts.html

[3] Graur, D. et al. "On the Immortality of Television Sets: 'Function' in the Human Genome According to the Evolution-Free Gospel of ENCODE." *Genome Biology and Evolution* 5(3):578–590 (2013). https://doi.org/10.1093/gbe/evt028

[4] Graur, D. "An Upper Limit on the Functional Fraction of the Human Genome." *Genome Biology and Evolution* 9(7):1880–1885 (2017). https://doi.org/10.1093/gbe/evx121

[5] Rands, C.M. et al. "8.2% of the Human Genome Is Constrained." *PLoS Genetics* 10(7):e1004525 (2014). https://doi.org/10.1371/journal.pgen.1004525

[6] ENCODE Project Consortium. "Expanded Encyclopaedias of DNA Elements in the Human and Mouse Genomes." *Nature* 583:699–710 (2020). https://doi.org/10.1038/s41586-020-2493-4

[7] De Koning, A.P. et al. "Repetitive Elements May Comprise Over Two-Thirds of the Human Genome." *PLoS Genetics* 7(12):e1002384 (2011). https://doi.org/10.1371/journal.pgen.1002384

[8] Gray, M.W. et al. "Irremediable Complexity?" *Science* 330:920–921 (2010). https://doi.org/10.1126/science.1198594

[9] Costa, M. "Group II Introns: Flexibility and Repurposing." *Frontiers in Molecular Biosciences* 9:916157 (2022). https://doi.org/10.3389/fmolb.2022.916157

[10] Lambowitz, A.M. & Zimmerly, S. "Group II Introns: Mobile Ribozymes that Invade DNA." *Cold Spring Harbor Perspectives in Biology* 3:a003616 (2011). PMC3140690.

[11] Rappsilber, J. et al. "Large-Scale Proteomic Analysis of the Human Spliceosome." *Genome Research* 12:1231–1245 (2002). https://doi.org/10.1101/gr.473902

[12] Nilsen, T.W. "The Spliceosome: The Most Complex Macromolecular Machine in the Cell?" *BioEssays* 25:1147–1149 (2003). https://doi.org/10.1002/bies.10394

[13] Sharp, P.A. "Five Easy Pieces." *Science* 254:663 (1991). https://doi.org/10.1126/science.1948046

[14] Zhao, C. & Pyle, A.M. "Crystal Structures of a Group II Intron Maturase Reveal a Missing Link in Spliceosome Evolution." *Nature Structural & Molecular Biology* 23:558–565 (2016). https://doi.org/10.1038/nsmb.3224

[15] Stoltzfus, A. "On the Possibility of Constructive Neutral Evolution." *Journal of Molecular Evolution* 49:169–181 (1999). https://doi.org/10.1007/PL00006540

[16] Lukeš, J. et al. "How a Neutral Evolutionary Ratchet Can Build Cellular Complexity." *IUBMB Life* 63:528–537 (2011). https://doi.org/10.1002/iub.489

[17] Vosseberg, J. & Snel, B. "Domestication of Self-Splicing Introns during Eukaryogenesis." *Biology Direct* 12:30 (2017). https://doi.org/10.1186/s13062-017-0201-6

[18] Lynch, M. & Marinov, G.K. "The Bioenergetic Costs of a Gene." *PNAS* 112:15690–15695 (2015). https://doi.org/10.1073/pnas.1514974112

[19] Lettice, L.A. et al. "A Long-Range Shh Enhancer Regulates Expression in the Developing Limb and Fin and Is Associated with Preaxial Polydactyly." *Human Molecular Genetics* 12(14):1725–1735 (2003). https://doi.org/10.1093/hmg/ddg180

[20] Gurnett, C.A. et al. "Two Novel Point Mutations in the Long-Range SHH Enhancer in Three Families with Triphalangeal Thumb and Preaxial Polydactyly." *American Journal of Medical Genetics Part A* (2007). https://doi.org/10.1002/ajmg.a.31563

[21] Farooq, M. et al. "Preaxial Polydactyly/Triphalangeal Thumb Is Associated with Changed Transcription Factor-Binding Affinity in a Family with a Novel Point Mutation in the Long-Range Cis-Regulatory Element ZRS." *European Journal of Human Genetics* (2010). https://doi.org/10.1038/ejhg.2009.225

[22] Vandermeer, J. et al. "A Novel ZRS Mutation Leads to Preaxial Polydactyly Type 2 in a Heterozygous Form and Werner Mesomelic Syndrome in a Homozygous Form." *Human Mutation* 35(8) (2014). https://doi.org/10.1002/humu.22581

[23] Lettice, L.A. et al. "Point Mutations in a Distant Sonic Hedgehog Cis-Regulator Generate a Variable Regulatory Output Responsible for Preaxial Polydactyly." *Human Molecular Genetics* 17(7):978–985 (2008). https://doi.org/10.1093/hmg/ddm370

[24] Kane, L. et al. "Cohesin Is Required for Long-Range Enhancer Action at the Shh Locus." *Nature Structural & Molecular Biology* 29:891–897 (2022). https://doi.org/10.1038/s41594-022-00821-8

[25] Bower, G. et al. "Range Extender Mediates Long-Distance Enhancer Activity." *Nature* 643:830–838 (2025). https://doi.org/10.1038/s41586-025-09221-6

[26] Chen, L.-F. et al. "Structural Elements Promote Architectural Stripe Formation and Facilitate Ultra-Long-Range Gene Regulation at a Human Disease Locus." *Molecular Cell* (2023). https://doi.org/10.1016/j.molcel.2023.03.009

[27] Woolfe, A. et al. "Highly Conserved Non-Coding Sequences Are Associated with Vertebrate Development." *PLoS Biology* (2004). https://doi.org/10.1371/journal.pbio.0030007

[28] Smemo, S. et al. "Obesity-Associated Variants within FTO Form Long-Range Functional Connections with IRX3." *Nature* 507:371–375 (2014). https://doi.org/10.1038/nature13138

[29] Lupiañez, D.G. et al. "Disruptions of Topological Chromatin Domains Cause Pathogenic Rewiring of Gene-Enhancer Interactions." *Cell* 161(5):1012–1025 (2015). https://doi.org/10.1016/j.cell.2015.04.004

[30] Lynch, M. & Conery, J.S. "The Origins of Genome Complexity." *Science* 302:1401–1404 (2003). https://doi.org/10.1126/science.1089370

[31] Lynch, M. "The Frailty of Adaptive Hypotheses for the Origins of Organismal Complexity." *PNAS* 104:8597–8604 (2007). https://doi.org/10.1073/pnas.0702207104

[32] Bastian, F., Enard, D. & Lartillot, N. "Empirical Validation of the Nearly Neutral Theory at Divergence and Population Genomic Scale Using 144 Placental Mammals Genomes." *bioRxiv* (2025).

[33] Grote, J. et al. "Streamlining and Core Genome Conservation among Highly Divergent Members of the SAR11 Clade." *mBio* (2012). 278 citations.

[34] Carretero-Paulet, L. et al. "High Gene Family Turnover Rates and Gene Space Adaptation in the Compact Genome of *Utricularia gibba*." *Molecular Biology and Evolution* 32:1284 (2015).

[35] Hu, H. et al. "Constrained Vertebrate Evolution by Pleiotropic Genes." *Nature Ecology and Evolution* (2017). https://doi.org/10.1038/s41559-017-0318-0

[36] Ball, P. "We Need New Metaphors That Put Life at the Centre of Biology." *Aeon* (July 2024). https://aeon.co/essays/we-need-new-metaphors-that-put-life-at-the-centre-of-biology

[37] Prum, R.O. "The Genome Is the Starting Point for a Performance We Enact over a Lifetime." *Aeon* (January 2024). https://aeon.co/essays/why-its-time-to-replace-the-genetic-blueprint-idea

[38] Lewontin, R. "The Dream of the Human Genome." *New York Review of Books* (1992); "It's Even Less in Your Genes." *NYRB* (2011).

[39] Longo, G. & Tendero, P.-E. "The Differential Method and the Causal Incompleteness of Programming Theory in Molecular Biology." *Foundations of Science* (2007). https://doi.org/10.1007/s10699-007-9111-x

[40] Jablonka, E. & Lamb, M.J. *Evolution in Four Dimensions.* MIT Press (2005/2014). https://direct.mit.edu/books/book/2267/

[41] Feschotte, C. "Transposable Elements and the Evolution of Regulatory Networks." *Nature Reviews Genetics* (2008). 1,245 citations.

[42] Quadrana, L. & Henderson, I.R. "The Natural History of Transposons in Plant Pangenomes and Panepigenomes." *Current Opinion in Plant Biology* (2025).

[43] Chuong, E.B., Elde, N.C. & Feschotte, C. "Regulatory Activities of Transposable Elements: From Conflicts to Benefits." *Nature Reviews Genetics* (2016). 1,179 citations.

[44] Gerhart, J. & Kirschner, M. "The Theory of Facilitated Variation." *PNAS* 104 (2007). https://doi.org/10.1073/pnas.0701035104

[45] Noble, D. "The Cardiac Pacemakers: A Paradigm of Robustness in Evolutionary Biology." *Journal of Physiology* (2025).

---

## Open questions

- **How much regulatory function hides in the "junk"?** The 8–15% functional estimate from comparative genomics misses lineage-specific and rapidly evolving functional elements. ENCODE's 2020 catalog of 7.9% candidate cis-regulatory elements is a lower bound on regulatory content. The true functional fraction may be 15–25%, but distinguishing weak function from noise remains an unsolved empirical problem.

- **Is the genome structured for evolvability by selection, or is apparent evolvability a byproduct?** Gerhart and Kirschner argue for selection on genome architecture itself. But Lynch's framework suggests much apparent "modularity" may simply be the residue of neutral evolution. Distinguishing these explanations empirically is difficult and largely untested.

- **Can formal software complexity metrics be applied to genomic regulatory circuits?** No one has systematically computed cyclomatic complexity, coupling coefficients, or cohesion metrics on gene regulatory networks and compared them to software benchmarks. This would be a genuinely novel contribution bridging bioinformatics and software engineering.

- **What exactly is the information-theoretic status of DNA?** The genome is clearly an information-bearing system, but a comprehensive formal analysis of what aspects of information processing are genuinely analogous to computation — and which are not — does not exist. The literature is mostly critique; the positive theory is missing.

- **How did the FTO/IRX3 misattribution persist so long, and how many other GWAS signals are similarly misattributed?** If long-range regulatory architecture means that associated variants can sit inside the wrong gene, the entire edifice of gene-level GWAS interpretation is potentially compromised for developmental regulator loci. The systematic scale of this problem is unknown.
