## By assigning the task of capturing inter-series dependencies to ReFocus, the learned embeddings gain improved interpretability

To validate this, we provide **Analysis of multivariate correlations on ECL and Traffic**. 

Below is the visualization of multivariate correlations of raw time series and the learned representation by Refocus Encoder. 

$X$ is the raw input, and $Y$ is the target. $O_1$ is the output representation of the first block, and $O_S$ is the last block. 

We use the Frobenius norm ![Frobenius Norm](https://latex.codecogs.com/png.latex?\|A-B\|_F=\sqrt{\sum_{i,j}(A_{ij}-B_{ij})^2})
 to quantify the similarity between maps. **A lower value indicates a higher similarity**. 

As shown in Figure below, the early encoder layer produces correlation maps similar to the input series $X$. 
In deeper layers, these maps gradually resemble the correlation patterns of the target series $Y$, 
suggesting that ReFocus effectively models inter-series dependencies in a hierarchical and progressive manner.

<img src="Figs/cor_map.jpg" alt="efficiency" width=100%>
