---
tags:
  - integration
---
Suppose $X$ is a random variable. If we wish to compute a transformation $h(X)$'s expected value, we use the formula $\mathbb{E}h(X)=\int h(X)\;\mathrm{d}P$ over the sample space $\Omega$ with measure $P$.  

This is cumbersome because rather than using the law of $X$, we must use the implicit probability space. 

## Change of Variables

Let $X:\Omega\rightarrow\mathbb{R}$ be a random variable on $(\Omega, \mathcal{F}, P)$ and $h$ a Borel measurable function such that $Eh^+(X)<\infty$ or $Eh^-(X)<\infty$. Then,
$$\int h(X(\omega))\;\mathrm{d}P(\omega)=\int h(x)\;\mathrm{d}\mathcal{L}_X$$
where $\mathcal{L}_X$ is the law of $X$.

>[!Note]
>The left hand side is an integral over $\omega$ whereas the right hand side is an integral over the target space of $X$ - $\mathbb{R}^d$.

>[!Proof]
>We apply the standard integration machine. 
>
>*Step 1*: Indicator functions.
>Let $h=I_A$. Then
>$$\int {\bf{1}}_{X(\omega)\in A}\;\mathrm{d}P(\omega)=P(\{X(\omega)\in A\})=\mathcal{L}_X(A)=\int{\bf{1}}_A\;\mathrm{d}\mathcal{L}_X(x)$$
>
>*Step 2*: Simple functions.
>Let $h=\sum\limits_{n=1}^N c_n I_{A_n}$. Then
>$$
>\begin{align*}\int \sum\limits_{n=1}^N c_nI_{X(\omega)\in A_n}\;\mathrm{d}P(\omega)&=\sum\limits_{n=1}^N c_n\int I_{X(\omega)\in A_n}\;\mathrm{d}P(\omega)\\
>&=\sum\limits_{n=1}^Nc_n\int I_{A_n}\;\mathrm{d}\mathcal{L}_X(x)\\
>&=\int h(x)\;\mathrm{d}\mathcal{L}_X(x)
>\end{align*}$$
>
>*Step 3*: Non-negative measurable functions.
>Let $h\in m\mathcal{B}^+$. Select a sequence $h_n$ such that $h_n(X(\omega))\uparrow h(X(\omega))$. Then Monotone Convergence implies
>$$
>\begin{align*}\int_{\Omega} h(X(\omega))\;\mathrm{d}P(\omega)&=\lim\limits_{n\rightarrow}\int_{\Omega}h_n(X(\omega))\;\mathrm{d}P(\omega)\\
>&=\lim\limits_{n\rightarrow\infty}\int h_n(x)\;\mathrm{d}\mathcal{L}_X(x)\\&=\int h(x)\;\mathrm{d}\mathcal{L}_X(x)\end{align*}$$ 


