---
tags:
  - analysis
  - measure
---
Jordan measure is less general compared to Lebesgue measure, but provides good intuition to understand Lebesgue measure. 

Using elementary sets (e.g. intervals, squares, finite unions, etc), we can approximate a set $E$ using elementary sets from within and around. 

>[!Definition] Jordan Measure
>Let $E$ be a bounded set. 
>- The *Jordan inner measure* $m_{*J}(E)$ of $E$ is defined as
>$$m_{*J}(E)=\sup\limits_{A\subset E,A\;elementary}m(A)$$
>- The *Jordan outer measure* $m^*_J(E)$ of E is defined as
>$$m^*_j(E)=\inf\limits_{E\subset B, B\; elementary}m(B)$$
>If $m_{*J}(E)=m^*_J(E)$, then $E$ is said to be *Jordan-measurable* and denote the Jordan measure (or Jordan content) as $m(E)$.

### Properties
**Fact 1** (Characterization of Jordan measure)
Let $E\subset\mathbb{R}^d$ be bounded. Then the following are equivalent.
1) $E$ is Jordan measurable.
2) For every $\epsilon>0$, there exists elementary sets $A\subset E\subset B$ such that $m(B\backslash A)\leq \epsilon$.
3) For every $\epsilon$, there exists an elementary set $A$ such that $m^*_J(A\Delta E)\leq \epsilon$.

$>[!proof] 
>$(1)\implies(2)$
>If $E$ is Jordan measurable, then there exists sets $A$ and $B$ such that $m(E)\lt m(A)+\frac{\epsilon}{2}$ and $m(E)\gt m(B)-\frac{\epsilon}{2}$. Combining, we see that $m(B)- m(A)\lt\epsilon$. By countable additivity $m(B)-m(A)=m(B\backslash A)$. 
>
>$(1)\implies (3)$
>Key idea: Notice that if $E\subset B$  where $B$ is elementary, then we can always improve $B$ by taking a refining it. $B$ is a finite union of rectangles. Take $E\subset C$ so that $m(C)-m(E)$ is even smaller and intersect it with $B$. 
>Finally notice that $B\backslash E$ is enclosed at a minimum at the boxes that partially 
>
>$(3)\implies (1)$
>1
>$(2)\implies (1)$
>This is a nice implication. Since $m_{*J}(E)\leq m^*_J(E)$ directly from the definition, we just need to show $m^*_J(E)\leq m_{*J}(E)$. Fix $\epsilon>0$. Then select a pair of elementary sets $A\subset E\subset B$ such $m(B\backslash A)< \frac{\epsilon}{2}$. We refine $A$ and $B$ by selecting another pair of elementary subsets $A'$ and $B'$ such that $m_{*J}(E)> m(A')-\frac{\epsilon}{4}$ and $m^*_J(E) < m(B')+\frac{\epsilon}{4}$, respectively, and intersecting them with $A$ and $B$. This produces new elementary sets $A''$ and $B''$ that satisfy both previous inequalities. In particular, 
>$$m^*_J(E)-m_{*J}(E)<m(B'')-m(A'')+\frac{\epsilon}{2}=m(B''\backslash A'')+\frac{\epsilon}{2}<\epsilon$$
>This implies the reverse inequality $m^*_J(E)\leq m_{*J}(E)$.






**Fact 2**
If $E$ and $F$ are measurable.
(1) $E\cup F$, $E\cap F$, $E\backslash F$, and $E\Delta F$ are measurable.
(2) For any $x\in\mathbb{R}^d$, $E+x$ is Jordan measurable and $m(E+x)=m(E)$.
>[!Proof]
>(1a)
>(1b) To prove intersection, we can choose an enclosing set $B\subset E\cap F$ that satisfies
>$$\begin{align*}
>m^*_J(E\cap F)< m(B)+\epsilon\\
>	m^*_J(E)x
>\end{align*}$$
>(1c)
>(1d)
>(2) The Jordan inner measure is at least $m(\emptyset)=0$.
>(3) We can use the Jordan inner measure here. For any elementary subset $Q$ of $E\cup F$ such that
>$$m(E\cup F)< m(Q)+\epsilon$$
>we can decompose the set into two small elementary subsets, $Q_1$ and $Q_2$, such that $Q_1\subset E$ and $Q_2\subset F$. Therefore, 
>(4) For every elementary set $A$ that covers $F$, it also covers $E$. Thus $m^*_J(E)=\inf_{E\subset A, A\;finite} m(A) \leq \inf_ {F\subset B, B\;finite} m(B)=m^*_J(B)$. Since $E$ and $F$ are measurable, $m(E)\leq m(F)$. 
>(5) $m(E\cup F) = m(E) + m(F\backslash E)\leq m(E) + m(F)$ by finite additivity and monotonicity.
>(6) For any elementary set $A\subset E$, we can translate it by $x$ to get a new set that is contained in $E+x$. These are in bijection with the original elementary subsets of $E$ and note $m(E+x)=m(E)$.

