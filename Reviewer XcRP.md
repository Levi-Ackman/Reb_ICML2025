## Reviewer XcRP

Thanks to Reviewer XcRP for the constructive comments, especially the recognition of our ***conceptual framing***, the ***linear complexity*** of CoTAR, and ***the rigor and reproducibility of our experiments*** (seven datasets, multiple metrics, comprehensive experiments, and released code). 

We address all noted concerns below. (*Notably, we've uploaded a revised manuscript, all newly added contents are in **Red**, and all revised contents are in **Purple**.*)

### W.1 Quantitative Validation of Centralization.

Thanks for raising this critical question, which inspires us to explore a quantitative analysis (in *Appendix C.6*) of the current MedTS. 

We introduce two metrics, Spectral Centralization Index (SCI) *[1]* and Dynamic Influence Centralization (DIC) *[2]*—*details can be found in the revised manuscript*—to measure the spatial and temporal centralization, respectively. *The higher value indicates a higher centralization*. We also include three general-purpose datasets (energy: ETTh2, ETTm2; climate: Weather) for comparison.

||ADFTD|APAVA|TDBrain|PTB|PTB-XL|ETTh2|ETTm2|Weather|
|-|-|-|-|-|-|-|-|-|
|**SCI**|0.918|0.520|0.616|0.622|0.652 |0.397|0.296|0.381|
|**DIC**|0.668|0.731|0.747|0.825|0.777 |0.241|0.119|0.342|

Across both metrics, MedTS shows consistently higher values compared to general-purpose datasets. This confirms that MedTS inherently exhibits a higher centralization, whereas energy and climate datasets are more decentralized. 

These findings quantitatively validate our hypothesis and further justify why TeCh’s centralized aggregating–redistributing design is especially effective for MedTS.

### W.2 Additional Comparisons with GAFormer and CATS.

We thank the reviewer for highlighting **GAFormer** *[3]* and **CATS** *[4]* as two highly relevant works that merit further discussion.

In response, we have added *Section C.4* in the revised Appendix, providing focused analysis and direct comparison. A summary is below:

**GAFormer vs. TeCh:**

* **Similarity:** Both capture dual dependencies across temporal and channel.
* **Difference:** GAFormer is *Transformer-based* and relies on *decentralized quadratic attention* for **forecasting**. TeCh instead employs a *centralized CoTAR module* with *Adaptive Dual Tokenization*, achieving *linear complexity* and *physiologically aligned* modeling for **MedTS classification**.

**CATS vs. TeCh:**

* **Similarity:** Both utilize global or auxiliary tokens for information aggregation and redistribution.
* **Difference:** CATS uses *static, parameterized auxiliary tokens* with decentralized attention. TeCh generates a *data-dependent core token* via CoTAR and enforces *centralized communication*, offering improved robustness under subject variability.

Since neither GAFormer nor CATS provides publicly available code or sufficient implementation details, we adopt **Leddam** *[5]* and **TimeXer** *[6]* as the closest reproducible counterparts in our comparative experiments, respectively.

|Method|ADFTD|ADFTD|APAVA|APAVA|TDBrain|TDBrain|PTB|PTB|PTB-XL|PTB-XL|
|-|-|-|-|-|-|-|-|-|-|-|
||Accuracy|F1-Score|Accuracy|F1-Score|Accuracy|F1-Score|Accuracy|F1-Score|Accuracy|F1-Score|
|Leddam| 53.14 ± 0.67| 46.64 ± 0.80|75.92 ± 1.78|74.08 ± 2.38|71.27 ± 0.88| 71.22 ± 0.97|83.84 ± 1.61|78.76 ± 2.77|67.41 ± 0.38| 51.84 ± 0.58|
|TimeXer|52.96 ± 0.50| 43.41 ± 0.85|72.44 ± 0.43|70.09 ± 0.86|72.48 ± 1.57|72.56 ± 1.45|83.32 ± 0.72|78.43 ± 0.99|66.14 ± 0.18|50.00 ± 0.30|
|Tech (Ours)|**54.54 ± 0.70**|**48.84 ± 1.72**|**86.86 ± 1.09**|**86.30 ± 1.06**|**93.21 ± 0.61**|**93.20 ± 0.61**|**85.96 ± 2.52**|**81.97 ± 4.07**|**73.53 ± 0.07**|**62.44 ± 0.27**|

Across all datasets and metrics, TeCh demonstrates clear and consistent improvements over both Leddam and TimeXer, further supporting the effectiveness of TeCh.

We kindly refer the reviewer to the revised manuscript for more details.

### W.3 Different Hyperparameters across Datasets.

Thank you for bringing this up. Using dataset-specific hyperparameters is ***a common and well-established practice*** in deep learning, including prior MedTS work (e.g., Medformer *[7]*). The MedTS datasets differ greatly in temporal sampling rate and channel interaction structure, so choosing the appropriate tokenization variant per dataset is necessary for practical deployment. Thereby, in our experiments, we search over these hyperparameters to identify ***the most suitable inductive bias*** for each dataset.

### W.4 Visualization and Interpretation of the Core Token.

We agree that assessing whether the core token reflects meaningful physiological processes is important. We thank the reviewer for prompting this clarification, which strengthens the interpretability of CoTAR. In the revised Appendix (*Section C.7*), we added a dedicated analysis with visualization (*Figure.5*).

We summarize the findings below:

* **Temporal embedding space:** The core token consistently lies near the center of all temporal representations, capturing a global temporal state analogous to slow neural rhythms in EEG (e.g., alpha/beta coherence) or beat-to-beat cycle integration in ECG.
* **Channel embedding space:** The core token occupies a central position, summarizing cross-channel coordination, consistent with EEG frontoparietal hubs or ECG pacemaker-driven myocardial synchronization.

For more information, we kindly refer the reviewer to the revised manuscript. These findings indicate that the core token is not arbitrary; it encodes a centralized, physiologically interpretable representation reflecting inherent coordination in MedTS signals.

We again thank Reviewer XcRP for all the helpful feedback, which has driven us to broaden our comparison and explore analysis of the core token. These efforts further strengthen the rigor and completeness of our work. 


*[1] Principal component analysis: a review and recent developments.*

*[2] Granger causality analysis in neuroscience and neuroimaging.*

*[3] GAFormer: Enhancing time-series transformers through group-aware embeddings.*

*[4] CATS: Enhancing Multivariate Time Series Forecasting by Constructing Auxiliary Time Series as Exogenous Variables.*

*[5] Revitalizing Multivariate Time Series Forecasting: Learnable Decomposition with Inter-Series Dependencies and Intra-Series Variations Modeling.*

*[6] Timemixer: Decomposable multiscale mixing for time series forecasting.*

*[7] Medformer: A Multi-Granularity Patching Transformer for Medical Time-Series Classification*
