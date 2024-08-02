---
tags:
  - measure
---
There are two approaches. 

1) The *non-negative* extended real numbers are $[0,+\infty)$ which are the non-negative real numbers and an additional element labeled $+\infty$. 
	There are some conventions with $+\infty$:
	- $+\infty+x=+\infty$
	- $+\infty \cdot x=+\infty$
	- $+\infty\cdot 0 = +\infty$
	 The third convention induces *upward continuity*. If $x_n$ and $y_n$ increase to $x$ and $y$ respectively in $[0,+\infty)$, then $x_ny_n\rightarrow xy$. However, *downward continuity* is not true. If $x_n=+\infty$ and $y_n=1/n$, then $y_nx_n\rightarrow +\infty$ but $xy=0$. 
	
	Sums are always convergent! 


This asymmetry is a result of having only $+\infty$ and no negative numbers. The second alternative is to have both negative numbers and infinity, but it is more challenging.

2) Measure theory can consider *absolutely integrability*. This involves taking values in the range $(-\infty,+\infty)$. 

	Sums need not converge and rearranging terms may not produce the same limit. This relies on the Riemann rearrangement theorem.

(1) is concerned with the [[Monotone Convergence Theorem]] and (2) is concerned with the [[Dominated Convergence Theorem]].

With (1), we have more flexibility to rearrange sums however we like. From [Terrence], we define an infinite sum as
$$\sum\limits_{\alpha \in A}x_\alpha = \sup\limits_{finite\;F\subset A}\sum\limits_{\alpha\in F} x_\alpha$$
The advantage of this definition is that it works even when $A$ is not totally ordered.

**Fact 1**
This is consistent with what we observe when $A$ is finite. From this definition, note that rearranging terms is possible. Namely an bijection $\phi$ satisfies
$$\sum\limits_{\alpha\in A} x_\alpha = \sum\limits_{\alpha\in A}x_{\phi(\alpha)}$$
**Fact 2** (Fubini-Tonelli for series)
Let $(x_n, x_m)_{n,m\in \mathbb{N}} x_{n,m}$ be a doubly infinite sequence of *extended non-negative reals*. Then 
$$\sum\limits_{(n,m)\in \mathbb{N}^2}x_{n,m}=\sum\limits_{n\in\mathbb{N}}\sum\limits_{m\in\mathbb{N}}x_{n,m}=\sum\limits_{m\in\mathbb{N}}\sum\limits_{n\in\mathbb{N}}x_{n,m}$$
The "double sum" is equal an "iterated sum".
>[!proof]-
>First note that for any finite subset $F\subset \mathbb{N}^2$, nonn
>$$\sum\limits_{\alpha\in F}\leq \sum\limits_{n=\mathbb{N}}\sum\limits_{m=\mathbb{N}}x_{n,m}$$
>Taking the supremum implies
>$$\sum\limits_{(n,m)\in A}\leq \sum\limits_{n=\mathbb{N}}\sum\limits_{m=\mathbb{N}}x_{n,m}$$
>To prove the reverse inequality, we fix $N$ and consider the finite sum
>$$\sum\limits_{n=1}^N\sum\limits_{m=1}^\infty $$
>This sum is simply the limit of $\sum\limits_{n=1}^N\sum\limits\limits_{m=1}^M x_{n,m}$ as $M\rightarrow\infty$. These partial sums correspond to the square lattice $F=\{(n,m)|1\leq n,\leq m\}$ and hence
>$$\sum\limits_{n=1}^N\sum\limits_{m=1}^\infty x_{n,m}\leq\sum\limits_{(n,m)\subset \mathbb{N}^2}x_{n,m}$$
>We conclude by taking $N\rightarrow\infty$.

**Exercise 1** 
If $(x_\alpha)_{\alpha\in A}$ is a collection of numbers $x_\alpha \in [0,+\infty)$ such that $\sum\limits_{\alpha\in A} x_\alpha<\infty$, then $x_\alpha=0$ for all but at most countably many $\alpha\in A$, even if $A$ itself is uncountable.
>[!proof]-
>Assume that all of the terms are positive. If the sum converges, then $x_\alpha\rightarrow 0$. Now consider the bins $E_n=\{x_\alpha | \frac{1}{N}\leq x_\alpha < \frac{1}{N+1}\}$. One of these bins must have an uncountable number of elements if $A$ is uncountable. If none of them did, then the total number of indices in $A$ is at most countable. 
>We arrive at a contradiction:
>$$\sum\limits_{\alpha \in A}x_\alpha\geq \sum\limits_{\alpha\in E_n}\frac{1}{n}=+\infty$$
>
>Aside: The only way for the sum to converge is if there is at most a finite number of elements for each $E_n$. This corresponds to at most countably many positive $a\in A$.

**Exercise 2** (Tonelli's Theorem over arbitrary sets)
Let $A$, $B$ be sets (possibly infinite), and $(x_{n,m})_{n\in A,m\in B}$ be a doubly infinite sequence of extended non-negative reals. Show that
$$\sum\limits_{(n,m)\in A\times  B}x_{n,m}=\sum\limits_{n\in A}\sum\limits_{m\in B}x_{n,m} = \sum\limits_{m\in B}\sum\limits_{n\in A}x_{n,m}$$
>[!note] Proof
>The proof is similar to **Fact 1**'s proof. First note that for a finite subset $F\subset\mathbb{N}^2$, we can group the elements by the first coordinate. Let $F_1$ be the set of values the first coordinate takes in $F$ and $F_\alpha\subset F$ be the elements whose first coordinate is $\alpha\in A$. Then
> $$\sum\limits_{(n,m)\in F_\alpha}\leq \sum\limits_{m\in B}x_{\alpha,m}$$
> Thus 
> $$\sum\limits_{(n,m)\in F} x_{n,m}=\sum\limits_{\alpha\in F_1}\sum\limits_{m\in B:(\alpha,m)\in F_\alpha}\leq\sum\limits_{\alpha\in F_1}\sum\limits_{m\in B}x_{\alpha,m}$$
> Since $F_1$ is just a particular subset of $A$, taking the supremum on both sides yields
>  $$\sum\limits_{(n,m)\in A\times B}x_{n,m}\leq\sum_{n\in A}\sum_{m\in B} x_{n,m}$$
>
>For the reverse inequality, recall [[Supremum|a fact on supremums]].