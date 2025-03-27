### ReFocus effectively captures key frequency components shared across channels.

To support this claim, we visualize the average spectral energy across all channels for both the ground truth samples $Y$ and the predictions by ReFocus $\hat{Y}$.

We chose the *input-96-forecast-720* on ECL and Traffic.

The following results demonstrate that the channel-wise average spectral distributions of $Y$ and $\hat{Y}$ are nearly identical. The computed cosine similarity reaches as high as **99.92%** (Traffic) and **99.89%** (ECL), indicating a striking alignment in their frequency characteristics.

<img src="Figs/core_freq.jpg" alt="efficiency" width=100%>

### By assigning the task of capturing inter-series dependencies to ReFocus, the learned embeddings gain improved interpretability

To validate this, we provide **Analysis of multivariate correlations on ECL and Traffic**. 

We chose the *input-96-forecast-720* on ECL and Traffic.

Below is the visualization of multivariate correlations:

![公式](https://latex.codecogs.com/svg.latex?\dpi{300}\begin{aligned}\bar{x}_{i,:}&=\frac{1}{T}\sum_{t=1}^{T}x_{i,t},\quad\tilde{x}_{i,t}=x_{i,t}-\bar{x}_{i,:},\tilde{\rho}_{ij}&=\frac{\sum_{t=1}^{T}\tilde{x}_{i,t}\,\tilde{x}_{j,t}}{\sqrt{\sum_{t=1}^{T}\tilde{x}_{i,t}^{2}}\,\sqrt{\sum_{t=1}^{T}\tilde{x}_{j,t}^{2}}+\epsilon},\quad\epsilon=1\times10^{-8},\mathrm{cor}_{ij}&=\frac{\exp\left(\tilde{\rho}_{ij}\right)}{\sum_{k=1}^{N}\exp\left(\tilde{\rho}_{ik}\right)}.\end{aligned})

of raw time series and the learned representation by Refocus Encoder. 

$X$ is the raw input, and $Y$ is the target. $O_1$ is the output representation of the first block, and $O_S$ is the last block. 

We use the Frobenius norm:

![Frobenius Norm](https://latex.codecogs.com/svg.latex?\dpi{200}\|A-B\|_F=\sqrt{\sum_{i,j}(A_{ij}-B_{ij})^2}) 

to quantify the similarity between maps. **A lower value indicates a higher similarity**. 

As shown in Figure below, the early encoder layer produces correlation maps similar to the input series $X$. 
In deeper layers, these maps gradually resemble the correlation patterns of the target series $Y$, 
suggesting that ReFocus effectively models inter-series dependencies in a hierarchical and progressive manner.

<img src="Figs/cor_map.jpg" alt="efficiency" width=100%>
