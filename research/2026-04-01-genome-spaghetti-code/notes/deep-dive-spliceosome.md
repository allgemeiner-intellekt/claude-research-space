# Deep Dive: The Spliceosome as Constructive Neutral Evolution's Centerpiece

## Question

How did the human spliceosome — a ~300-protein, 5-snRNA monster machine — evolve from self-splicing group II introns via Constructive Neutral Evolution (CNE)? Is this the best single example of spaghetti code in the genome, and what does it concretely tell us about the difference between evolved and designed systems?

---

## Investigation

### 1. The Ancestral State: Group II Introns as Self-Contained Units

Group II introns are remarkable: they are simultaneously ribozymes (self-catalytic RNA molecules), mobile genetic elements, and the evolutionary ancestors of the entire spliceosomal intron system. They are found in bacteria and in bacterial-derived organelles (mitochondria and chloroplasts) of fungi, algae, and plants. The most important point for the CNE argument is that they are *self-contained*: each intron carries within its own sequence everything needed to splice itself out of a precursor RNA.

**Structure.** The secondary structure of a group II intron is organized into six domains (DI through DVI), each a stem-loop structure. Domain I is the largest and provides the scaffold that positions the exons via Watson-Crick base-pairing between "Exon Binding Sites" (EBS) and "Intron Binding Sites" (IBS). Domain V is the catalytic heart — a short, 34-nucleotide helix that is absolutely essential for catalysis. Domain VI contains the critical branch-point adenosine. This six-domain architecture is entirely encoded within the intron sequence itself [Costa 2022, Lambowitz & Zimmerly 2011].

**Chemistry.** The splicing reaction is a two-step transesterification. First, the 2'-OH of a conserved adenosine in Domain VI attacks the 5' splice site, generating a lariat intermediate — a loop formed by a 2'-5' phosphodiester bond — and freeing the 5' exon's 3'-OH. Second, that 3'-OH attacks the 3' splice site, joining the exons and releasing the lariat. No external energy source is consumed for the chemical steps themselves; the transesterifications are isoenergetic. Two metal ions (Mg²⁺) coordinate the reaction at the active site [Smathers & Robart 2019].

**The encoded protein.** Many bacterial group II introns encode their own reverse transcriptase (RT), a multifunctional protein that acts as a "maturase" — it binds the intron RNA, stabilizes its active conformation, and helps it fold correctly for catalysis. This encoded protein is not strictly required for chemistry in isolated conditions (the RNA can self-splice *in vitro* at high Mg²⁺), but it dramatically increases the efficiency of splicing *in vivo* [Lambowitz & Zimmerly 2011]. This detail is critical: the dependence of the RNA on the protein is facultative in the ancestor, obligate in the descendant.

**Evidence for ancestry.** The connection between group II introns and spliceosomal introns rests on several independent lines of evidence [Vosseberg & Snel 2017, Galej et al. 2018, Smathers & Robart 2019]:

1. **Identical chemistry.** Both use the exact same two-step transesterification mechanism to form identical lariat intermediates with 2'-5' branch structures.
2. **Shared RNA architecture.** Domain V of group II introns is structurally and functionally equivalent to U6 snRNA in the spliceosome. The two structures are so similar that they have been called "the same RNA domain" [Galej et al. 2018].
3. **Prp8 as the key protein link.** Prp8 is the largest and most conserved protein in the spliceosome — it contacts the active site and is essential for both chemical steps. Its RT-like domain is structurally closer to the group II intron-encoded maturase proteins than to any other known reverse transcriptase. Crystal structures of bacterial group II intron maturases confirm this homology at 1.2-Å resolution [Zhao & Pyle 2016].
4. **snRNA origins.** The five spliceosomal snRNAs (U1, U2, U4, U5, U6) are thought to have evolved from fragments of a group II intron — a hypothesis Phillip Sharp called "five easy pieces" in a 1991 *Science* commentary. U6 snRNA and U2 snRNA together reconstitute the Domain V / Domain VI chemistry of a group II intron. Vosseberg & Snel (2017) trace this fragmentation in detail: the snRNAs emerged from intron domains that began acting as trans-acting elements before the intron lost self-splicing capability entirely.

