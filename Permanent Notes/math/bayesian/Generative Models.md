---
tags:
  - bayesian
  - ML
---

A generative model is a probability distribution $p(x,y)$ of latents $x$ and observations $y$. 

We (usually) have access to 
- The latent prior $p(x)$
- The observation model $p(y|x)$

Combining the two gives us $p(x,y)=p(y|x)p(x)$, but often we are interested in
$$p(x,y)=p(x|y)p(y)$$

Methods for finding $p(y|x)$ and $p(y)$.

- Exact Bayesian inference
- Important sampling
- Markov Chain Monte Carlo
- Encoder-Decoder models

