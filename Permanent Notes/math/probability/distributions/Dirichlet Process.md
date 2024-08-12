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

Observations:
- As $\alpha\rightarrow\infty$, $X(A)\rightarrow H(A)$ for measurable $A$. We can interpret this is as the tendency to stick with the $H$ even given observations $\theta_1,\theta_2, \ldots$.
- For measurable $A$, $\mathbb{E}\left[G(A)\right]=H(A)$. 
>[!hint]-
>WLOG consider the first component $X(A_1)$ of the [[Dirichlet Distribution]]. The expectation is $\mathbb{E}\left[X(A_1)\right]=\frac{\alpha H(A_1)}{\alpha\sum H(A_i)}=H(A_1)$
## Posterior Distribution
The [[Dirichlet Distribution]] is the conjugate prior of the multinomial distribution. Let $\{A_i\}$ be a finite partition of $\Theta$. Recall that
$$(G(A_1),\ldots, G(A_r))\sim Dir(\alpha H(A_1),\ldots, \alpha H(A_r))$$
Now for samples $\theta_1,\ldots, \theta_n$, we can count the number of instances in each partition $A_k$ - denote this as  $\#n_k=|\left\{\theta_i\in A_k\right\}|$. Each sample $x\in A_k$ is sampled with probability $G(A_k)$ and thus we can view each $\theta_i$ as a sample from the multinomial distribution $Mult(G(A_1),\ldots, G(A_r))$.

