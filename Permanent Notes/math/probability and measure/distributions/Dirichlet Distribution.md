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

