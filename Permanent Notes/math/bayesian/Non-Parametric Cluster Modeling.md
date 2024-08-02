---
tags:
  - bayesian
  - nonparametric
---
Bayesian cluster modeling can use an *unknown* number of clusters. A popular non-parametric prior for this is the [[Dirichlet Process]].


Compare a *finite* mixture model:
$$\begin{align*}
\pi&\sim Dirchlet(\alpha/K,\ldots,\alpha/K)\\
\eta_k&\sim G\\
c_i&\sim Mult(\pi)\\
y_i|c_i,\eta_1,\ldots,\eta_K&\sim F(\cdot;\eta_{c_i})
\end{align*}$$
with the analogous Dirichlet Process mixture model:
$$
\begin{align*}
G|\alpha, G_0&\sim DP(\alpha, G_0)\\
\eta_i&\sim G\\
y_n|\eta_i&\sim F(\cdot;\eta_i)
\end{align*}$$

The $G$ sampled from the DP is a discrete probability distribution, so there is a non-zero probability for repeated values $\eta$. This takes care of the clustering.

## Inference
- Dirichlet Processes are non-parametric, so using the EM algorithm is difficult. 
- Use MCMC
- Use variational inference.
