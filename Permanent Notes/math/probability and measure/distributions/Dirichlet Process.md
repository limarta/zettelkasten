---
tags:
  - distribution
  - nonparametric
---
A Dirichlet process (DP) is a distribution over distributions. 

Traditional parametric models use a fixed dimension or fixed number of components which causes under- or over-fitting. 

## Generalization of Dirichlet distribution
Consider a $K$-component mixture model where the mixing proportions $\pi$ is sampled from a $K$-component Dirichlet distribution.
$$\begin{align*}
\pi|\alpha &\sim Dir\left(\frac{\alpha}{K},\ldots \frac{\alpha}{K}\right)\\
z_i|\pi&\sim Mult(\pi_1,\ldots, \pi_K)\\
\theta_k^* &\sim H\\
x_i | z_i, \{\theta_k^*\} &\sim F(\theta_{z_i}^*)
\end{align*}$$
$\theta_k^*$ are the distribution parameters of $F$ for the $k$-th component. As $K\rightarrow\infty$ the number of components used in inference is roughly $O(\alpha \log n)$ for $n$ datapoints.

## Dirichlet Process
There are two parameters that affect a Dirichlet process - a hyperparameter $\alpha>0$ and a distribution $H$ over $\Theta$. $H$ is referred to as the *base distribution*. 

The Dirichlet Process $DP(H,\alpha)$ is a probability distribution whose samples are distributions over $\Theta$ such that:
- Let any partition $A_1,\ldots, A_r$ of $\Theta$. If $X\sim DP(H, \alpha)$, then $$(X(A_1),\ldots X(A_r)) \sim Dir(aH(A_1), \ldots, aH(A_r))$$
The value $X(A_i$) is the probability of measurable set $A_i$.

Facts:
- As $\alpha\rightarrow\infty$, $X(A)\rightarrow H(A)$ for measurable $A$.
- For measurable $A$, $\mathbb{E}\left[G(A)\right]=H(A)$. 
	>[!hint]-
	>WLOG consider the first component $X(A_1)$ of the [[Dirichlet Distribution]]. The expectation is $\mathbb{E}\left[X(A_1)\right]=\frac{\alpha H(A_1)}{\alpha\sum H(A_i)}=H(A_1)$
-

## Posterior Distribution
Let $G\sim DP(\alpha, H)$. Since $G$ is a distribution, we can draw samples from it. Recall that $G$ is also a distribution over $\Theta$. Let $\theta_1,\ldots, \theta_n$ be independent draws from $G$. 
>[!question] Given $\theta_1,\ldots, \theta_n$, what is the posterior of $G$?
>