The evolutionary consensus is unambiguous and strong. As Galej et al. (2018) put it in *Chemical Reviews*: these comparisons "support the long-held assertion that group II introns and the eukaryotic spliceosome have a common evolutionary origin."

---

### 2. The CNE Transition: From Self-Contained Ribozyme to 300-Protein Dependency

The key mechanism is Arlin Stoltzfus's 1999 framework of Constructive Neutral Evolution (CNE), elaborated and applied to the spliceosome specifically in:
- Stoltzfus (1999) *J. Mol. Evol.* 49:169–181 [primary source, 489 citations]
- Gray et al. (2010) *Science* 330:920–921 "Irremediable Complexity?" [207 citations]
- Lukeš et al. (2011) *IUBMB Life* 63:528–537 "How a neutral evolutionary ratchet can build cellular complexity" [187 citations]
- Vosseberg & Snel (2017) *Biology Direct* 12:30 "Domestication of self-splicing introns during eukaryogenesis" [34 citations]
- Muñoz-Gómez et al. (2021) *J. Mol. Evol.* 89:172–182 "Constructive Neutral Evolution 20 Years Later" [69 citations]

**The CNE mechanism in abstract.** CNE requires three ingredients:
1. **Excess capacity:** Component A performs a function without needing B. But a gratuitous A:B interaction arises neutrally and spreads by drift.
2. **Presuppression:** A mutation degrades A's independent function. Normally deleterious, but the existing A:B interaction rescues fitness — so the mutation is neutral. It spreads by drift.
3. **Ratchet:** A is now dependent on B. Losing B would be lethal. Purifying selection locks in the dependency. The system is now *more complex but not more functional* than the ancestral state.

Each individual step can be reversed, but the probability of the full reverse sequence is vanishingly small once multiple presuppression events have occurred. The system ratchets forward into obligate complexity.

**Applied to the spliceosome.** The narrative, reconstructed from Stoltzfus 1999 and Vosseberg & Snel 2017:

*Step 1 — The intron invasion.* Group II introns spread into the primitive eukaryotic lineage, most likely during the endosymbiotic event that produced mitochondria (which brought their group II intron load). A primitive spliceosome-like ability to splice these introns in *trans* was necessary for the host to survive. This initial requirement is the founding dependency.

*Step 2 — Fragmentation.* A group II intron fragmented, its domains separating into distinct RNA molecules (the proto-snRNAs). Each fragment could still interact with the intron substrate in *trans*, reconstituting splicing activity collectively. This is the "five easy pieces" scenario [Sharp 1991].

*Step 3 — Loss of self-splicing.* Once external factors (proto-snRNAs, the RT protein now working as a general maturase) began "helping" the introns splice, mutations that degraded the intron's own folding and catalytic capability were presuppressed — no longer deleterious because the external machinery compensated. Vosseberg & Snel (2017): "Mutations that reduce activity or affinity or stability are much more common than those with the opposite effect. The resulting directionality consists in... introns losing self-splicing ability, becoming dependent on available proteins as well as trans-acting intron fragments."

This is the key ratchet. The introns could now *afford* to degenerate, because the machinery was already there.

*Step 4 — Protein accretion.* The spliceosomal core recruited proteins from other RNA-processing pathways. Proteins that had "excess capacity" — that could incidentally bind the assembling snRNP complexes — got recruited neutrally. Once recruited, those proteins could presuppress mutations that degraded snRNA-intrinsic stability or folding. More proteins accreted. Vosseberg & Snel document that most of the protein complexity of the spliceosome was added in bursts before the LECA (Last Eukaryotic Common Ancestor), with further expansions in animals and plants — not a gradual accumulation.

*Step 5 — Irreversibility.* The spliceosome became "irremediable" — the title of Gray et al. 2010's *Science* paper. The introns cannot self-splice any more. The snRNAs cannot catalyze splicing without their full protein complement. The protein subunits cannot work without their partner snRNPs. The system has 300 interdependent components, each conditionally essential. You cannot simplify it. Gray et al. call this outcome "runaway bureaucracy."

