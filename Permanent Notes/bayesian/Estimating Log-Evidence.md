---
tags:
  - Bayesian
  - ML
---
**Goal**: Estimate $\log p(y)$ where $y$ is the "evidence" or set of observations. 

When dealing with generative models, we (usually) have access to
- The generative model $p(x,y)$ of joint latents and observations
- The latent prior $p(x)$
- The observation model $p(y|x)$

But not $p(y|x)$ or $p(y)$, and obtain these quantities exactly requires intractable marginalization.

**Related Problems**:
- Estimating the [[Normalization Constant|normalization constant]].
