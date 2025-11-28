We sincerely thank Reviewer 3453 for the constructive and insightful feedback, and we greatly appreciate the recognition of our core ***motivation***—namely, that decentralized attention mismatches the centralized nature of MedTS—as well as the acknowledgment of CoTAR’s ***effectiveness***, ***efficiency***, and the ***thoroughness*** of our empirical evaluation.

Below, we address each concern in detail. (*Notably, we've uploaded a revised manuscript, all newly added contents are in **Red**, and all revised contents are in **Purple**.*)

### W.1 Clarification of the "Dual Tokenization" TeCh Framework.

Thank you for pointing this out — this is an excellent observation! 

Indeed, as indicated in our implementation and Table 6, TeCh is implemented as ***a general CoTAR-based framework***, in which the tokenization strategy (Temporal, Channel, or Dual) is ***a tunable architectural hyperparameter*** rather than a fixed design. In our experiments, we searched over these configurations to identify the most suitable inductive bias for each dataset. Therefore, the headline SOTA results correspond to the best-performing tokenization variant within the TeCh family, all sharing the same CoTAR module and overall architecture.

We thoroughly revised the paper to clarify this in the Introduction (*line 101-104*), the Related Work (*line 141-144*), the Method (*Section 4.2*), the Experiments (*line 457-464*), and the Conclusion (*line 481-483*).

### W.2 Clarification of CoTAR Computing (Equation 2).

We thank Reviewer 3453 for the suggestion to clarify Equation (2)—this important point was also echoed by Reviewer KGK1.

To fully address it and improve the presentation of CoTAR, we rewrote Equation (2) in the revised manuscript (*line 202-209*) as a clear, step-by-step definition of the module’s computation and **explicitly list the shapes of all corresponding terms**. We also refined the accompanying textual description surrounding Equation (2) to better articulate the computation flow of CoTAR. Furthermore, we provide a concrete pseudo-code in the Appendix (*Page 17, lines 900–912*) so that the exact data flow and dimensionality are unambiguous. We hope these changes resolve the confusion.

### W.3 Mismatch in Ablation Results.

Thanks for this helpful comment. Your intuition aligns with our original intention. 

We initially planned to include ablation results for all seven datasets, but doing so substantially reduced readability—***the tables became overly large, required very small fonts***, and disrupted the flow of the main paper. Thus, we reported four MedTS datasets and one HAR dataset as representative examples. The inconsistency between Table 4 and Table 5 was due to a preparation oversight; we have corrected Table 5 to fully align with Table 4 in the revised manuscript.

To ensure completeness without sacrificing readability, we now provide **the full ablation results for all datasets in the Appendix** (*Section C.3, Tables 7&8*). We hope this addresses the concern and offers a comprehensive view of TeCh’s behavior across all settings.

### W.4 Mismatch in Model Implementation.

Thanks for raising this important question regarding implementation consistency. 

Since CoTAR is designed as ***a seamless replacement for attention***, TeCh is indeed built on a Transformer encoder structure, with attention replaced by our CoTAR module. This is why we still follow the Transformer encoder naming convention.

Regarding file access, we suspect this may be due to a temporary network issue. We are able to consistently access all files on our side. We kindly invite the reviewer to try again using the direct [**link**](https://anonymous.4open.science/r/TeCh-24/layers/Transformer_EncDec.py). Moreover, the full implementation of TeCh—including the CoTAR module—is also provided in the uploaded **Supplementary Material**, where the *./layers/Transformer_EncDec.py* file can be accessed without any difficulty. 

We hope this clears up the concern and confirms that the released code faithfully implements CoTAR as described.

Finally, thank Reviewer 3453 for the thoughtful comments, which helped us to further strengthen the clarity and completeness of our work. We hope our response has addressed all the concerns raised.