Critically, Gray et al. (2010) explicitly frame this as a counterpoint to adaptationist explanations. The spliceosome's complexity provides no more function than a self-splicing intron. Nothing about 300 proteins is *better* at removing introns than one intron removing itself. The complexity is pure overhead, locked in by neutral drift and purifying selection against dismantling.

**The Speijer (2011) debate.** Dave Speijer published a *BioEssays* challenge asking whether CNE really explains cellular complexity. The response, co-authored by Doolittle, Lukeš, Archibald, Keeling, and Gray — basically every major figure in this literature — explicitly defends CNE as a sufficient explanation for the spliceosome and other cases [Doolittle et al. 2011, *BioEssays*]. They are not retreating; they're fortifying.

---

### 3. The Software Analogy — Made Precise

The spaghetti code analogy maps cleanly, but it's richer than a simple "legacy code" story.

**The ancestral state is a self-contained module.** A group II intron is like a pure function: it takes input (the flanking exons), executes a transformation (catalysis), and returns output (spliced exons), with no external dependencies. All state is internal. The function carries its own enzyme.

**The first step is a gratuitous dependency.** Imagine a team adds a logging framework to the codebase. The function still works, but now it logs. Nothing is broken. The logging framework accumulates in the shared runtime.

**The second step is the fatal mutation.** Someone refactors the function: in doing so, they inadvertently remove one of the internal elements that kept it self-catalytic. In production, this doesn't matter — the runtime framework compensates. The change passes code review because tests pass. The function now *needs* the framework.

**The ratchet turns.** Now you can't remove the framework without breaking the function. Worse: other functions get added, all relying on the framework. Each one further cements the dependency. Over time, nobody remembers which parts of the framework are truly needed — removing any piece might break something somewhere. The framework has become "irremediable."

**The scale of the resulting mess:** The final spliceosome comprises ~300 proteins and 5 snRNAs organized into five snRNP subcomplexes (U1, U2, U4/U6, U5, and the U4/U6.U5 tri-snRNP). Assembly requires ~8 ATP-dependent RNA helicases (DExH/D-box proteins) to mediate conformational rearrangements at each step. Correct splicing requires dozens of protein-protein and protein-RNA contacts, each individually essential, none individually sufficient. The machine assembles from scratch on every intron, then disassembles.

The critical software insight: *this complexity was never designed.* Nobody specified a spliceosome. The complexity is the sediment of 10,000 individually invisible neutral steps, each of which made reversal slightly less likely.

---

### 4. Scale of the Mess: Concrete Numbers

**Genome composition:**
- Introns constitute approximately 25% of the human genome (~800 Mb out of ~3.2 Gb) — roughly 4–5 times the size of all exon sequences combined [Genominfo 2015, citing primary genome analysis].
- Coding exons represent approximately 1–2% of the human genome.
- So introns occupy about 15–20x more genomic real estate than the sequences that actually encode protein.

**Intron density:**
- Average human gene: ~8 introns, average intron length ~3.4 kb [BioNumbers BNID 106732, from Venter et al. genome annotation].
- With ~20,000 protein-coding genes, there are roughly 160,000–200,000 introns to splice in the human transcriptome.
- The total length of intronic sequence per typical gene (~27 kb introns) dwarfs the coding sequence (~1.3 kb CDS).

**The spliceosome machinery:**
- 5 snRNAs (U1, U2, U4, U5, U6)
- ~311 distinct proteins identified in the most comprehensive proteomic analysis (Rappsilber et al. 2002, *Genome Res.*), of which 96 were novel at time of identification
- The review by Nilsen (2003, *BioEssays*) — citing Jurica & Moore (2003) — confirmed "as many as 300 distinct proteins and five RNAs, making it among the most complex macromolecular machines known"
- 8 ATP-dependent RNA helicases required for spliceosome rearrangements
- The spliceosome assembles de novo on each intron, progressing through at least 7 distinct conformational states (E, A, B, Bact, B*, C, P, ILS complexes), each stabilized by different protein subsets

