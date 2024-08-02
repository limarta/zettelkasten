---
tags:
  - probability
---
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