---
tags:
  - AD
---
[[Forward Mode]] uses the concept of *dual numbers* to implement differentiation. 

### Dual Numbers
A dual number is of the form $a+b\epsilon$ where $\epsilon^2=0$. We can view dual numbers equivalently the quotient ring $R[x]/(x^2)$. Plugging in a dual number into a differentiable function outputs the derivative:

Let $f(x)=f(x_0)+f'(x_0)(x-x_0)+\frac{f''(x_0)}{2}(x-x_0)^2+\ldots$ 

Then
$$\begin{align*}
f(x_0+\epsilon)=f(x_0)+f'(x_0)\epsilon
\end{align*}$$
We see that the dual term has the derivative! 

### Chain Rule
Now if we have a function $h=f\circ g$, does evaluating each nested function in sequence respect the chain rule? Yes: $f(g(a+\epsilon))=f(g(a)+g'(a)\epsilon)=f(g(a))+f'(g(a))g'(a)\epsilon$.

### Forward Mode AD

If $f:\mathbb{R}^m \rightarrow\mathbb{R}^n$, then
- Forward mode is best when $m<<n$.
- [[Reverse Mode]] is best when $m>>n$. 
