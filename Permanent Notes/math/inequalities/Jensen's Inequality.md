---
tags:
  - inequalities
---
### Convexity
Jensen's inequality can be viewed as a generalization of [[Convex Functions|convexity]] (or concavity). Recall that if $f$ is a convex function, then $f(\lambda x + (1-\lambda) y)\leq \lambda f(x) + (1-\lambda) f(y)$. 

>[!note] Jensen's Inequality (Discrete)
>Let $\sum \omega_i=1$. Then if $f$ is convex,
>$$f(\omega_1x_1+\ldots \omega_n x_n)\leq \omega_1 f(x_1)+\ldots + \omega_n f(x_n) $$

Observation 1
- Equality holds only when $f$ is a constant function. 

### Measure-theoretic description
We can generalize to a general measure on $\mathbb{R}^n$.

>[!note] Jensen's Inequality (General)
>Suppose $f$ is a convex function defined on $V\subset \mathbb{R}^n$, and let $\mu$ be a probability measure over $V$. Then
>$$f\left(\int x \;\mathrm{d}\mu\right)\leq \int f(x)\;\mathrm{d}\mu$$

>[!note] Proof
>If $f$ is convex, then for each point $x\in V$ there exists a linear function $g(z)=a+bz$ such that $g(z)\leq f(z)$ and $g(x)=a+bx=f(x)$. In particular consider $x=\int x\;\mathrm{d}\mu$. 