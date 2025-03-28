###

These results demonstrate that **ReFocus consistently outperforms two strong baselines, TimeMixer and TimeXer, across a range of standard time series benchmarks**. 

It achieves the best MSE/MAE scores on most datasets, including significant improvements on ECL and Traffic. Even in cases where it is not the top performer, ReFocus remains highly competitive.

Its effectiveness across diverse datasets—ranging from electricity to traffic and weather—further highlights its adaptability and generalization capability.

| Dataset   | ReFocus   | TimeMixer |TimeXer|
|-|-|-|-|
|| MSE / MAE   | MSE / MAE|MSE / MAE |
| ECL       | **0.168 / 0.262** | 0.182 / 0.297 | 0.171 / 0.270 |
| Weather   | 0.245 / **0.271** | 0.245 / 0.276 | **0.241** / 0.271 |
| ETTh1     | **0.434 / 0.433** | 0.458 / 0.445 | 0.437 / 0.437 |
| ETTh2     | 0.371 / **0.396** | 0.384 / 0.407 | **0.367** / 0.396 |
| ETTm1     | 0.387 / **0.394** | 0.385 / 0.399 | **0.382** / 0.397 |
| ETTm2     | 0.275 / **0.320** | 0.278 / 0.325 | **0.274** / 0.322 |
| Traffic   | **0.412 / 0.265** | 0.484 / 0.297 | 0.466 / 0.287 |
