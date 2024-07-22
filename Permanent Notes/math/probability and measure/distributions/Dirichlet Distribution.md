---
tags:
  - distribution
---
A distribution over $K$-component distributions. 

Let $K\geq 2$. 

| Support | $x_1,\ldots x_k$ where $x_i\in[0,1]$ and $\sum x_i = 1$                  |
| ------- | ------------------------------------------------------------------------ |
| PDF     | $$\frac{1}{B(\boldsymbol{\alpha})}\prod\limits_{i=1}^Kx_i^{\alpha_i-1}$$ |
| Mean    | $$\mathbb{E}\left[X_i\right]=\frac{\alpha_i}{\alpha_0}$$                 |
>[!info] 
>Finding the expectation is easy. WLOG, modify $x_1$'s exponent from $\alpha_1-1$ to $\alpha_1$.


The Dirichlet distribution is the **conjugate prior** for the multinomial distribution. This makes sense since the multinomial distribution requires that we specify a *distribution over labels*. 

>[!proof]
>Let $p_1,\ldots,p_k\sim Dir(\alpha_1,\ldots, \alpha_k)$ and $n_1,\ldots, n_k|p_1,\ldots,p_k\sim Mult(p_1,\ldots,p_k)$. Then 
>$$P(p_1,\ldots, p_k|n_1,\ldots, n_k)\propto \frac{\prod\limits_{k=1}^K p_k^{n_k+\alpha_k-1}}{\int \prod\limits_{k=1}^K p_k^{n_k+\alpha_k-1}\;\mathrm{d}p_1\ldots \mathrm{d}p_K}$$
>
>The integral is the normalization constant of the distribution $Dir(n_1+\alpha_1,\ldots,n_k+\alpha_k)$. Indeed, the numerator is the unnormalized distribution. 
>
>We can summarize the results as follows. Given observations $n_1, \ldots, n_k$, we update $(\alpha_1,\ldots,\alpha_k)\rightarrow(\alpha_1+n_1,\ldots,\alpha_k+n_k)$. 



