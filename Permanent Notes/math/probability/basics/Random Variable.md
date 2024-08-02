---
tags:
  - probability
  - measure
---
### Real-valued Random Variables
A function $X$ defined on $\Omega$ is a **random variable** if for every Borel set $B\subset \mathbb{R}$, the preimage $X^{-1}(B)\in \mathcal{F}$.

When an R.V. is referred to as $\mathcal{F}$-measurable, it is to emphasize the $\sigma$-algebra.

Since a random variable is a [[Measurable Function|measurable function]], it has the induced measure
$$\mu(B)=P(X^{-1}(B))$$
known as the *law of X* or *distribution of X* or *probability law of X*. 

See [[measurable function]] to verify the *law of X* is a valid measure.

Every random variable induces a [[Distribution Function|distribution function]]. Given a non-decreasing, right-continuous function with range in $[0,1]$, one can use [[Distribution Function#Skorokhod's Theorem|Skorokhod's theorem]] to construct a random variable.

**Example 1** (Indicator Function)
The indicator function 
$$1_A(\omega)=\begin{cases}
1\quad\omega\in A\\
0\quad\omega\notin A
\end{cases}$$

A real-valued random variable
### Random Variable
A random variable can similarly be defined for a general measurable space. Let $X:\Omega\rightarrow S$ be a [[Measurable Function|measurable function]] from $(\Omega,\mathcal{F})$ to $(S,\mathcal{S})$. 

$X$ is a $(S,\mathcal{S})$-*random variable* if the measure of $