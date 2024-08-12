---
tags:
  - measure
---
## Lebesgue Outer Measure
Recall the [[Jordan Measure|Jordan outer measure]] uses coverings composed of a *finite* number of boxes. This turns out to be limiting and causes $m^*_J$ to not be a measure. Instead, Lebesgue integration fixes this issue by allowing for a *countably* infinite number of boxes.

The **Lebesgue outer measure** is 
$$m^*(E)=\inf\limits_{\bigcup_{n=1}^\infty B_n\supset E;B_1,B_2,\ldots\;\text{boxes}} \sum\limits_{n=1}^\infty |B_n|$$

>[!Example] Differences between Lebesgue and Jordan measure
>The flexibility of countability allows us to measure $[-R,R]\cap\mathbb{Q}$. Using Jordan content, the inner and outer Jordan measure are $0$ and $2R$ respectively. On the other hand, the $m*([-R,R]\cap\mathbb{Q}) = 0$. 
>
>Also note that the Lebesgue measure of a singleton is $0$, so this example shows countable additivity is consistent.

**Fact 1**: Properties of Lebesgue outer measure
- $m^*(\varnothing) = 0$
- If $E\subset F\subset \mathbb{R}^d$, then $m^*(E)\leq m^*(F)$
- (Finite Subadditivity) $m^*(E\cup F)\leq m^*(E)+m^*(F)$
- (Countable Subadditivity) If $E_1,E_2\ldots$ is a countable sequence of sets, then $m^*\left(\bigcup_n E_n\right)\leq\sum_n m^*(E_n)$

>[!Proof]
>For (3), chose coverings $\{Q_i\}$ and $\{P_i\}$ of $E$ and $E^c\cap F$ respectively such that 
>$$m^*(E)>\sum_i |Q_i| - \frac{\epsilon}{2}$$
>$$m^*(F)>\sum_j |P_j| - \frac{\epsilon}{2}$$
>Then 
>$$\begin{align*}m*(E\cup F)-\epsilon &= m^*(E\cup (E^c\cap F)) -\epsilon \\
>&\leq \sum_i |Q_i|-\frac{\epsilon}{2} + \sum_j |P_j|-\frac{\epsilon}{2}\\&< m^*(E)+m^*(E^c\cap F)\end{align*}$$
>
>Since $\epsilon>0$ is arbitrary, $m^*(E\cup F)\leq m^*(E)+m^*(E^c\cap F)\leq m^*(E) + m^*(F)$.
>
>For (4), we can do the same thing as (3). Here though we need the axiom of choice and Tonelli's theorem. Note to self: It is sufficient to consider coverings of the original sequence, not terms like $E^c\cap F$.
>
>Given $\epsilon>0$, define the collection $\mathcal{G}_n$ to be the countable coverings $\{Q_i\}$ such that $m^*(E_n)+\frac{\epsilon}{2^n}>\sum_i |Q_i|$ and $E_n\subset\bigcup_i Q_i$. Select one covering from $G_n$ for each $n$ (using AOC!). Then
>
>$$\begin{align*}
>m^*(E_1\cup E_2\cup\ldots)&\leq \sum\limits_{n,j} |Q^n_j|\\
>&=\sum\limits_{n}\sum\limits_{j} |Q^n_j|&\text{by Tonelli's theorem}\\
>&<\sum\limits_{n} \left(m^*(E_n)+\frac{\epsilon}{2^n}\right)\\
>&=\epsilon+\sum\limits_{n} m^*(E_n)
>\end{align*}$$
>

**Fact 1**
Let $E,F\subset\mathbb{R}^d$ be such that $dist(E,F)>0$. Then $m^*(E\cup F)=m^*(E)+m^*(F)$. 
>[!Proof]
>By finite sub-additivity, $m^*(E\cup F)\leq m^*(E)+m^*(F)$. For the reverse inequality, we 
## Lebesgue Measurability
There are two ways to define measurability in $\mathbb{R}^d$, one concrete using the topology of $\mathbb{R}^d$ and one abstract using [[Caratheodory's criterion]].

**Fact 1**
1) Every closed set is Lebesgue measurable.
2) If $E\subset\mathbb{R}^d$ is Lebesgue measurable, then so is its complement $\mathbb{R}^d\backslash E$.

>[!Proof]
>If $C$ is closed, then $C^c$ is an open set which is measurable. Then for any $\epsilon>0$ there exists an open set $O\supset C^c$ such that $m(O\backslash C^c)<\epsilon$. 


**Fact 2**
Let $E\subset \mathbb{R}^d$ be Lebesgue measurable. Then
$$m(E)=\sup\limits_{K\subset E,K\;\text{compact}}m(K)$$
 **Fact 3**
Let $E\subset \mathbb{R}^d$. The following are equivalent.
1) $E$ is Lebesgue measurable with finite measure.
2)  (Outer approximation by open) For every $\epsilon>0$, one can contain $E$ in an open set $U$ of finite measure with $m^*(U\backslash E)\leq \epsilon$.
3)  (Almost open bounded) $E$ differs from a bounded open set $U$ by a set of arbitrarily small Lebesgue outer measure. In other words, for every $\epsilon>0$, there exists an bounded open set $U$ such that $m^*(E\Delta U)\leq \epsilon$.
4) (Inner approximation by compact) For every $\epsilon>0$, one can find a compact set $F$ contained in $E$ with $m^*(E\backslash F)\leq \epsilon$.
5)  (Almost compact) $E$ differs from a compact set by a set of arbitrarily small Lebesgue outer measure.
6) (Almost bounded measurable) $E$ differs from a Lebesgue measurable set with finite measure by a set of arbitrarily small Lebesgue outer measure.
7) (Almost finite measure) $E$ differs from a Lebesgue measurable set with finite measure by a set of arbitrarily small Lebesgue outer measure.
8) (Almost elementary) $E$ differs from an elementary set by a set of arbitrarily small Lebesgue outer measure.
9)  (Almost dyadically elementary) For every $\epsilon>0$, there exists an integer $n$ and a finite union $F$ of closed dyadic cubes of sidelength $2^{-n}$ such that $m^*(E\Delta F)\leq \epsilon$.

>[!Proof]- Outer approximation by open
>$(1)\implies(2)$
>Set $\epsilon>0$. By measurability there exists an open set $O$ such that $m^*(O\backslash E)<\epsilon$. Moreover since $E$ has finite measure, there exists a countable cover $A=\bigcup A_i$ of open cubes. $A$ is open and so the intersection $A\cap O$ is also open. By monotonicity, $m^*(A\cap O)\leq m^*(A)\leq \sum_i |A_i|<\infty$. Finally note that $A\cap O$ is a set of finite Lebesgue outer measure that encloses $E$.
>
>$(2)\implies (1)$ 
>This is the definition of Lebesgue measurability.
>
>$(1)\implies (3)$
>

>[!Proof] Almost open bounded
