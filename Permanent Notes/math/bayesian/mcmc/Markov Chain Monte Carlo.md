---
tags:
  - MCMC
  - bayesian
---
Markov Chain Monte Carlo (MCMC) is a Monte Carlo technique used to approximate a target distribution when the target distribution is itself hard to express and sample from. 

MCMC algorithms take on several flavors but can all be tied together by all algorithms do essentially two steps:
- Propose a new sample in the state space using an *auxiliary* distribution known as the **proposal** distribution. 
- Proposed jumps $x\rightarrow x'$ are then gated by an acceptance score $0\leq a\leq 1$.  MCMC will jump to the new state $x'$ with probability $a$. If $a$ is small, then there must be a mismatch between the target and the proposal. If $a$ is large, it is harder to tell. It could mean (a) that the probabilities of choosing $x'$ are roughly the same for the target or the proposal or (b) that the proposal places so little weight on $x'$ compared to the target.
**Note** that the proposal distribution need not equal to the target (otherwise what is the point right?), and instead can basically be "anything". The gotcha here is that even though the proposal can be anything, the shape and structure of it can affect how fast the approximation converges (i.e. in the TV sense, for example).

## Concepts
- Gibbs Sampling
- Metropolis-Hastings
- Block sampler
- Rejuvenation
- Involutive MCMC
