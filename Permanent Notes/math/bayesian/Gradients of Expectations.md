---
tags:
  - bayesian
  - ML
what:
---
How can we optimize the quantity $E_p[f(x)]$? Over what parameters? To make this concrete, consider a parameterized distribution $p_\theta(x)$ and a function $f(x;\theta)$. 

**Goal**: Calculate $\nabla_\theta E_{p_\theta}\left[f_\theta(x) \right]$ 

In general, this is hard. There are several approaches.
- [[REINFORCE Gradient]]
- The [[The Re-parameterization Trick|re-parameterization trick]]