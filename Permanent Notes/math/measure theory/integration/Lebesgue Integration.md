---
tags:
  - integration
  - measure
---
**Notation** (Special Cases)
(b) For $(\mathbb{R}^d, \mathcal{R}^d, \lambda)$, we write $\int f(x);\mathrm{d}x$ for $\int f\;\mathrm{d}\lambda$.
(c) For $(\mathbb{R}, \mathcal{R}, \mu)$ with $\mu((a,b])=G(b)-G(a)$ for $a<b$, we write $\int f(x)dG(x)$ for $\int f\;\mathrm{d}\mu$.
(d) When $\Omega$ is countable, $\mathcal{F}=Pow(\Omega)$, and $\mu$ is the counting measure, we write $\sum_{i\in\Omega} f(i)$.
(e) There are four (confusingly) common ways of writing integrals with respect to a measure $\mu$.
	$$\int f\;\mathrm{d}\mu=\int f(x)\;\mu(\mathrm{d}x)=\int f(x)\;\mathrm{d}\mu(x)$$
	- The notation is roughly corresponds to weight an infinitesimal with $\mu$ and computing $\sum_i f(\xi_i)\mu((x_{i+1},x_i])$.
	- This notation is convenient for a [[Change of Variables (Integration)|change of variables]].

## The Integration Machine
The standard pipeline consists of four steps.
- Indicators
- Simple Functions
- Bounded Functions on support of finite measure
- General Functions