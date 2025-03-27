***By assigning the task of capturing inter-series dependencies to ReFocus, the learned embeddings gain improved interpretability.***

As shown in Figure below, the early encoder layer produces correlation maps similar to the input series $X$. 
In deeper layers, these maps gradually resemble the correlation patterns of the target series $Y$, 
suggesting that ReFocus effectively models inter-series dependencies in a hierarchical and progressive manner.

<img src="Figs/cor_map.jpg" alt="efficiency" width=100%>
