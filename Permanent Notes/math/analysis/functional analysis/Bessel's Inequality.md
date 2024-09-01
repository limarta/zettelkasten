---
tags:
  - functional_analysis
  - hilbert_space
---
Let $H$ be a [[Pre-Hilbert Space]] and $\{e_i\}_i$ be an orthonormal sequence. Then
$$\sum\limits_{i} \langle u, e_i\rangle^2\leq ||u||^2$$
>[!Tip]- Interpretation
>This inequality states that the hypotenuse $||u||$ is always at least as large as the norm of the projection of $u$ onto the span of $e_i$. 
>

>[!Proof]
>Let $v=\sum\limits_{i=1}^N \langle u, e_i\rangle e_i$. The key insight is to show that the length of $v$ is at most the length of $u$. To show this, note $\langle u-v, v\rangle=\sum_i^N \langle u,e_i\rangle^2 - \sum_i^N\langle u, e_i\rangle^2=0$. Shifting terms and applying Cauchy-Schwartz, we see $\begin{align*}||v||^2=\langle u, v\rangle\leq ||u||\cdot||v||\end{align*}$ or $||v||\leq ||u||$.

