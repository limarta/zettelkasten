---
tags:
  - measure
---
Let $\Omega$ be a topological space equipped with a topology $\mathcal{T}$. Then the **Borel σ-algebra** is $\sigma(\mathcal{T})$ and is denoted by $\mathcal{B}_\Omega$.

The most important example is "the" Borel $\sigma$-algebra $\mathcal{B}_\mathbb{R}$.

There are several descriptions of $\mathcal{B}_\mathbb{R}$ and more broadly $\mathcal{B}_{\mathbb{R}^d}$.

>[!Example] Equivalent generators of $\mathcal{B}_{\mathbb{R}}$
>$\begin{align*}
>\sigma(\{O\subset\mathbb{R}\;\text{open}\})&=\sigma(\{[a,b]:a<b\in\mathbb{R}\})\\&=\sigma(\{(-\infty,b]:b\in\mathbb{R}\})\\
>&=\sigma(\{(a,b):a<b\in\mathbb{R}\})\\
>&=\sigma(\{(a,b):a<b\in\mathbb{Q}\})
>\end{align*}$

>[!Example]
>$$\mathcal{B}_{\mathbb{R}^d}=\mathcal{B}\times\ldots\times\mathcal{B}=\sigma(\{(a_1,b_1)\times\ldots\times(a_d,b_d):a_i<b_i\in\mathbb{R}, i=1,\ldots, d\}$$
>
>The middle term denotes a [[σ-algebra product]]. Let $\mathcal{A}=\{(a_1,b_1)\times\ldots\times(a_d,b_d):a_i<b_i\}$.
>
>First we show $\mathcal{B}_{\mathbb{R}^d}=\sigma(A)$. Since $\mathbb{R}$ is second countable, we can express any open set $U\subset\mathbb{R}^d$ as a countable collection of cubes (e.g. cubes of rational side lengths and at rational centers). Since these cubes lie in $\mathcal{A}$, the countable union must lie in $\sigma(\mathcal{A})$. In other words, $\mathcal{B}_{\mathbb{R}^d}\subset\sigma(\mathcal{A})$. On the other hand, each element $(a_1,b_1)\times\ldots\times(a_d,b_d)$ is an open set and so must belong in $\mathcal{B}_{\mathbb{R}^d}$. This yields the reverse inclusion $\sigma(\mathcal{A})\subset\mathcal{B}_{\mathbb{R}^d}$.
>
>Now we show the second equality. Using a similar observation as above, any open cube $(a_1,b_1)\times\ldots\times(a_d,b_d)$ must belong in $\mathcal{B}\times\ldots\times\mathcal{B}$ (when viewed as a Catesian product), so $\sigma(\mathcal{A})\subset\mathcal{B}\times\ldots\times\mathcal{B}$. Conversely, if $F_1\times\ldots\times F_d$ is an element of $\mathcal{B}\times\ldots\times\mathcal{B}$, then note $F_1\times\Omega\times\ldots\Omega$ is an element of $\sigma(A)$. The intersection of similar products implies $F_1\times\ldots\times F_d$ belongs in $\sigma(\mathcal{A})$.