**Energy cost:**
- The chemical steps of splicing are isoenergetic transesterifications (no net ATP consumption in the chemistry itself)
- But the spliceosome requires ~2 ATP molecules per splicing event for the conformational rearrangements driven by the DExH/D helicases [Will & Lührmann 2011, *Cold Spring Harb. Perspect. Biol.*]
- Lynch & Marinov (2015, *PNAS*) calculate that transcribing a typical eukaryotic gene with a total intron length of 5 kb increases the transcriptional cost by roughly 87% compared to an intron-free equivalent gene (from ~1.5×10⁵ ATP per gene to ~2.8×10⁵ ATP per gene, per transcript cycle). For genes with the human average intron complement (~27 kb total introns), the cost premium is substantially higher.
- The larger cost: not splicing itself, but *transcribing the introns* that will be discarded. Every nucleotide of every intron must be polymerized, then the intron RNA is discarded as a lariat. This is the main bioenergetic burden of the intronic load.
- Lynch & Marinov note that the relative cost of this extra transcription is sufficiently small per gene in large eukaryotic cells that it falls below the selection threshold — a key reason the system could evolve and persist neutrally.

---

### 5. The Punchline: Is This the Best Example?

**Is the spliceosome the best case for "spaghetti code"?** Among the candidates, it is uniquely compelling for several reasons:

1. **We know the clean ancestor.** Unlike most complex molecular machines, we have a living system that represents the ancestral state: group II introns are still doing self-splicing in bacterial genomes and organelles right now. The before-and-after comparison is unusually direct.

2. **The complexity is measurable and extreme.** A self-splicing intron requires no protein at all (in vitro, at high Mg²⁺). The human spliceosome requires ~300 proteins. The complexity increase has no functional counterpart — splicing accuracy is not substantially better; the basic chemistry is identical.

3. **Multiple named theorists have made this specific argument.** Stoltzfus 1999, Gray et al. 2010, Lukeš et al. 2011 all use spliceosomal evolution as their primary exhibit. The spliceosome is the canonical CNE example, the one that launched the whole framework.

4. **Irreversibility is established.** Unlike some CNE cases where the ancestral function could in principle be reconstructed, spliceosomal introns have degenerated so extensively that they cannot self-splice even in principle — the conserved sequence elements necessary for group II intron folding are gone. The ratchet has turned so many times that the spring is broken.

**Other contenders.** For completeness:
- RNA editing in kinetoplastids (trypanosomes) involves a 70-protein complex to edit thousands of sites, where the "ideal" solution would be to simply have correct sequences in the genome. Gray et al. 2010 covers this in the same *Science* paper.
- Mitochondrial tRNA processing in some lineages (Lai et al. 2025 in *TIBS*) offers a recent new case.
- But neither has the same clarity of known ancestor, quantified complexity differential, and deep primary literature that the spliceosome has.

**What biologists have explicitly said.** Gray et al. (2010) write: "We are proposing that the complexity we observe is an evolutionary ratchet: once the complexity originates, it is irremediable, because eliminating any component would be lethal." Muñoz-Gómez et al. (2021) open their review with the spliceosome as the paradigm case. Vosseberg & Snel (2017) conclude: "especially [neutral evolution] was responsible for the emergence of an enormously complex eukaryotic splicing machinery from simple self-splicing sequences."

The word "irremediable" is doing real work here. It's not just "complex" — it's complex in a way that *cannot be fixed*. There is no selection gradient that points back toward simplicity, because any simplification step kills the organism. This is a profound difference from engineered software, where refactoring is always possible in principle. In the genome, once you've locked yourself into the framework, refactoring is lethal.

---

## Key Findings

- **Group II introns are self-splicing ribozymes with a six-domain structure, found in bacteria/organelles, that use identical chemistry (two-step transesterification with lariat intermediate) to spliceosomal splicing.** Strong evidence; multiple independent structural and biochemical lines of evidence. [Costa 2022, Lambowitz & Zimmerly 2011]

