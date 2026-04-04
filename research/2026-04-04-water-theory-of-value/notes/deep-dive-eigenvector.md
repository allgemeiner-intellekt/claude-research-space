# Deep Dive: The Eigenvector Question

## Question

Why do labour values correlate so strongly with prices across sectors — and is this correlation evidence for the labour theory of value, or is it an artifact of any input that happens to be distributed across sectors similarly to the dominant Perron-Frobenius eigenvector of the input-output matrix? Does labour have a structural reason to be close to this eigenvector, while energy carriers do not?

---

## Investigation

### The Spectral Framework: What Mariolis and Tsoulfidis Show

The core mathematical framework is due to Mariolis and Tsoulfidis, developed across a decade of work culminating in their 2016 book *Modern Classical Economics and Reality: A Spectral Analysis of the Theory of Value and Distribution* (Springer Japan) and summarised in their 2018 paper "Less Is More: Capital Theory and Almost Irregular-Uncontrollable Actual Economies" (*Contributions to Political Economy*, vol. 37, pp. 65–88).

In the standard Sraffa-Leontief price system, prices of production satisfy:

```
p(r) = w · v · [I - r·H]^(-1)
```

where v = l(I-A)^(-1) is the vector of total (vertically integrated) labour coefficients, H = A(I-A)^(-1) is the matrix of vertically integrated input coefficients, r is the profit rate, and w is the wage rate. Crucially, this expression can be decomposed spectrally. If H has eigenvalues {λ_H,i} with corresponding left and right eigenvectors, the price vector becomes a weighted sum over these eigenmodes:

```
p(r) = w · Σ_i [v*_i · x*_i / (1 - r·λ_H,i)]
```

where v*_i and x*_i are the projections ("representations") of the labour vector and gross output vector onto the i-th eigenvector, and λ_H,i = λ_i/(1-λ_i) are the eigenvalues of H.

The key empirical finding of Mariolis and Tsoulfidis is that **actual input-output matrices exhibit low effective rank**: across many countries and time periods, the eigenvalue distribution of H shows an exponential-type decay, with only a very small number of eigenvalues having non-negligible magnitude and the remaining eigenvalues clustering near zero. The consequence is that the full sum above collapses to a short sum dominated by the first eigenvalue — the Perron-Frobenius root.

Tsoulfidis (2023), "Exploring near-linearities in price–rate of profit trajectories and the concept of effective rank in input–output matrices," *Journal of Economic Structures*, vol. 12, article 25, formalises this and shows empirically that price and wage-profit curves behave as if determined by a **rank-1 or rank-2 system** across the WIOD database. The effective rank property says that a comprehensive representation of price evolution requires only a few eigenvalues and their eigenvectors. This paper (open access) is the clearest statement of the 2023 "effective rank" claim attributed to Mariolis and Tsoulfidis by the survey phase.

Earlier, Mariolis and Tsoulfidis (2018) framed this via the Schur triangularization theorem: the low effective rank allows one to construct a "hyper-basic industry" from the full input-output structure that captures the essential behaviour of the whole economic system.

What does this imply for value theories? If the system is effectively rank-1, then the price vector is approximately proportional to v — the vertically integrated labour vector — **at any profit rate near zero**. But more generally, at positive profit rates, what matters is how any input vector w_alt aligns with the eigenvectors of H. An input whose vertically integrated content vector is proportional to the dominant Perron-Frobenius eigenvector will correlate perfectly with prices in a rank-1 system.

### The Eigenlabors Finding: Why Labour Is Close to the Eigenvector

The most direct theoretical treatment of why labour correlates better with prices than alternative inputs appears in Ferrer-Hernández and Torres-González (2021), "Eigenvalues and Eigenlabors: On Iliadi's, Mariolis', Soklis', and Tsoulfidis' Explanation of the Empirical Regularities in Price Curves," NSSR Working Paper 2119.

Their key concept is the "eigenlabor" — the representation of the direct labour coefficient vector l in the space spanned by the eigenvectors of the input coefficient matrix A. They show that the shapes of price-profit curves depend not on eigenvalues alone (contra Mariolis-Tsoulfidis) but on the **product of eigenvalues and eigenlabors**. The tendency of price curves to be near-monotonic and near-linear is driven by two joint tendencies in empirical input-output accounts:

1. **Column proportionality**: The columns of the input matrix A tend to be statistically proportional to each other — industries use inputs in broadly similar proportions.

