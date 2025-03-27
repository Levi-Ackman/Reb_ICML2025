# Complexity Analysis of ReFocus

Given an input of shape $X$ [N, D]. (N is the number of tokens, and D is the model dimension).

## The complexity of ReFocus Encoder:

**MLP1**
$O(N \cdot D^2)+O(N \cdot D \cdot Q)$.
Since $Q \ll D$ ($Q=128$, and $D=512$ in this work), the dominant cost is $O(N \cdot D^2)$.

**Energy-based Frequency Picking**
The complexity of FFT is $O(N \cdot Q \cdot \log Q)$, and so is the IFFT. Complexity of Energy computing, Softmax and Component Picking, each part is $O(N \cdot Q)$. 
Map the representation back to the original space: $O (N \cdot D \cdot Q)$.

So the overall complexity is $O(N \cdot D \cdot Q)$, which is negligible compared to $O(N \cdot D^2)$.

**FFN Fusion**
Each with $O(N \cdot D^2)$

So, the overall complexity is dominated by $O(N \cdot D^2)$, which is Linear to input token number $N$.

***A standard Transformer encoder has self-attention with complexity:***

$O(N^2 \cdot D)+O(N \cdot D^2)$ (Self-Attention + FFN).

For large $N$, the Quadradic $O(N^2)$ term becomes the bottleneck, whereas our **ReFocus** Block avoids this quadratic cost.