Conditioning on the observations - really the counts per partition - updates the Dirichlet parameters from $(\alpha H(A_1),\ldots, \alpha H(A_r)\rightarrow(\alpha H(A_1)+\#n_1,\ldots, \alpha H(A_r)+\#n_r)$

This is true **for all** partitions $\{A_k\}$ and so $G|\theta_1,\ldots, \theta_n$ must also be a Dirichlet *process* as well.

Q: What are the updated coefficients for the DP?
>[!hint]-
>If $H'$ is the new base distribution, note that $H'(A)\propto \alpha H(A)+\#n$ or that $H'(x)\propto \alpha H(x)+\sum\limits_{i}\delta_{\theta_i}$. For any partition $\{A_k\}$, we find the normalizing the terms yields
>$$H'(A_k)=\frac{\alpha H(A_k)+\#n_k}{\sum\limits_{j=1}^r \alpha H(A_j)+\#n_j}=\frac{H(A_k)+\#n_k}{\alpha+N}$$
>Following a similar observation as above, 
>$$H'(x)=\frac{\alpha H(x)+\sum_{i}\delta_{\theta_i}}{\alpha+N}$$
>and the new concentration parameter is $\alpha' =\alpha +N$. 
>

To summarize, 
$$G|\theta_1,\ldots, \theta_n\sim DP(\alpha + n, \frac{\alpha}{\alpha + n}H+\frac{n}{\alpha + n}\frac{\sum_i \delta_{\theta_i}}{n})$$
Observation:
- The new base distribution is a weighed average of the old base distribution $H$ and the empirical distribution $\sum_i \delta_{\theta_i}/N$. Refer to the previous observation [[Dirichlet Process#Dirichlet Process|here]].
- The poster base distribution is also the predictive distribution $\theta_n|\theta_1,\ldots, \theta_{n-1}$. See [[Dirichlet Process#Predictive Distribution - Samples from a Dirichlet Process|here]].
## Predictive Distribution - Samples from a Dirichlet Process
We wish to express $\theta_n|\theta_1,\ldots, \theta_{n-1}$, but we need to account for the random variable $G$. We use the [[Model Inference|hierarchical model]] to express this distribution (this is standard). For a fixed $A$, the probability

$$\begin{align*}
P(\theta_{n+1}\in A|\theta_1,\ldots, \theta_{n})&=\int P(\theta_{n+1}\in A, |G,\theta_1,\ldots,\theta_{n})P(G|\theta_1,\ldots, \theta_{n})\;\mathrm{d}P(G)\\
&=\int P(\theta_{n+1}\in A|G)P(G|\theta_1,\ldots,\theta_{n})\;\mathrm{d}P(G)\\
&=\int G(A)P(G|\theta_1,\ldots, \theta_{n})\;\mathrm{d}P(G)\\
&=\mathbb{E}\left[G(A)|\theta_1,\ldots, \theta_{n}\right]\\
	&=\frac{\alpha}{\alpha +n}H(A)+\frac{n}{\alpha+n}\#n
\end{align*}$$
Thus the predictive distribution is
$$\theta_{n+1}|\theta_1,\ldots,\theta_{n}\sim \frac{\alpha}{\alpha+n}H+\frac{1}{\alpha+n}\sum_i \delta_{\theta_i}$$
The predictive distribution of $\theta_{n+1}$ is the **same** as the posterior base distribution. Thus 
$$\theta_n|\theta_1,\ldots, \theta_{n-1}\sim \begin{cases}
	X_i&\text{w.p.}\;\frac{1}{n-1+\alpha }\\
X\sim H&\text{w.p.}\;\frac{\alpha}{n-1+\alpha}
 \end{cases}$$
 Then for a sequence $\theta_1,\ldots, \theta_n$, the chain rule gives us
 $$P(\theta_1)P(\theta_2|\theta_1)\ldots P(\theta_n|\theta_1,\ldots,\theta_{n-1})=\frac{\square}{1-1+\alpha}\cdots\frac{\square}{n-1+\alpha}$$
 The $\square$s above represent the numerators which are depend on whether $H$ is sampled or a previous value $\theta_i$ is reused. Let there be $K$ unique values denoted by $\theta_k^*$. Then each $\theta_i$ must equal to one of the $\theta_k^*$ for some $k$. If $\theta_k^*$ is sampled, then the probability this occurred is $\# \theta_k^*/(n-1+\alpha)$ where $\#\theta_k^*$ is the number of previous instances of $\theta_k^*$. 

The product above can be re-arranged as (notice that order is irrelevant)
$$\frac{\alpha^k\prod\limits_{k=1}^K(\#\theta_k^*-1)!}{\alpha(1+\alpha)\cdots(n-1+\alpha)}\prod\limits_{k=1}^K H(\theta_k^*)$$
>[!note]-
>The $\alpha\cdot H(\theta_k^*)$ comes from drawing $\theta_k^*$ for the first time. The factorials are due to sampling $\theta_k^*$ repeatedly. 

This means the joint distribution of $\theta_1,\ldots, \theta_n$ is exchangeable for all $n$. Precisely, $P(\theta_1,\ldots,\theta_n)=P(\theta_{\sigma(1)},\ldots,\theta_{\sigma(n)})$. We can apply [[De Finetti's Representation Theorem|De Finetti's theorem]] on the infinitely exchangeable sequence. There exists a random distribution $G$ such that the sequence is composed of $i.i.d$ draws from
$$P(\theta_1,\ldots,\theta_n)=\int\prod\limits_{i=1}^nG(\theta_i)\;\mathrm{d}P(G)$$
The distribution $P(G)$ is the Dirichlet process we are after.
## Blackwell-MacQueen Urn Scheme
We can encode the predictive probability $\theta_{n}|\theta_1,\ldots,\theta_{n-1}$ above as "urn simulation" known as the *Blackwell-MacQueen Urn Scheme* or the *Chinese Restaurant Process*.

- Assume $H$ is a distribution over colors.
- Each $X_n$ represents a color ball placed in the urn.
- Start with an empty urn.
- On step $n$:
	* With probability proportional to $\alpha$, draw $X_n\sim H$ and place the ball into the urn.
	* With probability proportional to $n-1$, draw a ball from the urn. Return the ball and add a second ball with the *same* color.

These schemes describe values drawn from $G\sim DP(\alpha, H)$ but don't actually describe how $G$ looks like. For that, we need a different construction.
### Chinese Restaurant Process and the Clustering Property
See [[Chinese Restaurant Process]].
## Stick Breaking
The Urn scheme and CRP provide a way to sample from $G$, but what does $G$ itself look like?

Observations:
- $G$ is almost surely a infinite discrete distribution - in other words a distribution of atoms with probability masses. 
- The CRP and urn scheme describe $G$ "in the limit" after many samples reveal the clustering, but can we obtain the *exact* point masses?

The **stick breaking** construction provides the point masses, albeit in another infinite stochastic process. In other words, to generate more point masses, we need to run the simulation longer.

$$
\begin{align*}
\beta_k&\sim Beta(1,\alpha)\quad&\theta_k^*&\sim H\\
\pi_k&=\beta_k\prod\limits_{i=1}^{k-1}(1-\beta_i)\quad &G&=\sum\limits_{k=1}^\infty \pi_k \delta_{\theta_k^*}
\end{align*}$$
The $\pi_k$ can be viewed as parts of a unit stick. $\pi_1=\beta_1$ is the first piece, $\pi_2=\beta_2(1-\beta_1)$ is the second piece, etc.
# Applications

- A Dirichlet Process can be used for *cluster modeling*. In simple models, the number of clusters is fixed, but a DP allows for an unknown number of clusters. See here for more [[Non-Parametric Cluster Modeling|examples of non-parametric modeling]]. 