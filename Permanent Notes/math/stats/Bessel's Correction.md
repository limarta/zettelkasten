---
tags:
  - statistics
  - estimators
---
It is known that $s^2=\frac{1}{n-1}\sum\limits_{i=1}^n (x_i-\bar{x})^2$ is an unbiased estimator for the variance of R.V. $X$. But what is the intuition?

Consider the residual vector $(x_1-\bar{x}, \ldots, x_n-\bar{x})$. There are $n$ independent observations $x_i$, but only $n-1$ independent residuals.

#### Caveats
1. Bessel's correction does not give an unbiased estimate for the standard *deviation*.
2. The corrected estimator often yields a higher mean squared error than the uncorrected estimator.
3. It is necessary when the population mean is *unknown* and when one is estimating *both* population *mean* and population *variance*, using the *sample* mean to estimate the population mean.
>[!note] 
>The need for a larger correction factor ($\frac{1}{n-1}>\frac{1}{n}$) can intuited from the following: if we knew the true population mean $\mu$, then the squared error is $(x_i-\mu)^2$. We can decouple the true mean by using the sample mean:
>$$(x_i-\mu)^2=(x_i-\bar x)^2+2(x_i-\bar x)(\bar x - \mu)+(\bar x-\mu)^2$$
>Summing over all $x-i$ cancels the term in the middle, so we are left with the sum of the *square residuals* and the square error of our estimate of the average. The $\frac{1}{n-1}$ tries to correct for the second term.

>[!hint]- Proof
>$$
>\begin{align*}
>\mathbb{E}\left[\sum\limits_{i=1}^N(x_i-\bar{x})^2\right]&=\mathbb{E}\left[\sum\limits_{i=1}^N(x_i-\mu)^2+\sum\limits_{i=1}^N(\mu-\bar{x})^2+2\sum\limits_{i=1}^N(x_i-\mu)(\mu-\bar{x})\right]\\
>&=N\text{Var}(x)+N\text{Var}(\bar x)+2\mathbb{E}\left[(\mu-\bar{x})\sum\limits_{i=1}^N(x_i-\mu)\right]\\
>&=N\text{Var}(x)+N\text{Var}(\bar x)+2N\mathbb{E}\left[(\mu-\bar{x})(\bar{x}-\mu)\right]\\
>&=N\text{Var}(x)+\text{Var}(x)-2\text{Var}(x)\\
>&=(N-1)\text{Var}(x)
>\end{align*}$$
