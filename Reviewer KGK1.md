Thanks to Reviewer KGK1 for the thorough review and supportive remarks. We’re glad you found our domain-driven **motivation** compelling (centralized physiological sources vs. decentralized attention), recognized CoTAR’s **strong performance** and linear **efficiency**, and valued **the breadth of our empirical evidence**. 

We address all the raised points below. (*Notably, we've uploaded a revised manuscript, all newly added contents are in **Red**, and all revised contents are in **Purple**.*)

### W.1 Clarification of Equation (2).

We sincerely appreciate the suggestion to clarify Equation (2), which also raised by Reviewer 3453.

To give more details and improve the readability of Equation (2), we rewrote it step-by-step and **explicitly list the shapes of all corresponding terms**. These changes can be found in the revised manuscript (*line 202-209*).  

We also refined the accompanying text before and after Equation (2) to better articulate the computation flow of CoTAR. Moreover, we provide a concrete pseudo-code in the Appendix (*Page 17, lines 900–912*) to better present the exact work flow of CoTAR. 

We hope these details resolve the confusion.

### W.2 Subject-independent Cross-validation.

Thanks for this insightful comment. You precisely highlighted how a fixed subject-independent split can mask method differences due to noisy subjects. This greatly informed our evaluation design and helped us more comprehensively validate the effectiveness of our method.

Following the suggestion, we conducted ***five-fold cross-validation based on subject IDs***, ensuring balanced classes in each fold to mitigate the bias of a fixed split. As shown in Table below, TeCh still consistently outperforms Medformer across all datasets. On APAVA, TeCh **improves Accuracy and F1-Score by +12.6% and +13.0%, respectively**; on PTB, the gains are +6.2% and +12.1%. TeCh also exhibits lower standard deviation (e.g., *6.79 vs. 9.71* on APAVA F1-Score), indicating stronger robustness. These results confirm that TeCh generalizes more effectively across subjects and **remains resilient to inter-subject noise**, benefiting from CoTAR’s centralized aggregating–redistributing mechanism. We have also included these result in the Appendix (*Section C.5, Table 10*).

|Method|ADFTD|ADFTD|APAVA|APAVA|TDBrain|TDBrain|PTB|PTB|PTB-XL|PTB-XL|
|-|-|-|-|-|-|-|-|-|-|-|
||Accuracy|F1-Score|Accuracy|F1-Score|Accuracy|F1-Score|Accuracy|F1-Score|Accuracy|F1-Score|
|Medformer|53.41 ± 3.05|49.03 ± 3.97|68.01 ± 9.13|66.63 ± 9.71|82.92 ± 9.03|81.13 ± 9.16|83.30 ± 5.46|72.46 ± 5.17|71.76 ± 0.66|61.10 ± 0.70|
|Tech (Ours)|**55.05 ± 2.43**|**49.82 ± 2.82**|**80.66 ± 6.53**|**79.62 ± 6.79**|**87.06 ± 6.71**|**86.00 ± 6.62**|**89.48 ± 3.18**|**84.59 ± 2.84**|**73.65 ± 0.41**|**62.79 ± 0.52**|

### W.3 Comparison with MedGNN.

Thanks for the suggestion to compare against more advanced SOTA methods such as MedGNN. We appreciate this recommendation and have conducted a direct comparison with MedGNN accordingly. The brief results (mean ± std) are as follows:

|Method|ADFTD|ADFTD|APAVA|APAVA|TDBrain|TDBrain|PTB|PTB|PTB-XL|PTB-XL|
|-|-|-|-|-|-|-|-|-|-|-|
||Accuracy|F1-Score|Accuracy|F1-Score|Accuracy|F1-Score|Accuracy|F1-Score|Accuracy|F1-Score|
|MedGNN|**56.12 ± 0.11**|**55.00 ± 0.24**|82.60 ± 0.35|80.25 ± 0.16|91.04 ± 0.09|91.04 ± 0.08|84.53 ± 0.28|80.40 ± 0.62|**73.87 ± 0.18**|**62.54 ± 0.20**|
|Tech (Ours)|54.54 ± 0.70|48.84 ± 1.72|**86.86 ± 1.09**|**86.30 ± 1.06**|**93.21 ± 0.61**|**93.20 ± 0.61** |**85.96 ± 2.52**|**81.97 ± 4.07**|73.53 ± 0.07|62.44 ± 0.27|

TeCh outperforms MedGNN on APAVA, TDBrain, and PTB with clear margins, and remain comparable on PTB-XL. While on ADFTD, MedGNN performs better. Overall, TeCh is superior to MedGNN on three datasets and competitive on the remaining two.

Since the results of MedGNN on FLAAP and UCI-HAR are currently missing, *we will reproduce MedGNN on these datasets and include the full results into the camera-ready version.*

### W.4 Limited Performance on ADFTD.

Thank you for pointing this out. We acknowledge that on the ADFTD dataset, TeCh underperforms on F1-Score compared with both Medformer and MedGNN, even though its Accuracy remains comparable. A likely reason is aggregation bias introduced by CoTAR’s centralized aggregating–redistributing mechanism. While this design enhances global consistency, it may unintentionally over-smooth features of rare classes, leading to reduced Recall for minority categories, to which the F1-Score is particularly sensitive.

In the future, we plan to mitigate this issue by incorporating minority-aware data augmentation and semi-supervised sampling strategies to better preserve and represent rare-class patterns.

Thank you again for all these thoughtful and helpful feedbacks. Your comments helped us refine the presentation and strengthen the evaluation. We hope the clarifications and added experiments adequately resolve the concerns raised.
