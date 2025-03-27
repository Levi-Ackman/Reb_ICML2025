### Forecasting Benchmark Beyond Sensor Time Series

We chose two datasets:

**Exchange** features daily exchange rates for eight countries from 1990 to 2016. 

**illness** comprises weekly records of influenza-like illness (ILI) patient counts from the Centers for Disease Control and Prevention in the United States from 2002 to 2021.


Our ReFocus achieves improvements of **3.61%** (Exchange) and **8.68%** (illness) over the second-best baseline, respectively.

|Dataset | Length | ReFocus| FilterNet | iTransformer| PatchTST| TimesNet|
|--------|--------|-------------------|---------------------|------------------------|--------------------|--------------------|
|||MSE/MAE|MSE/MAE|MSE/MAE|MSE/MAE|MSE/MAE|
|Exchange| 96-96     | **0.083/0.201**       | 0.091/0.211         | 0.086/0.206            | 0.088/0.205        | 0.107/0.234        |
|| 96-192    | **0.174/0.297**       | 0.186/0.305         | 0.177/0.299            | 0.176/0.299        | 0.226/0.344        |
|| 96-336    | 0.318/0.410       | 0.380/0.449         | 0.331/0.417            | **0.301/0.397**        | 0.367/0.448        |
|| 96-720    | **0.813/0.686**       | 0.896/0.712         | 0.847/0.691            | 0.901/0.714        | 0.964/0.746        |
|| Avg    | **0.347/0.399**       | 0.388/0.419         | 0.360/0.403            | 0.367/0.404        | 0.400/0.406        |
|illness | 36-24     | **1.813/0.844**       | 2.347/0.921         | 2.004/0.860            | 2.046/0.849        | 2.317/0.934        |
| | 36-36    | **1.795/0.871**       | 2.012/0.904         | 1.910/0.880            | 2.344/0.912        | 1.972/0.920        |
| | 36-48    | **1.788/0.861**       | 2.113/0.926         | 2.036/0.891            | 2.123/0.883        | 2.238/0.940        |
| | 36-60    | **1.882/0.891**       | 2.162/0.942         | 2.022/0.919            | 2.001/0.895        | 2.027/0.928        |
| | Avg    | **1.820/0.867**       | 2.159/0.923         | 1.993/0.888            | 2.129/0.885        | 2.139/0.931        |