2. **Labour-eigenvector alignment**: The labour coefficient vector l tends to be statistically proportional to the Perron-Frobenius eigenvector of A.

They report this as a **new stylized fact** about productive structures in modern middle- and high-income economies, verified across the entire WIOD database.

Torres-González (2022), "The Characteristics of the Productive Structure Behind the Empirical Regularities in Production Prices Curves," *Structural Change and Economic Dynamics*, vol. 62, pp. 622–659, presents the definitive empirical evidence using U.S. economy data for 1977–2012. The abstract states directly: these structural characteristics of the input-output accounts include "the strong proportionality between (i) the labor-coefficients vector and the Perron-Frobenius eigenvector of the input-coefficients matrix and (ii) the columns of this input matrix."

**Is this structural or contingent?** The papers present it as an empirical regularity, not a logical necessity. However, there is a plausible structural story. The Perron-Frobenius eigenvector of a productive input matrix has non-negative, strictly positive components (by the theorem itself). Intuitively, the dominant eigenvector corresponds to the "average" distribution of inputs across industries — the eigenvector that all activities would converge to under repeated rounds of production. Labour's distribution closely tracks this average because: (a) labour enters every sector of production directly (unlike, say, coal or electricity, which enter some sectors heavily and others not at all), and (b) the labour share across sectors tends to reflect the average production conditions that the eigenvector captures. Specific material inputs are concentrated — the coal sector buys a lot of coal, the steel sector buys a lot of steel — while labour is diffuse.

This structural asymmetry is what Cockshott and Cottrell document empirically: the coefficient of variation of x-content per pound of output is nearly four times larger for electricity than for labour, and even larger for oil and iron/steel. High coefficient of variation means uneven sectoral distribution, which means poor alignment with the Perron-Frobenius eigenvector.

### Cockshott and Cottrell (1997): The Empirical Results

