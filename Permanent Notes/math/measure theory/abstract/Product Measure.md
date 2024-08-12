---
tags:
  - measure
---
For two measurable spaces $(\Omega_1,\mathcal{F}_1)$ and $(\Omega_2,\mathcal{F}_2)$, we the product space $(\Omega,\mathcal{F})$ consists of $\Omega=\Omega_1\times\Omega_2$ and $\mathcal{F}=\mathcal{F}_1\times\mathcal{F}_2$ where the product refers to the [[σ-algebra product]].

We can equivalently write $\mathcal{F}$ as
$$\mathcal{F}=\sigma\left(\left\{\biguplus\limits_{j=1}^\infty A_j\times B_j:A_j\in\mathcal{F}_1,B_j\in\mathcal{F}_2\right\}\right)=\sigma(\mathcal{A})$$
# Construction of Product Measure

Given two [[Sigma-Finite Measure|sigma-finite measures]] $\mu_i$ on $(\Omega_i,\mathcal{F}_i)$, $i=1,2$, there exists a unique $\sigma$-finite measure $\mu$ on the product space $(\Omega,\mathcal{F})$ such that
$$\mu\left(\biguplus\limits_{j=1}^\infty A_j\times B_j\right)=\sum\limits_{j=1}^\infty \mu_1(A_j)\mu_2(B_j),\quad\forall A_j\in\mathcal{F_1},B_j\in\mathcal{F}_2, m<\infty$$

Denote it as $\mu=\mu_1\times\mu_2$.

>[!Hint]-
>We need to use [[Caratheodory's Extension Theorem]] here.

>[!Proof]
>Something here.