- **Prp8, the largest and most conserved spliceosomal protein, has an RT-like domain structurally homologous to group II intron-encoded maturases, confirming evolutionary ancestry at the protein level.** Strong evidence; crystal structures at 1.2 Å [Zhao & Pyle 2016].

- **The 5 snRNAs (U1, U2, U4, U5, U6) evolved from fragments of a group II intron (the "five easy pieces" scenario), with U6 corresponding to group II Domain V, the catalytic core.** Strong evidence; structural equivalences established by cryo-EM [Galej et al. 2018].

- **The CNE mechanism — introns losing self-splicing capability once external factors were available, creating a one-way ratchet — is the consensus explanation for spliceosomal complexity among the relevant community of molecular evolutionists (Stoltzfus 1999, Gray et al. 2010, Lukeš et al. 2011, Vosseberg & Snel 2017).** Strong evidence; primary literature; 489+207+187 citations respectively. This is not a fringe view.

- **The spliceosome contains ~300 distinct proteins and 5 snRNAs** (Rappsilber et al. 2002, confirmed by Nilsen 2003). Strong evidence; proteomic data.

- **Introns occupy approximately 25% of the human genome, or about 4–5x the total exonic sequence.** Strong evidence; standard genomics references.

- **Average human gene has ~8 introns, average intron length ~3.4 kb, giving ~27 kb of intronic sequence per gene vs ~1.3 kb of coding sequence.** Strong evidence; BioNumbers / genome annotation data.

- **The primary energetic cost of the intronic load is transcriptional, not spliceosomal: producing intron RNA that will be discarded costs on the order of 87% more ATP per transcription cycle for a 5-kb intron complement, and proportionally more for the human average.** Strong evidence; Lynch & Marinov 2015 PNAS quantitative framework.

- **The system is "irremediable": spliceosomal introns have degenerated beyond the possibility of self-splicing, and any simplification of the spliceosome is lethal.** Strong evidence, logically derived from the absence of self-splicing activity and the essentiality of spliceosome components.

- **The spliceosome is the single most compelling example of CNE-driven complexity because (a) the ancestor is still alive and characterizable, (b) the complexity differential is quantifiable and extreme, and (c) it is the founding case study of the CNE framework itself.** Strong evidence; consensus among practitioners.

---

## Assessment

The evidence chain here is unusually clean. We have:
1. A living ancestor (group II introns in bacteria and organelles) that demonstrates the ancestral functionality.
2. A precise mechanism (CNE ratchet) that explains how self-contained function was converted to obligate dependency.
3. Detailed molecular homologies (Domain V = U6 snRNA; maturase RT = Prp8 RT domain) that confirm ancestry.
4. A quantified outcome: 0 proteins needed for ancestral function vs. ~300 for the derived state, with identical chemistry.

The CNE argument is not that selection played no role. It is that the *origin* of the complexity did not require selection — it required only that (a) there was something to suppress the deleterious effects of each new dependency and (b) the ratchet could not easily run backward. Both conditions are well-satisfied here.

The one genuine uncertainty is about the exact sequence of events during eukaryogenesis — what came first, the group II intron invasion or the early spliceosome? Vosseberg & Snel (2017) show the complexity didn't accumulate gradually but in bursts, and we lack an organism that represents a "half-assembled spliceosome." This is a real gap in the historical reconstruction. But the endpoint (300 proteins) and the starting point (self-splicing RNA) are both solid, and the CNE mechanism is the most parsimonious way to get from one to the other.

For the essay's purposes, this case study is vivid precisely because the software analogy is so exact: the intron *was* the function, the maturase *was* the helper library, the snRNAs *were* the fragmented modules, and the spliceosome *is* the accumulated framework. The intron can no longer run without the framework. Nobody built the framework — it just accreted, one neutral dependency at a time. And now you cannot remove it, because the intron would die.

This is what evolution looks like when selection is too weak to push back: not streamlined elegance, but irremediable complexity. The spliceosome is a machine that exists not because it is the best solution, but because it is the solution that became necessary.

---

## Sources

