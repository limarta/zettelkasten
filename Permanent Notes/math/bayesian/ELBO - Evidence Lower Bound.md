---
tags:
  - bayesian
  - ML
---
The ELBO comes from estimating the [[Estimating Log-Evidence||evidence]]. It can be derived by

$$
\begin{align*}
\log p(y) &= \log \frac{p(x,y)}{p(x|y)}\tag{1}\\
&= \log \frac{p(x,y)}{q(x)} + \log \frac{q(x)}{p(x|y)}\quad\text{for all q(x)}\\
&= E_{x\sim q}\left[\log\frac{p(x,y)}{q(x)}+\log \frac{q(x)}{p(x|y)}\right] \tag{2}\\
&=E_{x\sim q}\left[\log\frac{p(x,y)}{q(x)}\right]+E_{x\sim q}\left[\log\frac{q(x)}{p(x|y)}\right]\\
&=ELBO(q(x)||p(x,y))+D(q(x)||p(x|y))
\end{align*}
$$
On line (2), we use the fact that the expression is independent with respect to $x$. Thus we can average it over $q(x)$. 

Observation 1:
Since the divergence $D(q|| p_{x|y})\geq 0$ , we can drop the term to get
$$\log p(y) \geq ELBO(q || p_{xy})$$
This is where we can the "lower bound" part of the name. Maximizing this lower bound gives is better estimates to $\log p(y)$. In fact we obtain equality when the divergence term is **zero**. In other words, when the proposal $q(x)$ exactly matches $p(x|y)$ - the posterior. We can interpret this as saying in order to understand the evidence $p(y)$, we must understand the posterior $p(x|y)$.

Observation 2:
On line (1), we used specifically $p(x,y)$ and $p(x|y)$ to expression $p(y)$, but this isn't the only way. In general if we can consider $p(y)=\tilde{p}(y)/{Z}$ where $Z$ is the [[Normalization Constant|normalizing constant]] and run the same argument. 

Observation 3:
If we know $p(x,y)$ and $q(x)$ we can write out the integral for $ELBO$. In general, it is quite tough to actually compute the $ELBO$, but the form of the expectation yields a simple Monte Carlo estimate: take values $\log p(x_i,y)/q(x_i)$ and average them together.

Question:
From Observation 1, we can view estimation as an optimization problem over some probability simplex.  Observation 3 tells us how to evaluate $ELBO$, but how do we even minimize it? We can use several [[Gradients of Expectations||tricks]].


