Additional comparison with **iTransformer** and **PatchTST** under **Hyperparameter Search**. 

We chose the ***input-96-forecast-720*** task.

Including learning_rate $lr \in [1e−5, 1e−4, 1e-3\]$, batch size $bs \in [32, 64, 128\]$, Number od Encoder $N \in [1,2,3,4\]$, 
and Dimension of Model $D \in [128, 256, 512\]$. 

*We set the training epochs to 100 (to balance the extra epochs trained under the `Key Frequency Enhanced Training Strategy').*

|Dataset|iTransformer|PatchTST|ReFocus|
|-|-|-|-|
||MSE / MAE| MSE / MAE| MSE / MAE|
| **ETTm1**      | 0.486 / 0.455   | **0.454** / 0.439  | 0.463 / **0.437**  |
| **ETTm2**      | 0.408 / 0.405   | 0.400 / 0.399  | **0.395 / 0.392**  |
| **ETTh1**      | 0.493 / 0.483   | 0.490 / 0.476  | **0.470 / 0.474**  |
| **ETTh2**      | 0.423 / 0.442   | 0.431 / 0.446  | **0.417 / 0.436**  |
| **ECL**        | 0.215 / 0.304   | 0.235 / 0.316  | **0.198 / 0.290**  |
| **Traffic**    | 0.461 / 0.300   | 0.488 / 0.301  | **0.446 / 0.287**  |
| **Weather**    | 0.356 / 0.348   | 0.353 / 0.347  | **0.344 / 0.343**  |
| **Solar_Energy** | 0.247 / 0.274 | 0.259 / 0.282  | **0.242 / 0.271**  |

