---
tags:
  - probability
---
The *distribution* **function** of a real-valued random variable $X$ is defined as
$$F(x)=P(X\leq x)$$
Note this is different from the *[[Random Variable|distribution of X]]* (or *law of X*).

**Theorem** Any distribution function $F$ has the following properties:
1) $F$ is non-decreasing.
2) $\lim_{x\rightarrow\infty} F(x)=1$, then $\lim_{x\rightarrow-\infty}F(x)=0$.
3) $F$ is right continuous.
4) If $F(x-)=\lim_{y\uparrow x}$, then $F(x-)=P(X<x)$.
5) $P(X=x) = F(x)-F(x-)$.

>[!Proof]-
>1) Comes directly from monotonicity of the measure.
>2) From continuity from above and below respectively. (Care is taken to validate the hypothesis from below).
>3) If $y\downarrow x$, then $\{X\leq y\}\downarrow\{X\leq x\}$. 
>4) If $y\uparrow x$, then $\{X\leq y\}\uparrow\{X\lt x\}$.
>5) $P(X=x)=P(X\leq x) - P(X<x)$.

### Skorokhod's Theorem
**Theorem** (Skorokhod's Theorem)
If $F$ satisfies $(1)$, $(2)$, and $(3)$, then it is the distribution of some random variable.

>[!Proof]-
>We view the set $[0,1]$ as a probability space with the Borel $\sigma$-algebra and probability measure $P$. Let $\omega\in[0,1]$ and define the random variable
>$$X(\omega)=\sup\limits_{y}\{y|F(y)<\omega\}$$
>
>The goal is to show $$X^{-1}((-\infty, x])=\{\omega|X(\omega)\leq x\}=\{\omega|\omega\leq F(x)\}$$
>
>We verify this by first considering $\omega\leq F(X)$. If so, then $X(\omega)\leq x$ since $x\notin \{y|F(y)<\omega\}$. On the other hand consider $\omega>F(x)$. Then there exists some $\epsilon>0$ such that $F(\omega+\epsilon)<\omega$ since $F$ is right-continuous. So $X(\omega)\geq x+\epsilon>x$. 
>
>With the identity established, the last piece is to evaluate it under $P$ (the Lebesgue measure). This is just $P(\{w|w\leq F(x)\})=F(x)$ since this is just the interval $[0,F(x)]$.

**Note**
Even though $F$ may not be 1-1, some books refer to $X$ as the "inverse of $F$".

**Fact**
A distribution function has at most countably many discontinuities.

>[!Proof]
>A discrete probability distribution has a countable number of discontinuities in its CDF, so all that is left to show is that no distribution function has an uncountable number of discontinuities.
>
>Since $F$ is non-decreasing and right-continuous, the only type of discontinuity is a *jump continuity*. Consider a discontinuity at $x$ and fix $\epsilon_x>0$. Then for intervals $I_n=(x,x+\frac{1}{n})$ there exists a value $x'$ such that $F(x')-F(x)\geq \epsilon_x$ since $F$ is non-decreasing. Create a sequence $\{x_n\}_n$ corresponding to each $n$.  Then
>$$\inf\limits_{y\in(x,\infty)} F(y)=\inf_n F(x_n)\geq \epsilon$$ 
>This implies $F(x)<F(x)+\epsilon_x<F(y)$ for $y>x$. 
>
>Suppose there are an uncountable number of discontinuities and denote this set as $D$. Since $F$ is a non-decreasing function bounded between $0$ and $1$, the sum
>$$\sum\limits_{x\in D} \epsilon_x<\infty$$
>
>Using Fact ? from [[Extended Real Numbers]], only a finite number of terms in this sequence can be positive. This is a contradiction.

### Density Function
When the distribution function $F(x)=P(X\leq x)$ has the form
$$F(x)=\int\limits_{-\infty}^x f(y)\;\mathrm{d}y$$
we say $X$ has density $f$.