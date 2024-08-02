---
tags:
  - distribution
  - nonparametric
---
The Chinese Restaurant Process demonstrates the clustering effect of the [[Dirichlet Process#Chinese Restaurant Process and the Clustering Property|Dirichlet Process]].

Let $G\sim DP(\alpha, H)$ and let $\theta_i\sim G$ be samples from the random distribution. Then the *predictive distribution* is
$$\begin{align*}\theta_{n+1}|\theta_1,\ldots,\theta_n&\sim \frac{\alpha}{\alpha+n}\left(H+\sum_i\delta_{\theta_i}\right)\\
&=\frac{\alpha}{\alpha+n}\left(H+\sum_k n_k\delta_{\theta_k^*}\right)\end{align*}$$
where $\theta_k^*$ are the unique values taken on by $\{\theta_i\}$. The unique values form a partition over $[n]$, so we can imagine draws of $(\theta_1,\ldots,\theta_n)$ to be sampled partitions. 

The random partition characterization is enough to describe the DP:
- Sample a random partition of $[n]$.
- For each cluster, sample $\theta_k^*\sim H$ and assign each member of the cluster $\theta_i=\theta_k^*$.

>[!warning]
>What does it mean to appeal to de Finetti?



>[!extra]
>The CRP also defines a distribution over permutations. Each round table is a cycle which fully characterizes the permutation.