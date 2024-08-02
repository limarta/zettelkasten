---
tags:
  - MCMC
  - computer_vision
---
The paper proposes a *data-driven MCMC* method to segment images. Their Markov chain consists of
- [[Reversible split-merge jumps]] and model switching.
- Diffusions for edges, fuzzy parts
## Problem Formulation
We seek to partition an image $\textbf{I}$ into an unknown number of disjoint regions. If $\Lambda$ is the coordinate lattice, then we want $K$ disjoint regions
$$\Lambda=\bigcup\limits_{i=1}^K R_i,\quad R_i\cap R_j=\phi$$An image region $\textbf{I}_R$ is a *realization* from a probabilistic model $p(I_R;\Theta)$. Here $\Theta$ is a stochastic process of some type.

Goal: Find latent variables $W=(K,\{R_i,\ell_i,\Theta_i\};i=1,\ldots,K)$ given the image $\textbf{I}$. In other words, we want $W\sim p(W|\textbf{I})$.

| Distributions                   | Purpose                                           |
| ------------------------------- | ------------------------------------------------- |
| Prior $p(W)$                    | The prior over the true segmentation.             |
| Likelihood $p(\textbf{I} \| W)$ | The observation model given the segmentation map. |
| Color image model               | The image color model                             |
### Prior $p(W)$
$$
\begin{align*}
p(W)&\propto p(K)\prod\limits_{i=1}^K p(R_i)p(\ell_i)p(\Theta_i|\ell_i)\\
&\propto e^{-\lambda_0 K}\prod\limits_{i=1}^K p(\Gamma_i)p(A_i)p(\ell_i)p(\Theta_i|\ell_i),\quad A_i=|R_i|\quad \Gamma_i=\partial R_i\\
&\propto \exp\left(-\lambda_0 K -\sum\limits_{i=1}^K\left[\mu\oint_{\partial R_i}\;\mathrm{d}s+\gamma|R_i|^c+\nu|\Theta_i|\right]\right)
\end{align*}
$$
>[!note] 
>The segmentation prior is broken up into three components. 
>1) The *number* of segments $K$.
>2) Each rectangle's area $A_i$ and contour $\partial R_i$
>3) The stochastic model $(\ell_i, \Theta_i)$. The distribution $p(\ell)$ is uniform over the available types and hence is dropped from the expression above. The resulting model parameters are $\Theta_i$ and is penalized from having large complexity.
>

### Likelihood Model
Given the stochastic processes $(\Theta_i,\ell_i)$, the visual patterns in each region $R_i$ are assumed to be **independent**. Other words,
$$p(\textbf{I}|W)=\prod\limits_{i=1}^K p(\textbf{I}_{R_i};\Theta_i, \ell_i)$$

| Stochastic Process              | Description                                       |
| ------------------------------- | ------------------------------------------------- |
|                                 | The prior over the true segmentation.             |
| Likelihood $p(\textbf{I} \| W)$ | The observation model given the segmentation map. |
| Color image model               | The image color model                             |
## Constructing the Markov Chains
## Data-driven MCMC