**Fact 3**
Let $B$ be a closed box in $\mathbb{R}^d$, and let $f:B\rightarrow\mathbb{R}$ be a continuous function. Then
1) The graph $\Gamma=\{(x,f(x)):x\in B\}\subset\mathbb{R}^{d+1}$ is Jordan measurable in $\mathbb{R}^{d+1}$ with Jordan measure zero. 
2) The set $\Gamma'=\{(x,t): x\in B;0\leq t\leq f(x)\}\subset\mathbb{R}^{d+1}$ is Jordan measurable.

>[!Proof]-
>For (1), note that $f$ is uniformly continuous on the compact box $B$. Thus for any $\epsilon>0$ there exists $\delta>0$ such that $d(x,y)<\delta$ implies $|f(x)-f(y)|<\epsilon$. Now since $B$ is compact, we can select a finite collection (square) neighborhoods $\{U_\delta(x_i)\}_{i=1,\ldots,N}$ whose union is $B$. For each square in this collection, construct the volume $A_i=U_\delta(x_i)\times (f(x_i)-\epsilon, f(x_i)+\epsilon)$.  Moreover, we ensure that the neighbors are disjoint. The measure of $\Gamma$ is at most
>$$m^*_J(\Gamma)<\sum\limits_{i=1}^N m(A_i)\epsilon = \epsilon|B|$$
>Taking $\epsilon\rightarrow 0$ implies $m^*_J(\Gamma)=m(\Gamma)=0$.
>
>For (2), the set describes the volume under $\max(f,0)$.. Consider the same boxes $A_i$. We modify this setup by "moving up" the boxes where $f(x)<0$ everywhere to height zero. Then this collection *is a cover* for the $\max(f,0)$. We stuff the remaining volume with new boxes $R_i$ underneath each box $A_i$ that is elevated.
>
>Recall from **Fact 1** that a set $E$ is Jordan measurable if there exists for any $\epsilon>0$, elementary subsets $A\subset E\subset B$ such that $m(B\backslash A)\leq \epsilon$. 
>
>If we set $B$ to be the $\{A_i\}\cup\{C_i\}$ and $A$ to be just the extra boxes $\{C_i\}$, then $A\backslash B$ is simply the cover $\{A_i\}$. Like in part $(1)$ this collection call always be refined, decreasing the measure to $0$. This proves that $\Gamma'$ is measurable. 

**Fact N**
Let $E\subset \mathbb{R}^d$ be a bounded set. Then
1) $E$ and $\bar{E}$ have the same Jordan outer measure. 
2) $E$ and $E^\circ$ have the same Jordan inner measure.
3) $E$ is Jordan measurable if and only if the boundary $\partial E$ of $E$ has Jordan outer measure zero.

>[!Proof]-
>Note: Since an elementary set is a finite union of closed boxes, it is closed.
>
>(1) For any elementary set $B\supset E$, the closure $\bar{E}$ is contained in $B$. Hence $m^*_J(E)\leq m^*_J(\bar{E})$. To show the reverse inequality, for some $B$
>$$m(E)>m(B)-\epsilon\geq \inf\limits_{\bar{E}\subset D} m(D)-\epsilon$$
>since $\bar{E}$ is the intersection of all closed sets, including $B$. Thus $m^*_J(E)>m(\bar{E})-\epsilon$ for arbitrary $\epsilon>0$ or $m^*_J(E)\geq m^*_J(\bar{E})$.
>
>(2) The interior of $E$, $E^\circ$,  is the set of points which have a neighborhood in $E$. This is equivalent to the union of all open sets enclosed in $E$.  Like (1), we can run the same argument except use open elementary sets $A\subset E$ and switch to the Jordan *inner* measure.
>
>(3) If $E$ is measurable, then $m_{*J}(E^\circ)=m(E)=m^*_J(\bar{E})$. Moreover note $m^*_J(E^\circ)\leq m(E)$ and $m_{*J}(\bar{E})\geq m(E)$. This implies that $E^\circ$ and $\bar{E}$ are Jordan measurable with measure $m(E)$. By finite additivity, $m(E^\circ) + m(\bar{E}\backslash E^\circ) = m(\bar{E})$ which implies $m(\partial E)=0$.

**Fact N+1** (A statement on polytopes)

**Fact N+2** (Metric Entropy formulation of Jordan measure)


### Non-example
The *bullet-riddled square* $[0,1]^2\backslash \mathbb{Q}^2$ and set of bullets $[0,1]^2\cap \mathbb{Q}^2$ are **not** Jordan measurable.
>[!hint]-
>We point our attention first to the bullet-riddled square, $\mathbb{S}$. Any elementary set $A$ enclosing $\mathbb{S}$ must contain the entire unit square (do I see why?). Thus, $m^*_J(\mathbb{S})=1$. Similarly any elementary set $A\subset \mathbb{S}$ must be the empty set. The Jordan inner measure is $0$.
>
>For the bullets, the any enclosed set must be a finite collection of bullets (not even countable!) which means the inner measure is $0$. Similarly any covering over the bullets must still contain the entire unit square (again do I see why!).