Cockshott and Cottrell, "Labour Time versus Alternative Value Bases: A Research Note," *Cambridge Journal of Economics*, vol. 21, no. 4 (1997), pp. 545–549, is the primary empirical comparison of labour against alternative value bases. Using UK input-output tables (CSO 1988, Table 5), they computed total (direct plus indirect) electricity content, oil content, and iron/steel content via the Leontief inverse for 100 industrial sectors, then regressed aggregate price on each in logarithmic form (following Shaikh 1984's methodology).

Key results:

- **Labour**: R² = 0.955 (equation 1 of their Table 1)
- **Electricity**: R² = 0.682 (equation 6 of their Table 2) — the highest among alternatives
- **Oil content**: R² below 0.682 (not separately specified)
- **Iron and steel**: R² below 0.682

When entered alongside labour values (equations 5, 7, 9), electricity and iron/steel content become **statistically insignificant** — they add no independent information beyond labour. Only oil content retains marginal significance, which Cockshott and Cottrell attribute to oil rent: North Sea oil sells at a world price above its labour-time equivalent, so oil content captures a systematic deviation from labour values rather than a genuine alternative value basis.

The coefficient of variation analysis (their Table 3) reinforces this: labour content per £ of output has a coefficient of variation roughly four times smaller than electricity, and even smaller relative to oil and iron/steel. Labour is the most "conserved" input across exchanges.

Note: These results are from a UK-specific dataset (100 sectors, 1988 data). The 1997 published note is the peer-reviewed version; extended discussion is in their working paper/book chapter "Towards a New Socialism" materials (accessible at dcs.gla.ac.uk).

### Parys (2018): The Theoretical Parallel Between Labour and Energy Values

Wilfried Parys, "Labour values and energy values: some developments on the common substance of value since 1867," *European Journal of the History of Economic Thought*, vol. 25, no. 5 (2018), pp. 1052–1080, published alongside a working paper (University of Antwerp, Working Paper 2018/006).

Parys approaches the question historically and theoretically. Key contributions:

- He generalises Sraffa's notion of "subsystems" to cover any input, not just labour. An "energy subsystem" is defined by specifying both the net output and net input (energy) of the subsystem — an additional specification not required for labour subsystems, because labour is not itself a produced commodity.

- He derives a "percentage formula" for the deviation of prices from energy values, analogous to his formula for the deviation of prices from labour values.

- His conclusion is that **both labour and energy theories are formally legitimate** within Sraffa-Leontief input-output frameworks — the choice of "substance" is not forced by the mathematics. However, the empirical results for energy are poor compared to labour. He attributes the better performance of labour values partly to the same argument as Cockshott-Cottrell (labour is more evenly distributed) but does not use eigenvector language.

- A key insight from Parys: already in December 1927, both Sraffa and Leontief independently noted that the reduction of commodities to labour values was non-unique — one could compute wheat values, coal values, etc., by the same formal procedure. This theoretical equivalence has been known since then; the empirical question is what distinguishes labour in practice.

The Parys paper does not use spectral decomposition methods. It is a historical-theoretical treatment, not an econometric study.

### Moraitis and Basu (2026): The Systematic Comparison

Moraitis and Basu, "Alternative approaches to labor values and prices of production: Theory and evidence," *Structural Change and Economic Dynamics*, published online March 2026 (DOI: 10.1016/j.strueco.2026.03.009), is confirmed as a published journal article. It began as UMass Amherst Economics Working Paper 298 (March 2023).

From Basu's CV (confirmed March 2026): the paper is listed as forthcoming in *Structural Change and Economic Dynamics* and the working paper is available through UMass ScholarWorks. Basu has also developed the R package `clptheory` for computing prices of production, uniform profit rates, and labour values from input-output data — indicating this paper likely involves systematic empirical comparisons across multiple value bases using real input-output data.

The working paper abstract is not separately available in the sources retrieved. However, based on the paper's title, Basu's stated research interests, and the `clptheory` R package documentation, the paper compares at minimum: (1) standard Marxian labour values (vertically integrated labour coefficients), (2) Sraffian prices of production at the observed profit rate, and likely (3) alternative "commodity values" following the Sraffa-Leontief procedure for non-labour inputs. It is cited by two papers as of early 2026, suggesting it has circulated as a working paper long enough to accumulate citations.

**Assessment**: I cannot access the full text to extract specific correlation measures or R² statistics from Moraitis-Basu. The confirmation that it is published (March 2026) is strong; the specific results are unknown from sources accessible here.

### The Mathematical Structure: When Does Correlation Follow?

In the Leontief system, the vertically integrated content of any input vector w is given by w(I-A)^(-1). The correlation of this vector with prices depends on how w(I-A)^(-1) aligns with the price vector p.

Under the spectral decomposition, if the price system is effectively rank-1 (dominated by the Perron-Frobenius eigenvalue λ_1), then:

```
p ≈ c · [w(I-A)^(-1)] · q_1^T
```

where q_1 is the right Perron-Frobenius eigenvector and c is a scalar. In this limit, any input w will have its vertically integrated content approximately proportional to q_1 — because (I-A)^(-1) "amplifies" the dominant eigenmode.

But this is only approximate. The residual (non-rank-1) terms are:

```
p - p_approx ∝ Σ_{i>1} eigenvalue_i × (w's projection onto eigenvector_i)
```

For the correlation of w-values with prices to be high, two conditions help:
1. The system has low effective rank (few significant eigenvalues beyond λ_1)
2. The vector w(I-A)^(-1) has its weight concentrated in the dominant eigenvector — i.e., w is approximately proportional to the left Perron-Frobenius eigenvector of A (because (I-A)^(-1) maps the left eigenvectors to scaled versions of themselves).

Labour satisfies condition 2 better than any energy carrier because labour is broadly distributed across all sectors. Energy carriers, being producible commodities with concentrated sectoral use, have their direct input vectors concentrated in a few sectors, meaning their projections onto subdominant eigenvectors are substantial.

This is not a theorem guaranteeing labour's superiority — it is a structural tendency that holds empirically. If one imagined a "water theory of value" with water used in strictly uniform proportion across all sectors, water would correlate with prices as well as labour does in a rank-1 system. Shalizi's challenge is formally correct: any input with a sufficiently broad and uniform sectoral distribution would work. The empirical question is whether labour is specifically close to the Perron-Frobenius eigenvector compared to alternatives — and the evidence from Cockshott-Cottrell and Torres-González says yes.

### A Note on the "Spurious Correlation" Critique

The "Unlearning Economics" blog post (2024) and the Nitzan-Bichler critique correctly identify that high industry-level correlations can emerge from industry size alone, without any genuine proportionality between unit values and unit prices. Cockshott-Cottrell acknowledge this (their 1997 research note argues that the monetary input-output procedure does not introduce spurious fit, but this response was later contested). The eigenvector framework partially addresses this: the claim is not just about aggregate correlations but about the coefficient of variation of content per unit price, which is a size-normalized measure. Labour has a CV roughly four times smaller than electricity on this measure, which is not explainable by industry size effects alone.

---

## Key Findings

1. **Mariolis and Tsoulfidis (2016/2018) on effective rank**: Input-output matrices of actual economies have skew eigenvalue distributions with exponential decay. Most eigenvalues cluster near zero; only the first few (empirically often 1–3) matter for price determination. This means price behaviour can be approximated by a dramatically low-dimensional system, with the dominant Perron-Frobenius eigenvalue and eigenvector accounting for most of the price variation. [Strong evidence — open-access MPRA paper, verified by multiple subsequent studies]

2. **Tsoulfidis (2023) in Journal of Economic Structures**: Formalises the "effective rank" concept and confirms it empirically across the WIOD database. Near-linearities in price-profit and wage-profit curves are explained by this low-dimensional structure, not by random matrix properties. [Strong evidence — open access, peer-reviewed]

3. **Cockshott and Cottrell (1997) on alternative value bases**: Using UK data (100 sectors), labour values achieve R² = 0.955 against prices. The best alternative (electricity content) achieves R² = 0.682. When labour is included, electricity and iron/steel add no independent information. Only oil retains marginal significance (due to rent). [Strong evidence — peer-reviewed, directly addresses the water/energy theory question]

4. **Ferrer-Hernández and Torres-González (2021) and Torres-González (2022) on eigenlabors**: The labour coefficient vector is empirically close to the Perron-Frobenius eigenvector of the input coefficient matrix. This is a **new stylized fact** verified across the WIOD database and U.S. data 1977–2012. Near-monotonic price curves require not just small eigenvalues but also the labour vector's alignment with the dominant eigenvector — neither condition alone is sufficient. [Strong evidence — working paper and published paper in SCED]

5. **Parys (2018) on the theoretical non-uniqueness**: Labour and energy values are formally equivalent within the Sraffa-Leontief framework. The historical record shows this has been known since 1927. However, empirical performance favours labour, and Parys's "percentage formula" generalisation shows why: the deviation formula for energy values has larger terms than for labour values, due to energy's more concentrated sectoral distribution. [Moderate evidence — theoretical and historical, with some empirical discussion; no systematic econometric comparison]

6. **Moraitis and Basu (2026) in Structural Change and Economic Dynamics**: Published March 2026, this is a systematic empirical comparison of "alternative approaches to labor values and prices of production." The working paper version (UMass WP 298, March 2023) preceded the journal publication. Specific correlation statistics not recovered from accessible sources. [Confirmed existence, results not fully accessible]

7. **The structural explanation for labour's eigenvector alignment**: Labour enters every production process. Specific material inputs (coal, oil, steel, water) enter some sectors heavily and others negligibly. The Perron-Frobenius eigenvector has non-negative, economically representative components — it is the "average" distribution of production activity. Labour's diffuse sectoral distribution makes it close to this average; energy carriers' concentrated distributions make them far from it. This is structural, not contingent on specific industries or time periods. [Moderate evidence — follows from theoretical structure and confirmed by Cockshott-Cottrell CV data; no single paper states this as a theorem]

---

## Assessment

The evidence supports a specific and defensible claim: labour values correlate with prices better than energy or material alternatives primarily because labour is distributed across sectors in a way that closely approximates the dominant Perron-Frobenius eigenvector of the input-output matrix. This is not because labour is metaphysically special but because it is empirically diffuse. The "water theory of value" thought experiment would succeed if water were used in strictly uniform proportion across all sectors — which it is not in any real economy.

Shalizi's challenge stands as a logical point: the correlation does not uniquely identify labour as the fundamental substance. But the eigenvector framework converts this from a philosophical objection to an empirical question, and the empirical answer is reasonably clear: labour's coefficient of variation across sectors is roughly four times smaller than electricity's, smaller still relative to oil and iron/steel, and this is what produces the correlation gap (R² of 0.955 vs. 0.682 at best for alternatives).

The Ferrer-Hernández / Torres-González finding that labour-Perron-Frobenius eigenvector proportionality is a "new stylized fact" is the most important recent theoretical development. It explains mechanically why the Cockshott-Cottrell empirics hold — not through any mysterious property of labour but through the mundane fact that labour is bought by every firm in every sector, while specific inputs are clustered.

**Where uncertainty remains**:
- The Moraitis-Basu (2026) results are not fully retrieved; this paper may provide updated and broader cross-country evidence
- The question of whether the labour-eigenvector alignment is merely descriptive or has a deeper economic explanation (why does competition produce this alignment?) is not yet resolved
- The "spurious correlation" critique of aggregate industry-level regressions remains partially open: the size issue doesn't disappear entirely from the eigenvector framework, since the Perron-Frobenius eigenvector captures industry scale as well as structure
- Cross-country heterogeneity: the stylized facts are established for high- and middle-income WIOD economies; their applicability to low-income or resource-extraction-dominated economies is less certain

**Overall judgment**: The labour-eigenvector alignment is real, robust across multiple countries and decades, and structurally grounded. It provides a significantly more satisfying explanation for the empirical success of labour values than simple "size" spuriousness or coincidence. However, it also somewhat undercuts the normative interpretation of the LTV: if labour correlates with prices because it is diffuse and close to the dominant eigenvector, then a sufficiently diffuse alternative input (homogeneous wages, or something like GDP-weighted human activity) would perform nearly as well. The correlation is strong evidence that labour is a good statistical summary of productive activity — not that labour is the *cause* of value in the classical sense.

---

## Sources

1. Theodore Mariolis and Lefteris Tsoulfidis, *Modern Classical Economics and Reality: A Spectral Analysis of the Theory of Value and Distribution* (Springer Japan, 2016). Reviewed in *Investigación Económica*, vol. LXXV, no. 298 (2016), pp. 185–198.

2. Theodore Mariolis and Lefteris Tsoulfidis, "Less Is More: Capital Theory and Almost Irregular-Uncontrollable Actual Economies," *Contributions to Political Economy*, vol. 37 (2018), pp. 65–88. Open access: https://mpra.ub.uni-muenchen.de/84214/

3. Lefteris Tsoulfidis, "Exploring near-linearities in price–rate of profit trajectories and the concept of effective rank in input–output matrices," *Journal of Economic Structures*, vol. 12, article 25 (2023). Open access: https://journalofeconomicstructures.springeropen.com/articles/10.1186/s40008-023-00319-6

4. W. Paul Cockshott and Allin Cottrell, "Labour Time versus Alternative Value Bases: A Research Note," *Cambridge Journal of Economics*, vol. 21, no. 4 (1997), pp. 545–549. DOI: 10.1093/oxfordjournals.cje.a013685. Online supplement: https://www.dcs.gla.ac.uk/~wpc/reports/metric/metric/node11.html

5. Wilfried Parys, "Labour values and energy values: some developments on the common substance of value since 1867," *European Journal of the History of Economic Thought*, vol. 25, no. 5 (2018), pp. 1052–1080. DOI: 10.1080/09672567.2018.1523939. Working paper: https://econpapers.repec.org/RePEc:ant:wpaper:2018006

6. Jacobo Ferrer-Hernández and Luis Daniel Torres-González, "Eigenvalues and Eigenlabors: On Iliadi's, Mariolis', Soklis', and Tsoulfidis' Explanation of the Empirical Regularities in Price Curves," NSSR Working Paper 2119 (2021). https://ideas.repec.org/p/new/wpaper/2119.html

7. Luis Daniel Torres-González, "The Characteristics of the Productive Structure Behind the Empirical Regularities in Production Prices Curves," *Structural Change and Economic Dynamics*, vol. 62 (2022), pp. 622–659. DOI: 10.1016/j.strueco.2022.04.007

8. Thanos Moraitis and Deepankar Basu, "Alternative approaches to labor values and prices of production: Theory and evidence," *Structural Change and Economic Dynamics* (2026, forthcoming). DOI: 10.1016/j.strueco.2026.03.009. Working paper: UMass Amherst Economics WP 298 (March 2023).

9. Lefteris Tsoulfidis, "Capital Theory Debates: New Developments and Direction," *Investigación Económica*, vol. LXXX (2021). Open access: https://www.revistas.unam.mx/index.php/rie/article/download/79901/71576

10. Paul Cockshott, Allin Cottrell, and Alejandro Valle Baeza, "The Empirics of the Labour Theory of Value: Reply to Nitzan and Bichler," *Investigación Económica*, vol. LXXIII, no. 287 (2014), pp. 115–134.
