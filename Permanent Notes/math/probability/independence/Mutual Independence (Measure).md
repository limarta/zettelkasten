---
tags:
  - independence
---
Let $\mathcal{A}_\alpha\in\mathbb{F}$ be a set of events indexed by (possibly uncountable) $\alpha$.  The collection is mutually independent if for any $L<\infty$ and distinct indices $\alpha_1,\ldots,\alpha_L\in\mathcal{I}$,
$$P(A_1\cap\ldots\cap A_L)=\prod\limits_{n=1}^L P(A_n)\quad \forall A_n\in \mathcal{A}_{\alpha_k}$$
**Fact 1**
Suppose $\mathcal{G}_i=\sigma(\mathcal{A}_i)\subset \mathcal{F}_i$ where $\mathcal{A}_i$ are [[π-System|π systems]] for $i=1,2,\ldots, n$. Then the collections $\mathcal{G}_i$ are mutually independent if the $\pi$-systems are mutually independent.

>[!Proof]
>Using a lemma of [[Dynkin's Pi-Lambda Theorem]].

The fact that a (possibly uncountable) collection independent $\pi$-systems $\mathcal{A}_i$ implies the generated $\sigma$-algebras are independent directly follows from *Fact 1*.

Independence is also preserved under projections.

**Fact 2**
If the events $\mathcal{H}_{\alpha,\beta}$, $(\alpha,\beta)\in\mathcal{J}$ are mutually independent $\pi$-systems, then $\mathcal{G}_\alpha=\sigma\left(\bigcup_\beta \mathcal{H}_{\alpha,\beta}\right)$ are also mutually independent.

>[!Proof]
>


>[!Example]
>Let $X_1,X_2,\ldots$ be mutually independent. (Recall this means any *finite* collection of the events $\{\sigma(X_i)\}$ are mutually independent). 
>
>From the previous fact, the events $\sigma(\sigma(X_1)\cup\ldots\cup \sigma(X_t))$ and $\sigma(\bigcup_{n\geq t+1}\sigma(X_n))$ are independent. Each event is just the generated $\sigma$-algebra of smaller $\sigma$-algebra and so they are equivalent to $\sigma(X_1,\ldots, X_t)$ and $\sigma(X_{t+1},\ldots)$ respectively.


