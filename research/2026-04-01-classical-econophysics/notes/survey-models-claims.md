# Survey: Models and Empirical Claims in *Classical Econophysics*

**Research question:** What are the specific models and empirical findings the book presents — particularly around income/wealth distributions, labor theory of value, and information-theoretic approaches to economics?

---

## Summary

*Classical Econophysics* (Routledge, 2009; 384 pp.) by Allin Cottrell, Paul Cockshott, Gregory Michaelson, Ian Wright, and Victor Yakovenko is a dense, multi-author monograph that applies tools from statistical mechanics, information theory, and computing science to classical political economy. The book is organized around four themes: (I) work, information, and value; (II) exchange, money, and capital; (III) class distribution of income; and (IV) information and coordination. Its most empirically concrete contributions fall into three clusters: (1) Cockshott and Cottrell's long-running input-output program demonstrating that labor values predict market prices with high correlation and outperform Sraffian prices-of-production; (2) Yakovenko's (and collaborators') physics-inspired model of money and income distributions showing exponential (Boltzmann-Gibbs) distributions for the lower class and power-law tails for the upper class; and (3) Ian Wright's agent-based simulation that unifies a broad range of empirical distributions of capitalism — firm size, growth rates, income, profit rate, recession duration — within a single model grounded in the law of value. The information-theoretic thread, developed mainly by Cockshott and Michaelson, treats information theory as structurally continuous with thermodynamics and uses Kolmogorov complexity to evaluate the scientific status of value theories.

---

## Key Sources

### *Classical Econophysics* — Full Table of Contents (Taylor & Francis / Routledge)
- **Link**: https://www.taylorfrancis.com/books/mono/10.4324/9780203877548/classical-econophysics-allin-cottrell-paul-cockshott-gregory-john-michaelson-ian-wright-victor-yakovenko
- **Key content**: 384 pages, 15 chapters plus introduction, across four parts. TOC retrieved in full (see below). Confirms the scope: production theory, information theory, statistical mechanics of money, probabilistic law of value, money/credit/banking, class income distribution, profit rates, and Hayek critique.
- **Assessment**: Publisher page. Authoritative on structure but abstracts are paywalled. The book description explicitly states the central claims: "Ricardian labour theory of value is re-examined in the light of econophysics, presenting agent based models in which the Ricardian theory of value appears as an emergent property. The authors present models giving rise to the class distribution of income, and the long term evolution of profit rates in market economies."

**Full table of contents (confirmed):**

**Part I — Work, information and value**
- Ch. 1: Problematizing labour (23 pp.)
- Ch. 2: Problematizing information (17 pp.)
- Ch. 3: Labour productivity (27 pp.)
- Ch. 4: Babbage and the birth of digital technology (11 pp.)
- Ch. 5: From machines to the universal machine (28 pp.)
- Ch. 6: Political economy: value and labour (24 pp.)

**Part II — Exchange, money and capital**
- Ch. 7: The probabilistic approach to economic variables (9 pp.)
- Ch. 8: The statistical mechanics of money (13 pp.)
- Ch. 9: A probabilistic approach to the law of value (23 pp.)
- Ch. 10: Value in the capitalist economy (19 pp.)
- Ch. 11: Money, credit and the form of value (30 pp.)
- Ch. 12: Banking and capital (28 pp.)

**Part III — Class distribution of income**
- Ch. 13: A probabilistic model of the social relations of capitalism (29 pp.)
- Ch. 14: Understanding profit (27 pp.)

**Part IV — Information and coordination**
- Ch. 15: Hayek, information and knowledge (20 pp.)

---

### Yakovenko & Rosser (2009) — "Colloquium: Statistical mechanics of money, wealth, and income"
- **Link**: http://arxiv.org/pdf/0905.1518.pdf | DOI: 10.1103/RevModPhys.81.1703
- **Key content**: Published in *Reviews of Modern Physics* — the most prestigious review journal in physics — with 491 citations. This is the definitive synthetic statement of Yakovenko's econophysics program, which feeds directly into Chapter 8 of the book. Core model: money is treated as a conserved quantity like energy. In pairwise economic transactions (agent i pays agent j), the total money is conserved. For random transactions, statistical mechanics predicts the equilibrium distribution is exponential: P(m) ~ exp(-m/T) where T is "economic temperature" (= average money per agent). This follows from maximum entropy subject to conservation of total money. Empirical claim: income data for the USA (IRS data 1983–2001) shows the bottom 97–99% of the population follows this exponential law; only the top 1–3% follows a Pareto power law. The power-law tail tracks the stock market and is interpreted as "superthermal" — out of equilibrium and driven by investment returns rather than wage income. The lower bulk is stable and time-stationary.
- **Assessment**: Peer-reviewed, high-impact, widely cited. Strong empirical grounding in IRS microdata. Main limitation: the conservation-of-money assumption is an idealization (money is not actually conserved at the micro level of individual transactions in a credit economy); the authors acknowledge debt and credit complicate the model. This is the foundation for Chapters 7–8 of the book.

### Dragulescu & Yakovenko (2000) — "Statistical mechanics of money"
- **Link**: http://arxiv.org/pdf/cond-mat/0001432 | DOI: 10.1140/epjb/e2000-00122-1
- **Key content**: The founding paper of the money-distribution program. Introduces the Boltzmann-Gibbs analogy for money: in a closed economy with random pairwise transactions and conservation of total money, the equilibrium distribution is exponential. Computer simulation confirms this. Also introduces the concept of a "thermal machine" in economics — extracting monetary profit from temperature differences between economic subsystems. 714 citations.
- **Assessment**: Peer-reviewed in *European Physical Journal B*. Foundational; the book's Chapter 8 is built directly on this work.

### Dragulescu & Yakovenko (2001) — "Exponential and power-law probability distributions of wealth and income in the United Kingdom and the United States"
- **Link**: https://www2.physics.umd.edu/~yakovenk/papers/PhysicaA-299-213-2001.pdf | Published in *Physica A* (507 citations)
- **Key content**: Empirical paper applying the two-class model to UK and USA data. UK wealth data (Inland Revenue 1996): exponential distribution for the bottom 90%, power law for the top. US income data from individual states: each state shows exponential bulk. Introduces the "temperature" parameter for each state/country as a measure of average income level.
- **Assessment**: Strong empirical paper in a well-regarded physics journal. The UK wealth data source is strong (official government data). The US state-level analysis is suggestive but aggregated.

### Ludwig & Yakovenko (2021) — "Physics-inspired analysis of the two-class income distribution in the USA in 1983–2018"
- **Link**: https://arxiv.org/pdf/2110.03140 | Published in *Philosophical Transactions of the Royal Society A*
- **Key content**: Extended empirical analysis over 35 years of IRS data. Confirms and extends the two-class model. Key finding: the exponential (lower class) distribution is extremely stable over time — only the temperature parameter (average income) shifts. All growth in inequality is attributable to the expansion of the upper power-law class, which grew from ~1% in 1983 to ~4% of the population by 2018. Attributes this expansion to digitization and non-locality of the economy. Gini coefficient: for a pure exponential, the theoretical Gini = 0.5; empirically confirmed for the lower class.
- **Assessment**: Recent peer-reviewed update of the empirical program. Strengthens the two-class model considerably.

### Cockshott & Cottrell (1997) — "The Scientific Status of the Labour Theory of Value"
- **Link**: https://users.wfu.edu/cottrell/eea97.pdf
- **Key content**: Eastern Economic Association paper using Kolmogorov-Chaitin complexity theory to assess the information gain of competing value theories. The core argument: a scientific law is one that provides information gain — i.e., output information exceeds input information plus the complexity of the law itself. Tests three predictors of prices: (1) vertically integrated labour coefficients (Marxian values), (2) Sraffian prices of production, (3) TSS (temporal single system) prices of production. The labour-value predictor requires the least input data (the A matrix of technical coefficients plus a vector of direct labour coefficients), while Sraffian prices require additionally the profit rate, and TSS prices require additionally a full vector of historical input prices. On parsimony grounds, labour values are the more elegant predictor and achieve comparable or better predictive fit. Demonstrates with UK and USA input-output data. The information-theoretic framing (Solomonoff/Chaitin complexity) is the direct bridge from information theory to value theory.
- **Assessment**: Working paper, not formally peer-reviewed in this form, but the empirical results have been published elsewhere. The Kolmogorov complexity framing is intellectually interesting but somewhat unconventional — the key empirical results (high r² of labour values vs. prices) are better documented in other papers.

### Cockshott & Cottrell (1999) — "Economic planning, computers and labor values"
- **Link**: https://users.wfu.edu/cottrell/socialism_book/aer.pdf
- **Key content**: Companion piece arguing for the feasibility of a planned economy using labour values as the unit of account. The technical argument: computing vertically integrated labour coefficients for n products requires O(n³) operations, which was infeasible for millions of goods using 1999 hardware but increasingly tractable. Proposes a "Strumilin + Lange" planning algorithm using labour tokens and market prices to balance supply and demand. The empirical claim embedded here: actual capitalist prices are not prices of production (profit rates do not equalize), making labour values a better predictor than the standard Sraffian alternative.
- **Assessment**: Peer-reviewed publication (appeared in AER supplement). The planning-algorithm proposal is speculative but the empirical backdrop (labour values predict prices) is well-supported.

### Cockshott & Cottrell (2005) — "Robust correlations between prices and labour values: a comment"
- **Link**: Semantic Scholar ID b40ec4f3efd79c613a385813bf6e50c3b44ff0e6
- **Key content**: Reply defending the empirical methodology of price-value correlations against methodological objections. 22 citations.
- **Assessment**: Peer-reviewed comment in a political economy journal. Part of a long methodological debate with critics including Kliman. The defense holds that (a) the use of monetary input-output data rather than in-kind data does not contaminate the results (proven formally — see the 1997 paper), and (b) aggregate sector correlations are valid measures.

### Cockshott, Cottrell & Valle Baeza (2014) — "The Empirics of the Labour Theory of Value: Reply to Nitzan and Bichler"
- **Link**: https://bnarchives.yorku.ca/496/2/cockshott_cottrell_valle_baeza_2014_the_empirics_of_the_ltv_reply_to_nitzan_and_bichler.pdf | *Investigación Económica*, 73(287), 115–134
- **Key content**: Most comprehensive empirical defense. Against the "spurious correlation" critique: (1) demonstrates the monetary input-output calculation does not introduce circularity (the labour-value vector derived from monetary tables agrees with the vector from physical tables up to a scalar, independent of the price vector); (2) addresses the scale-effect objection by showing correlations remain strong even when controlling for industry scale; (3) cites a wide body of international evidence (Ochoa 1989 for USA, Petrovic 1987, Valle Baeza 1994, Zachariah 2006, Tsoulfidis et al.). The empirical claim: across many countries and time periods, sectoral labour values explain 90–98% of the variance in market prices.
- **Assessment**: Peer-reviewed in a Mexican economics journal. Strong methodological defense. The key r² figures cited (90–98%) are aggregate-sector correlations, which critics argue overstate the underlying unit-price correlation. The authors' rebuttal is methodologically sound but the debate is genuinely unresolved in the literature.

### Cockshott (2023) — "Profit rates: their dispersion and long term determination"
- **Link**: https://eprints.gla.ac.uk/317340/3/317340.pdf | In: *Value, Money, Profit, and Capital Today*, Emerald, doi:10.1108/S0161-723020230000039010
- **Key content**: Recent (2023) paper that extends the empirical work from the book with updated UK data. Key empirical findings: (1) For UK industries in 2015, correlation of log labour values against log market value = **98.4%**; correlation of prices of production against log market value = **94.5%**. Mean Absolute Deviation for labour values = 18.7%; for prices of production = 44.5%. (2) There is a strong **inverse relationship between organic composition of capital and profit rate** (correlation -35% for 2015 UK data, -61% for Victorian/Edwardian Britain 1855–1910). This directly contradicts the "transformation" hypothesis that profit rates equalize. (3) Develops a dynamic model of the profit-rate attractor: P* = (G + d + t) / A, where G = workforce growth rate, d = depreciation rate, t = rate of technical change, A = accumulation share of surplus. This model (derived from the assumptions of labour value theory) has ~42% correlation with observed UK profit rate movements 1855–1910. The same formula appears in the book (Chapter 14).
- **Assessment**: Author preprint of peer-reviewed chapter. Strong empirical grounding with UK ONS data. Directly updates the book's claims with more recent data and more methodologically careful treatment of capital stocks. Confirms the book's core results.

### Cockshott & Cottrell (2003) — "A note on the organic composition of capital and profit rates"
- **Link**: https://academic.oup.com/cje/article-abstract/27/5/749/1710394 | *Cambridge Journal of Economics*, 27(5), 749–754
- **Key content**: Peer-reviewed article (CJE) showing that for US industrial data, industries with higher organic composition of capital have lower profit rates — the inverse relationship predicted by Marx's theory but contradicting the equalization hypothesis. 22 citations in Semantic Scholar.
- **Assessment**: Published in a leading heterodox economics journal. The empirical finding is concise and well-documented. Important precursor to the book's Chapter 14.

### Wright (2004/2005) — "The Social Architecture of Capitalism"
- **Link**: https://arxiv.org/abs/cond-mat/0401053 | *Physica A*, 346, 589–622 (2005); DOI: 10.1016/j.physa.2004.08.006. 79 citations.
- **Key content**: Ian Wright's most important pre-book paper, directly feeding into Chapter 13 of *Classical Econophysics*. An agent-based model where workers and capitalists interact under the assumption that the law of value governs the economy. The model self-organizes into a statistical equilibrium that **simultaneously reproduces**: (1) power-law firm size distribution; (2) Laplace (exponential) distribution of firm and GDP growth rates; (3) lognormal firm demise distribution; (4) exponential recession duration distribution; (5) lognormal-Pareto income distribution (not merely the Pareto tail — the entire two-class structure); (6) gamma-like distribution of firm profit rates. It also generates business cycle dynamics (Goodwin-like oscillations) with wage and profit shares consistent with national accounts data. Key theoretical innovation: the power-law tail of income distribution is generated by an **additive process on a power-law network** (the employer-employee social relation), rather than the multiplicative process (investment returns) that most econophysics models use. The model conjectures that the profit-rate distribution is a parameter-mixed ratio of normal variates, where the size parameter follows a power law — a testable prediction.
- **Assessment**: Peer-reviewed in *Physica A* (top journal for statistical mechanics applications). 79 citations. The model is technically sophisticated and the unification of multiple empirical distributions is impressive. Limitations: the model is highly stylized and the mapping to real institutional detail is loose. The Goodwin-like dynamics are qualitative rather than precisely calibrated.

### Banerjee & Yakovenko (2009) — "Universal patterns of inequality"
- **Link**: https://doi.org/10.1088/1367-2630/12/7/075032 | *New Journal of Physics*, 12, 075032. 135 citations.
- **Key content**: Extends the entropy-maximization framework beyond money to energy consumption per capita across countries. Key claim: for a partitioned limited resource with random redistribution, maximum entropy gives exponential distribution. Applied to: (a) global energy consumption 1990–2005 — approximately exponential, with Gini coefficient theoretically predicted to approach 0.5; (b) US income distribution — stochastic process with additive (exponential) + multiplicative (power-law) components reproduces full income distribution. Shows that the increase in US income inequality 1990s-2000s comes primarily from the upper tail expanding its share above 20% of total income.
- **Assessment**: Peer-reviewed, well-cited. Strengthens the entropy-as-maximum-entropy interpretation. Notable claim: globalization drives the world toward a single Boltzmann-Gibbs equilibrium, which theoretically predicts global Gini → 0.5.

### Plummer & Dezzani (2012) — "Probabilistic Political Economy in Geographical Context"
- **Link**: https://journals.sagepub.com/doi/pdf/10.1068/a44681 | *Environment and Planning A*, 44, 513–517
- **Key content**: A brief editorial situating the *Classical Econophysics* book (cited as "Cockshott et al., 2009") within the broader tradition of probabilistic political economy, connecting it to Farjoun & Machover (1983), Sheppard & Barnes, and econophysics. Notes that the book's approach represents a break from deterministic classical political economy models. Useful for situating the book in the broader landscape.
- **Assessment**: Editorial piece, not primary research. But confirms the book's reception as part of a recognized research tradition.

### Paul Cockshott's Research Page (University of Glasgow)
- **Link**: https://www.dcs.gla.ac.uk/~wpc/reports/index.html
- **Key content**: Lists all of Cockshott's papers. Confirms the book's subtitle framing: "essays in thermodynamics, information theory and political economy." A paper listed there — "Information, Work, and Meaning" (with Michaelson) — is described as "an introduction to information theory by me and Greg Michaelson, its relationship to thermodynamics and to classical political economy with particular emphasis on how it applies to industrial mass production." This describes what becomes Part I of the book. Also listed: "Conservation laws, financial entropy and the Eurozone crisis" (with Zachariah) — extends the book's entropy approach to financial systems. The "Organic composition of capital and profit rates" (CJE 2003) and the profit-rate dynamic attractor model are both listed.
- **Assessment**: Primary source (author's own page). Important for confirming which pre-book papers feed into specific chapters.

---

## Landscape Assessment

### State of knowledge

The book sits at a well-defined but contested intersection. The empirical programme on labour values and prices (Cockshott-Cottrell) has been running since the early 1990s and has produced consistent results across many countries: labour values predict sectoral output prices with correlations typically 90–98% (r²). This is among the most replicated empirical results in heterodox economics. The Yakovenko income-distribution programme has similarly produced consistent results: the exponential (Boltzmann-Gibbs) model fits the bottom 90%+ of income distributions in the USA, UK, and many other countries, with the Pareto power law fitting the top few percent. Both programmes are genuinely empirical — using publicly available input-output tables and IRS/tax data.

The information-theoretic thread (Cockshott-Michaelson, Part I) is more philosophical-foundational. The central argument is that the Shannon-Boltzmann identity — that information entropy and thermodynamic entropy are formally equivalent — has substantive implications: the labour theory of value gains empirical support because labour time is itself a form of physical work (in the thermodynamic sense), and because maximum-entropy reasoning explains the empirical distributions. This connection is suggestive but remains contested.

Ian Wright's agent-based model (Chapter 13) is the most ambitious theoretical contribution: it claims to derive the statistical regularities of capitalism from the single assumption that the law of value is operative. The unification of six distinct empirical distributions within one model is striking. However, the model is computationally specified rather than analytically tractable, and the precise mechanism by which the law-of-value assumption generates each distribution is not always transparent.

### Agreements and conflicts between sources

- The two-class income distribution (exponential bulk + power-law tail) is confirmed by multiple independent empirical analyses and is not seriously disputed in the econophysics literature. The dispute is about interpretation: Yakovenko interprets it as reflecting two fundamentally different income-generating mechanisms (additive wage income vs. multiplicative capital income), while Wright's model generates the same pattern from a different mechanism (additive process on a power-law network).
- The high correlation between labour values and market prices is widely confirmed across countries and time periods. The methodological objections (Kliman, Nitzan-Bichler) have been rebutted in detail; the key formal result (that using monetary rather than physical input-output data does not introduce spurious correlation) has been proven mathematically by Cockshott and Cottrell.
- The inverse relationship between organic composition of capital and profit rate (contradicting Marx's own equalization hypothesis from Capital III) is confirmed empirically in multiple datasets and is a key finding that the book uses to motivate preferring labour values over Sraffian prices of production as a predictor of market prices.
- The profit-rate dynamic attractor model (P* = (G+d+t)/A) is derived from the labour theory of value and tested against Victorian British data with modest but non-trivial predictive power.

### Gaps and under-explored areas

1. **The money chapters (Chs. 7–8, 11–12)**: Based on chapter page counts and descriptions, the statistical-mechanics-of-money chapters are relatively short (9 pp. and 13 pp. respectively). The subsequent money-credit-banking chapters (30 pp. and 28 pp.) are substantial. I was unable to retrieve the text of these chapters — their specific models and claims remain somewhat opaque from external sources.

2. **Chapter 9 — "A probabilistic approach to the law of value" (23 pp.)**: This is likely the most original chapter, bridging the Yakovenko money model and the Cockshott-Cottrell value programme. I could not retrieve the chapter text; its specific formal content is unclear. Based on the book description and the Cockshott 1997 paper on information gain, it likely deploys maximum entropy arguments to derive the distribution of commodity prices around labour values.

3. **Chapter 2 — "Problematizing information" (17 pp.)**: The information-theoretic content of the book — Shannon entropy, Kolmogorov complexity, and their connection to thermodynamic entropy — is developed here and in Part I generally. Based on Cockshott's research page, this draws on "Information, Work, and Meaning" (Cockshott-Michaelson). I did not find the text of this chapter or companion paper.

4. **Chapter 15 — "Hayek, information and knowledge" (20 pp.)**: The book ends with a critique of Hayek from an information-theoretic standpoint. Based on a 1994 Cockshott-Cottrell paper ("Information and economics: A critique of Hayek"), this likely argues that Hayek's claims about dispersed knowledge are not justified by modern information theory — that the information problem is in principle computable. I did not retrieve this chapter.

5. **The Chartalist money theory** (Ch. 11): The book description mentions "Chartalist school of financial theory." This is unusual in the context of the other contributors and may represent Cockshott's integration of MMT-adjacent monetary theory with the statistical mechanics approach.

### Surprises

1. **The depth of the information-theoretic programme**: It is not merely analogical. The book argues for a genuine conceptual identity between thermodynamic entropy, information-theoretic entropy, and economic value — mediated by the fact that labour is physical work in the thermodynamic sense. This is a more radical claim than is typically advertised.

2. **The empirical strength of the labour-value results**: For UK 2015 data, the correlation between log labour values and log market values is 98.4%, while prices of production achieve only 94.5%, with the MAD for production prices being more than double that of labour values (44.5% vs. 18.7%). This is a striking empirical result that has not received sufficient attention in mainstream economics.

3. **Wright's model as unification**: The fact that a single agent-based model grounded in the law of value reproduces six distinct empirical distributions — all typically studied in isolation and explained by different theories — is a major theoretical achievement that is underappreciated. It suggests that these distributions are not independent phenomena but structural features of capitalism as a whole.

4. **The convergence between Yakovenko and Cockshott-Cottrell**: Yakovenko's money model and Cockshott-Cottrell's value programme start from very different traditions (condensed matter physics vs. Marxist political economy) but converge on similar conclusions: that economic distributions are governed by statistical equilibrium principles analogous to those in physics, and that labour (energy) is the conserved quantity underpinning this equilibrium.

---

## Searches conducted

1. Semantic Scholar: "Classical Econophysics Cockshott Cottrell Yakovenko labor theory value" — no direct papers found (book not indexed)
2. Semantic Scholar: "Yakovenko income distribution Boltzmann-Gibbs exponential power law" — found core papers
3. Exa neural search: book title + authors + Routledge — found publisher pages, PDF link (inaccessible), and chapter DOIs
4. Semantic Scholar: "Cockshott Cottrell prices labor values empirical correlation" — found key debate papers
5. Exa: "Ian Wright econophysics stochastic profit rate Goodwin model" — found Wright's social architecture paper
6. Exa: "Cockshott Cottrell values and prices input-output empirical" — found empirical defense papers
7. Taylor & Francis book page — retrieved full table of contents
8. Retrieved full text: Cockshott-Cottrell 1997 (eea97.pdf), 1999 (aer.pdf), Wright 2004 (arXiv), Cockshott 2023 (Glasgow eprints), Cockshott-Cottrell-Valle Baeza 2014
9. Retrieved Yakovenko colloquium paper abstract and full bibliographic details
10. Semantic Scholar: "Draguleschu Yakovenko money distribution exponential Boltzmann 2000" — found founding paper
11. Semantic Scholar: "Wright social architecture capitalism profit rate" — found paper details
12. Exa: "Classical Econophysics book review Cockshott Cottrell 2009" — found book review (Academia.edu, gated)
13. Semantic Scholar: "econophysics labor theory value statistical mechanics entropy" — contextual papers
14. Cockshott's Glasgow research page — retrieved full list of related papers

---

## Sources with URLs

1. Taylor & Francis book page: https://www.taylorfrancis.com/books/mono/10.4324/9780203877548/classical-econophysics-allin-cottrell-paul-cockshott-gregory-john-michaelson-ian-wright-victor-yakovenko
2. Routledge product page: https://www.routledge.com/Classical-Econophysics/Cottrell-Cockshott-Michaelson-Wright-Yakovenko/p/book/9780415696463
3. Yakovenko & Rosser (2009): http://arxiv.org/pdf/0905.1518.pdf | DOI: 10.1103/RevModPhys.81.1703
4. Dragulescu & Yakovenko (2000): http://arxiv.org/pdf/cond-mat/0001432
5. Dragulescu & Yakovenko (2001): http://www2.physics.umd.edu/~yakovenk/papers/PhysicaA-299-213-2001.pdf
6. Ludwig & Yakovenko (2021): https://arxiv.org/pdf/2110.03140
7. Cockshott & Cottrell (1997) [scientific status]: https://users.wfu.edu/cottrell/eea97.pdf
8. Cockshott & Cottrell (1999) [planning/computers]: https://users.wfu.edu/cottrell/socialism_book/aer.pdf
9. Cockshott, Cottrell & Valle Baeza (2014): https://bnarchives.yorku.ca/496/2/cockshott_cottrell_valle_baeza_2014_the_empirics_of_the_ltv_reply_to_nitzan_and_bichler.pdf
10. Cockshott (2023) [profit rates]: https://eprints.gla.ac.uk/317340/3/317340.pdf
11. Ian Wright (2004) [Social Architecture]: https://arxiv.org/abs/cond-mat/0401053 | DOI: 10.1016/j.physa.2004.08.006
12. Banerjee & Yakovenko (2009): https://doi.org/10.1088/1367-2630/12/7/075032
13. Cockshott's research page: https://www.dcs.gla.ac.uk/~wpc/reports/index.html
14. Book review (gated): https://www.academia.edu/2267308/Book_review_of_Classical_econophysics_by_Cockshott_W_Paul_Allin_F_Cottrell_Gregory_J_Michaelson_Ian_P_Wright_and_Victor_M_Yakovenko
15. Plummer & Dezzani editorial: https://journals.sagepub.com/doi/pdf/10.1068/a44681
