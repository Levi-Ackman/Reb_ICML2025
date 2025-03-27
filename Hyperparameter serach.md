Additional comparison with **iTransformer** and **PatchTST** under **Hyperparameter Search**. 

We chose the ***input-96-forecast-720*** task.

Including learning_rate $lr \in [1e−5, 1e−4, 1e-3\]$, batch size $bs \in [32, 64, 128\]$, Number od Encoder $N \in [1,2,3,4\]$, 
and Dimension of Model $D \in [128, 256, 512\]$. 

*We set the training epochs to 100 (to balance the extra epochs trained under the `Key Frequency Enhanced Training Strategy').*

<span style="font-size:12px;">
|Models\Metric|ETTm1 (MSE)|ETTm1 (MAE)|ETTm2 (MSE)|ETTm2 (MAE)|ETTh1 (MSE)|ETTh1 (MAE)|ETTh2 (MSE)|ETTh2 (MAE)|ECL (MSE)|ECL (MAE)|Traffic (MSE)|Traffic (MAE)|Weather (MSE)|Weather (MAE)|Solar_Energy (MSE)|Solar_Energy (MAE)|
|-------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|---------|---------|-------------|-------------|-------------|-------------|------------------|------------------|
|iTransformer|0.486|0.455|0.408|0.405|0.493|0.483|0.423|0.442|0.215|0.304|0.461|0.300|0.356|0.348|0.247|0.274|
|PatchTST|0.454|0.439|0.400|0.399|0.490|0.476|0.431|0.446|0.235|0.316|0.488|0.301|0.353|0.347|0.259|0.282|
|ReFocus|0.463|0.437|0.395|0.392|0.470|0.474|0.417|0.436|0.198|0.290|0.446|0.287|0.344|0.343|0.242|0.271|
</span>
