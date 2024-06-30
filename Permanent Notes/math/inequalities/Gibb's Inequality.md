---
tags:
  - inequalities
---
Gibb's inequality is a statement on cross-entropy and subsequently KL divergence. 

Desirables:
- $D(p||q)\geq 0$
- For $X\sim p(x)$, the cross entropy $C(p,q)$ is $minimized$ when $p=q$.

Theorem 1 ([[Gibb's Inequality]])
For distributions $p(x)$ and $q(x)$, the following holds:
$$E_p\left[\log q(x)\right]\leq E_p\left[\log p(x)\right]$$
> [!hint] 
We would like to get $\int p(x)\cdot\frac{q(x)}{p(x)}dx=\int q(x)dx =1$. Shape the term in the expectation to achieve this.

> [!note]- Proof
> By [[Jensen's inequality]], $E_p\left[\log q(x)/p(x)\right]\leq \log E_p\left[q(x)/p(x)\right]=\log 1 =0$. Rearranging the terms yields Gibb's inequality.

Negative the inequality gives the statement on entropy:
$$H(p)\leq C(p,q)$$
