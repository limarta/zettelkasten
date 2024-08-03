---
tags:
  - integration
---
In general we cannot say 
$$\lim\limits_{n\rightarrow\infty}\int f_n=\int\lim\limits_{n\rightarrow\infty}f_n$$
where the limit on the right hand side denotes a pointwise limit. Even if  $f_n\geq 0$, we still cannot assert this without additional conditions (e.g. [[Monotone Convergence Theorem]]). 

Fatou's lemma gives an upper bound on the function $\liminf\limits_{n}f_n$ for *nonnegative* $f_n$.

**Fatou's Lemma**
If $f_n\geq 0$ then
$$\int(\liminf\limits_{n\rightarrow\infty}f_n)\;\mathrm{d}\mu\leq \liminf\limits_{n\rightarrow\infty}\int f_n\;\mathrm{d}\mu$$


>[!tip] Helpful Example
>A sequence $f_1,f_2,f_1,f_2,\ldots$ as shown below has integrals show in red and blue. The infinum's integral shown in green is less than either area.
>
>![[fatou.svg]]

>[!Proof]-
>The key is to use the picture above except, rather than use minimums, we must use the infinum. Define $g_N(x) = \inf\limits_{n\geq N}f_n(x)$. Note $g_1(x)\leq g_2(x)\leq\ldots$ and and converges pointwise to $\liminf\limits_{n\rightarrow\infty} f_n(x)$. By the [[Monotone Convergence Theorem]], 
>$$\int\liminf\limits_{n\rightarrow\infty} f_n(x)\;\mathrm{d}\mu=\lim\limits_{n\rightarrow\infty}\int g_n(x)\;\mathrm{d}\mu$$
>Since $g_n(x)\leq f_k(x)$ for $k\geq n$, monotonicity implies $\int g_n\;\mathrm{d}\mu\leq \int f_k\;\mathrm{d}\mu$. Taking the limit infinum on both sides and noting that the left hand side is monotonic implies
>$$\int\liminf\limits_{n\rightarrow\infty}f_n\;\mathrm{d}\mu\leq \liminf\int g_n\;\mathrm{d}\mu\leq \liminf\limits_{n\rightarrow\infty} \int f_n\;\mathrm{d}\mu$$
