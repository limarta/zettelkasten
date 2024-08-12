---
tags:
  - probability
---
# Expectation

Integration specialized to a probability measure $P$.
Let $X\geq 0$ be a random variable on $(\Omega, \mathcal{F}, P)$. Then the **expectation** of $X$ is 
$$EX = \int X\;\mathrm{d}P=\int X(\omega)\; P(\mathrm{d}\omega)$$

Generally, let $X$ be a random variable on $(\Omega, \mathcal{F}, \mathcal{P})$ not necessarily nonnegative. Then the **expectation** of $X$ is
$$EX=EX^+-EX^-$$
when either $EX^+$ or $EX^-$ are finite. 

To compute expectations, one often does a [[Change of Variables (Integration)|change of variables]].

There are several important inequalities related to the expectation.
- [[Jensen's Inequality]]
- Holder's Inequality
- Chebyshev's Inequality
- Markov's Inequality

# Density Functions

Suppose we can express the distribution function of a random variable $X$ as
$$F_X(\alpha)=\int\limits_{-\infty}^\alpha f(x)\;\mathrm{d}x$$
Then using a [[Change of Variables (Integration)|change of variables]], we can calculate the expectation using the *law of X* rather than the underlying probability space $P$. In particular
$$\int X\;\mathrm{d}P=\int xf(x)\;\mathrm{d}x$$

More generally if $h\in m\mathcal{F}$, then 
$$\mathbb{E}h(X)=\int X\;\mathrm{d}P=\int h(x)f(x)\;\mathrm{d}x$$
>[!Proof]
>We utilize a [[Induced Measure|fact of induced measures]] and a [[Change of Variables (Integration)|change of variables]]. By the change of variables formula $\mathbb{E}h(X)=\int h(x)\;\mathrm{d}\mathcal{L}_x$. But recall $\mathcal{L}_x$ is equal to the induced measure $f\lambda$ where $\lambda$ is the Lebesgue measure. The integral can be expressed as $(f\lambda)(h)$, which by compositionality, is equal to $\lambda(fh)$. 
