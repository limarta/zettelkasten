---
tags:
  - convergence
  - probability
---
Let $\Omega_0=\{\omega\in\Omega:\liminf\limits_{n\rightarrow\infty} X_n(\omega)=\limsup\limits_{n\rightarrow\infty} X_n(\omega)\}$ which is the set of points where the random variable converges. Note that $\Omega_0$ is a measurable set (do you see?).

**Almost-sure Convergence**
A sequence of random variables $\{X_n\}_n$ converges almost surely if $P(\Omega_0)=1$ 

$\Omega_0$ may contain infinite limits. Instead we can consider
$$\Omega_1=\{w\in\Omega:\liminf\limits_{n\rightarrow\infty} X_n(\omega)=\limsup\limits_{n\rightarrow\infty}X_n(\omega)<\infty\}$$
>[!Note] Using eventually and i.o. sets
>We can write $\Omega_1$ as 
>$$\bigcap\limits_{k=1}^\infty \bigcup\limits_{m=1}^\infty\bigcap\limits_{n\geq m} \{|X_n-X|<\frac{1}{k}\}$$
>In plain English, this just states what a limit is: "For every $\epsilon=\frac{1}{k}>0$, there exists some $N_0$ such that $|X_n(\omega)-X(\omega)|<\epsilon$ for $n\geq N_0$". 