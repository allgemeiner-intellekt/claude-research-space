# Deep Dive: The Biderman–Seger Co-Authorship Tension

## Question

Did Stella Biderman co-author the Seger et al. 2023 paper "Open-Sourcing Highly Capable Foundation Models" while publicly holding the opposite position? And what does this reveal about how "AI safety expert consensus" is constructed in policy papers?

## Investigation

### Step 1: Verify the co-authorship claim

The Q4 survey note stated that "Biderman had co-authored the Seger et al. multi-stakeholder paper — unusual given the papers take different positions; she was the dissenting voice there." This claim turns out to be **false as stated**, and the truth is both more mundane and more interesting.

**Primary sources checked for the Seger et al. paper (arXiv:2311.09227):**

- arXiv abstract page (https://arxiv.org/abs/2311.09227): Lists 22 authors, ending with Abhishek Gupta. No Biderman.
- Elizabeth Seger's own website (elizabethseger.com/open-source-model-sharing): Same 22-author list. No Biderman.
- Harvard ADS entry (ui.adsabs.harvard.edu/abs/arXiv:2311.09227): Same 22-author list.
- law-ai.org hosting page: Same 21-22 authors. No Biderman.
- GovAI official PDF (cdn.governance.ai): The **title page** and **internal title page** confirm the same 22 authors.

The official GovAI PDF's internal title page contains an **Acknowledgements** section that reads: "We thank the following people for feedback and comments: Andrew Trask, Ben Cottier, Herbie Bradley, Irene Solaiman, Norman Johnson, Peter Cihon, Shahar Avin, **Stella Biderman**, Toby Shevlane."

And directly below the acknowledgements, the paper contains a disclaimer: "Given the size of the group, inclusion as an author does not entail endorsement of all claims in the paper, nor does inclusion entail an endorsement on the part of any individual's organization."

**Biderman is in the acknowledgements, not the author list.** She provided feedback and comments — a reviewer role — not authorship.

### Step 2: Explain the Semantic Scholar error

Semantic Scholar (paperId: a0af35c5c343464bf353549d0a79ee68b199277a) lists 29 authors including Biderman as author #29, along with Andrew Trask, Ben Cottier, Herbie Bradley, Irene Solaiman, N. Johnson, Peter Cihon, and S. Avin — precisely the acknowledgement names. Semantic Scholar ingested the acknowledgement list as co-authors. This is a known failure mode in Semantic Scholar's automated metadata extraction: when papers have acknowledgement sections that list names in a format similar to author lists, the parser conflates the two.

This is the origin of the survey note's error. The survey agent used Semantic Scholar's author list as its source, which incorrectly included Biderman as a co-author.

### Step 3: What is Biderman's actual relationship to this paper?

Biderman provided feedback on a draft — meaning she read a version of the paper and gave comments. She is **not** listed as having any dissenting section within the paper, nor is she credited with any contribution. The acknowledgement form ("feedback and comments") is the weakest form of engagement — it does not imply agreement, partial agreement, or any identifiable intellectual contribution to the final document.

Her Senate testimony (October 2023, Schumer AI Insight Forum — confirmed from the primary document at schumer.senate.gov), submitted roughly at the same time the paper was posted (September 29, 2023), argues vigorously for open-source AI. Key passages:

- "Closed Models are not Safe: Their Dangers are Just Hidden" — explicit section heading
- "The alleged safety filters deployed on popular commercial models are much better at making models look safe than actually be safe."
- "The safety protocols that have been trumpeted as the solution by tech companies are very easily subverted and are frequently ineffective patches over deeper issues."
- "Companies are known to actively censor such research and regularly suspend accounts for researchers trying to test the limitations of their models."

She does not mention the Seger et al. paper in her Senate testimony. There is no public statement from Biderman about co-authoring, reviewing, or disagreeing with the Seger paper specifically.

### Step 4: What paper DID Biderman actually co-author that is adjacent to this debate?

Biderman is a confirmed co-author on Kapoor et al. (2024), "Position: On the Societal Impact of Open Foundation Models" (arXiv:2403.07918, published at ICML 2024 as an oral presentation). This paper — with 25 co-authors including Sayash Kapoor, Rishi Bommasani, Percy Liang, Arvind Narayanan, Alondra Nelson, and Stella Biderman — argues for a "grounded assessment" of open foundation models and finds that the marginal risk evidence is insufficient to justify restrictions at current capability levels. This is the paper that actually documents Biderman's position in a collaborative academic format — and it runs counter to the Seger paper's conclusions.

The survey agent likely confused the two papers: Biderman is an acknowledged reviewer of Seger et al. (2023) and a co-author of Kapoor et al. (2024). These are very different relationships.

### Step 5: Does the original claim have any residual validity?

The weakened version of the claim is: Biderman gave feedback on a paper she disagrees with, and the acknowledgment was published alongside a strong disclaimer that co-authorship (here: acknowledged reviewer) does not equal endorsement.

This is interesting in a different, narrower way than the original claim. The Seger paper explicitly acknowledges that people with different views provided input, and explicitly disclaims that inclusion implies endorsement. This is actually an unusually honest practice — most policy papers don't print such disclaimers. But it doesn't produce the "dissenting co-author" dynamic the survey note described.

### Step 6: The actual tension worth examining — what does the Seger paper's acknowledgment list tell us?

The acknowledgement list is itself revealing: Andrew Trask (Privacy ML), Irene Solaiman (Hugging Face, known for nuanced gradient-of-release work), Toby Shevlane (structured access advocate, GovAI), Peter Cihon (AI governance researcher), Shahar Avin (CSER), and Stella Biderman (EleutherAI, strong pro-open). The authors sought feedback from people across the spectrum — including one of the most prominent open-weight advocates. This is not a case of manufactured consensus. The paper does not present itself as consensus at all; it makes an argument, with the disclaimer that reviewers don't endorse all claims.

The irony the survey note was reaching for — that "AI safety expert consensus" is manufactured by co-authorship conventions — would be a real phenomenon worth investigating, but this paper is not a clean example of it. It would actually be a slightly stronger example of intellectual honesty: the Seger paper sought out and acknowledged a prominent critic (Biderman), published a disclaimer about what authorship means in large collaborative papers, and did not claim her review implied her agreement.

## Key Findings

- **Stella Biderman is NOT a co-author of Seger et al. 2023.** She is in the acknowledgements section as someone who provided "feedback and comments" on a draft. Strong evidence — confirmed from the official GovAI PDF, arXiv page, Elizabeth Seger's own website, and Harvard ADS. Multiple independent primary sources agree.

- **Semantic Scholar incorrectly lists Biderman as a co-author** of this paper, having apparently ingested the acknowledgements list as author metadata. This is the origin of the survey note's error, which relied on Semantic Scholar's author list. Moderate-to-strong evidence for this explanation — the 7 "extra" names on Semantic Scholar exactly match the acknowledgements section of the GovAI PDF.

- **The Seger paper contains an explicit disclaimer** on its title page: "inclusion as an author does not entail endorsement of all claims in the paper, nor does inclusion entail an endorsement on the part of any individual's organization." Strong evidence — read directly from the official PDF.

- **Biderman's actual position** is documented in her October 2023 Senate testimony (Schumer AI Insight Forum) and her co-authorship of Kapoor et al. 2024 (ICML oral). Both strongly pro-open-weight. Strong evidence — both primary sources confirmed.

- **The specific tension** the survey note flagged ("a co-author publicly dissenting from the paper they signed") does not exist in this case. Biderman reviewed the paper, disagreed with it (implied by her other positions), and was acknowledged — but she never signed onto it as a co-author.

- **The broader claim about manufactured consensus** is not disproved, but this paper is the wrong example. The Seger paper is notably transparent about its limitations in this regard, unlike many policy papers that project false unanimity.

## Assessment

The survey note's claim was factually incorrect at its most load-bearing point: Biderman was not a co-author of Seger et al. 2023. The error is traceable to a known Semantic Scholar metadata parsing failure that conflated the paper's acknowledgement section with its author list.

The rhetorically powerful story the review agent flagged — "an AI safety expert signed a paper she disagrees with, showing that consensus is manufactured by co-authorship conventions" — does not hold up. That story would require Biderman to appear on the author list, which she does not. What actually happened is more prosaic: she gave comments on a draft, the authors thanked her, and both parties moved on.

The **genuinely interesting residual** from this investigation is different. The Seger paper's acknowledgements include Biderman alongside Irene Solaiman, Toby Shevlane, and others from across the open/closed spectrum. The paper explicitly disclaims that being acknowledged implies agreement. This suggests the authors were aware they were operating in a contested space and tried to engage critics. Biderman's presence in the acknowledgements is not evidence of manufactured consensus — it's actually evidence against it.

What this investigation does confirm, in a different way from expected, is the **unreliability of Semantic Scholar as a primary source for author lists** in policy papers with large acknowledgement sections. Any research that cites "AI safety expert X co-authored paper Y arguing for Z" and traces that claim only to Semantic Scholar metadata should be verified against the actual PDF — the error pattern found here could recur in other large collaborative documents.

The report should not use the Biderman-Seger tension as a finding. It was an error in the survey notes. The report can instead note that Biderman provided feedback on the Seger paper (a true, verified fact) as evidence of genuine cross-community engagement — and that Biderman's actual peer-reviewed position is documented in Kapoor et al. 2024, which argues against restrictions at current capability levels.
