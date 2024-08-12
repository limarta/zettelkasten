---
tags:
  - probability
---
# P-Trivial

A $\sigma$-algebra $\mathcal{H}\subset\mathcal{F}$ is $\boldsymbol{\mu}$**-trivial** if for $\mu:\mathcal{F}\rightarrow[0,+\infty]$, $\mu(H)$ or $\mu(H^c)$ is 0 for all $H\in\mathcal{H}$.

>[!Example]
>If $\mu=P$, then $\mathcal{H}$ is P-trivial if $P(H)\in \{0,1\}$.

A random variable $X$ is **P-trivial** or **P-degenerate** if there exists a non-random constant $c$ such that $P(X\neq c)=0$. This means that $X$ is essentially constant.

>[!Example]
>$X(\omega)=0$ is P-trivial.

**Fact**
If $X\in m\mathcal{H}$ for a P-trivial $\sigma$-algebra $\mathcal{H}$, then $X$ is P-trivial.

>[!Proof]
>The the sets $H_c=X^{-1}((-\infty,c])$ must belong in $\mathcal{H}$ and have measure equal to $F_X(c)=\mu(H_c)$ (verify that this indeed produces a distribution!). These values must be either $0$ or $1$, so the distribution function must take the form ${\bf{1}}_{x\geq c}$ for some $c$. Thus $P(X\neq c)=0$.


# Independence and P-Triviality

Observe that a P-trivial $\sigma$-algebra is independent of any other $\sigma$-algebra. We can state a converse.

**Fact**
If each $\sigma$-algebra $\mathcal{G}_k\subset\mathcal{G}_{k+1}$ is P-independent of a $\sigma$-algebra $\mathcal{H}\in\sigma\left(\bigcup_k \mathcal{G}_k\right)$, then $\mathcal{H}$ is P-trivial.

>[!Proof]
>The union $\bigcup_k \mathcal{G}_k$ is a $\pi
$-system which is independent of $\mathcal{H}$.  Thus by [[Mutual Independence (Measure)|a proposition on π-systems]] , $\mathcal{H}$ and $\sigma\left(\bigcup_k\mathcal{G}_k\right)$ are independent. Therefore $H\in\mathcal{H}$ is independent of itself and must satisfy
$$P(H)=P(H)P(H)$$
which implies $P(H)=0$ or $P(H)=1$.


>[!Note]
>The simplest case is when $\mathcal{H}\subset\mathcal{G}$, but this is not the only case covered by the proposition.

The previous fact helps prove [[Kolmogorov's 0-1 Law]].