1. Costa, M. (2022). Group II Introns: Flexibility and Repurposing. *Frontiers in Molecular Biosciences*, 9:916157. DOI: 10.3389/fmolb.2022.916157 [open access]

2. Smathers, C.M., & Robart, A.R. (2019). The mechanism of splicing as told by group II introns: Ancestors of the spliceosome. *BBA Gene Regulatory Mechanisms*, 1862(11-12):195-203. DOI: 10.1016/j.bbagrm.2019.06.001

3. Vosseberg, J., & Snel, B. (2017). Domestication of self-splicing introns during eukaryogenesis: the rise of the complex spliceosomal machinery. *Biology Direct*, 12:30. DOI: 10.1186/s13062-017-0201-6 [open access]

4. Stoltzfus, A. (1999). On the Possibility of Constructive Neutral Evolution. *Journal of Molecular Evolution*, 49:169–181. DOI: 10.1007/PL00006540

5. Gray, M.W., Lukeš, J., Archibald, J.M., Keeling, P.J., & Doolittle, W.F. (2010). Irremediable Complexity? *Science*, 330:920–921. DOI: 10.1126/science.1198594

6. Lukeš, J., Archibald, J.M., Keeling, P.J., Doolittle, W.F., & Gray, M.W. (2011). How a neutral evolutionary ratchet can build cellular complexity. *IUBMB Life*, 63:528–537. DOI: 10.1002/iub.489

7. Muñoz-Gómez, S.A., Bilolikar, G., Wideman, J.G., & Geiler-Samerotte, K. (2021). Constructive Neutral Evolution 20 Years Later. *Journal of Molecular Evolution*, 89:172–182. DOI: 10.1007/s00239-021-09996-y [open access]

8. Brunet, T.D.P., & Doolittle, W.F. (2018). The generality of Constructive Neutral Evolution. *Biology & Philosophy*, 33:2. DOI: 10.1007/s10539-018-9614-6

9. Galej, W.P., Toor, N., Newman, A.J., & Nagai, K. (2018). Molecular Mechanism and Evolution of Nuclear Pre-mRNA and Group II Intron Splicing: Insights from Cryo-EM Structures. *Chemical Reviews*, 118:4156–4176. DOI: 10.1021/acs.chemrev.7b00499

10. Zhao, C., & Pyle, A.M. (2016). Crystal structures of a group II intron maturase reveal a missing link in spliceosome evolution. *Nature Structural & Molecular Biology*, 23:558–565. DOI: 10.1038/nsmb.3224

11. Rappsilber, J., Ryder, U., Lamond, A.I., & Mann, M. (2002). Large-Scale Proteomic Analysis of the Human Spliceosome. *Genome Research*, 12:1231–1245. DOI: 10.1101/gr.473902

12. Nilsen, T.W. (2003). The spliceosome: the most complex macromolecular machine in the cell? *BioEssays*, 25:1147–1149. DOI: 10.1002/bies.10394

13. Lambowitz, A.M., & Zimmerly, S. (2011). Group II introns: mobile ribozymes that invade DNA. *Cold Spring Harbor Perspectives in Biology*, 3:a003616. PMC3140690

14. Lynch, M., & Marinov, G.K. (2015). The bioenergetic costs of a gene. *PNAS*, 112:15690–15695. DOI: 10.1073/pnas.1514974112

15. Sharp, P.A. (1991). "Five Easy Pieces." *Science*, 254:663. DOI: 10.1126/science.1948046

16. Doolittle, W.F., Lukeš, J., Archibald, J.M., Keeling, P.J., & Gray, M.W. (2011). Comment on "Does constructive neutral evolution play an important role in the origin of cellular complexity?" *BioEssays*, 33:427–429. DOI: 10.1002/bies.201100039

17. Will, C.L., & Lührmann, R. (2011). Spliceosome Structure and Function. *Cold Spring Harbor Perspectives in Biology*, 3:a003707. PMC3119917

18. BioNumbers BNID 106732: Number of introns in typical human gene and average length. https://bionumbers.hms.harvard.edu/bionumber.aspx?id=106732
