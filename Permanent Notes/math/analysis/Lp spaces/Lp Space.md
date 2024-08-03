---
tags:
  - analysis
  - measure
---
Given a measurable space $\mathcal(\Omega, \mathcal{F}, \mu)$, a function $f$ is in $L^p(\Omega, \mathcal{F}, \mu)$ if 
$$\int |f|^p\;\mathrm{d}\mu <\infty$$
It turns out the following expression defines a norm on the $L^p$ space.
$$||f||_p=\left(\int |f|^p\right)^{1/p}\;\mathrm{d}\mu$$ 
## Examples

**Example 1**

The most important $L^p$ are those defined over $\mathbb{R}^n$, namely $L^p(\mathbb{R}, \mathcal{B}_\mathbb{R})$ or $L^p(\mathbb{R}^d, \bar{\mathcal{B}_\mathbb{R}})$ attached with the Lebesgue measure. We often denote the space with Borel $\sigma$-algebra as $L^p(\mathbb{R}^d)=L^p$ when the context is clear. 

Among these spaces, $p=1$ and $p=2$ are the most important.



### Confusion: Is "Lp in Lq" or "Lq in Lp"

Time and time again, I get confused about this but it turns out it may not exactly be my fault? It turns out it depends on the characteristics of the measure. For example, in a probability space $(\Omega, \mathcal{F}, P)$, Jensen's inequality implies (link) the lemma
$$p\leq q\implies ||X||_p\leq ||X||_q\implies L^q\subset L^p$$
or that $\left[\mathbb{E}|X|^p\right]^{1/p}$ is a non-decreasing function of $p$. 

Now let's consider functions $f:\mathbb{N}\rightarrow[0,+\infty]$ which are over $\mathbb{N}$ with a [[Counting Measure|counting measure]]. From this fact (link needed), we have
$$p\leq q\implies ||x||_q\leq ||x||_p\implies \ell^p\subset\ell^q$$

We can see why by analyzing two cases. 

#### Finite Measures

If $\mu(\Omega)=1$, then $\mu$ is a finite measure. The most important example is a probability measure $P$. If $0<p<q$, then by Holder's inequality

$$\begin{align*}
\int 1\cdot|f|^p\;\mathrm{d}\mu&\leq \left(\int 1^{\frac{q}{q-p}}\;\mathrm{d}\mu\right)^\frac{q-p}{q}\left(\int\left(|f|^p\right)^{q/p}\right)^{p/q}\\
&=\mu(\Omega)^\frac{q-p}{q}||f||_q^p
\end{align*}$$
or
$$||f||^p\leq\mu(\Omega)^\frac{q-p}{pq}||f||_q$$
We have the inclusion $L^q(\Omega,\mu)\hookrightarrow L^p(\Omega, \mu)$. When $\mu(\Omega)=1$ (e.g. in a probability space), then we get [[Lyapunov's Inequality]]. 

#### Measures with atoms

The space $\ell^p$ is a set of atoms over $\mathbb{N}$ whose measures are all equal to $1$. Generally the reverse inequality holds when the atoms have a positive lower bound. With a weight function $w(t)\geq \epsilon>0$ for $t\in T$, define the "weighted" counting measure as
$$\nu(A)=\sum\limits_{t\in A} w(t)$$

The for a function $f(t)$ and two numbers $0<p<q$, the Holder inequality yields
$$\sum\limits_{t\in A} |f(t)|^q w(t) $$