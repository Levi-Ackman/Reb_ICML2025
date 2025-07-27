### Compare with Extensive Baseline
In response to the suggestions from Reviewer Xhc1 & XwNW, we have additionally included comparative experiments against two recent strong baselines: **TimeXer** and **TimeMixer**. To conserve space, we report the average performance across four forecasting horizons [96, 192, 336, and 720].

These results demonstrate that **ReFocus consistently outperforms two strong baselines, TimeMixer and TimeXer, across a range of standard time series benchmarks**. 

It achieves the best MSE/MAE scores on most datasets, including significant improvements on ECL and Traffic. Even in cases where it is not the top performer, ReFocus remains highly competitive.

Its effectiveness across diverse datasets—ranging from electricity to traffic and weather—further highlights its adaptability and generalization capability.

| Dataset   | ReFocus   | TimeMixer|TimeKAN|Time-LLM|GPT4TS|
|-|-|-|-|-|-|
|| MSE / MAE   | MSE / MAE|MSE / MAE |MSE / MAE |MSE / MAE |
| ECL       | **0.168 / 0.262** | 0.183 / 0.272 | 0.236 / 0.320 |0.195/0.288|0.205/0.290|
| Weather   | **0.245** / **0.271** | 0.245 / 0.274 | 0.246 / 0.274 |0.275/0.291|0.264/0.284|
| ETTh1     | **0.434 / 0.433** | 0.470 / 0.451 |  0.440 / 0.437 |0.448/0.443|0.447/0.436|
| ETTh2     | **0.371** / **0.396** | 0.389 / 0.409 | 0.388 / 0.412 |0.381/0.404|0.381/0.408|
| ETTm1     | 0.387 / **0.394** | 0.384 / 0.397 | **0.382** / 0.397 |0.410/0.409|0.389/0.397|
| ETTm2     | **0.275** / **0.320** | 0.279 / 0.325 | 0.281 / 0.325 |0.296/0.340|0.285/0.331|
| Traffic   | **0.412 / 0.265** | 0.496 / 0.298 | 0.505 / 0.302 |0.541/0.358|0.488/0.317|
