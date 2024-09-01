---
tags:
  - functional_analysis
  - hilbert_space
---
Let $\{e_i\}$ be a [[Maximal Orthonormal Basis]] in a Hilbert space $H$. The *Fourier-Bessel* series of an element $u\in H$ is defined as
$$\sum\limits_i^\infty \langle u, e_i\rangle e_i$$

Under these conditions, the series converges to $u$. In other words
$$u=\sum\limits_i^\infty \langle u, e_i\rangle e_i$$

>[!Proof]
>The sequence of partial sums $u_N=\sum_i^\infty \langle u, e_i\rangle e_i$ is Cauchy. If $N< M$, $$||u_M-u_N||^2=\sum_{i=N+1}^M \langle u, e_i\rangle^2$$
>By the Bessel inequality, $\sum_{i>N} \langle u, e_i\rangle^2\rightarrow 0$ as $N\rightarrow \infty$.
>
>Since $H$ is complete, $u_N\rightarrow w\in H$. Now we show that $w=u$. By continuity of the inner product,
>>[!Tip]- Continuity of Inner Product
>>Does $\langle x,e\rangle\rightarrow\langle y,e\rangle$ as $x\rightarrow y$? Observe $|\langle x-y,e\rangle|\leq ||x-y||\cdot ||e||$. Hence $x\rightarrow y$ implies $|\langle x,e\rangle - \langle y,e\rangle|\rightarrow 0$. 
>
>$$\begin{align*}\langle w,e_i\rangle - \langle u_N, e_i\rangle&=\left\langle \lim \limits_{M\rightarrow \infty} u_M, e_i\right\rangle - \langle u_N, e_i\rangle\\
>&=\lim\limits_{M\rightarrow\infty} \langle u_M, e_i\rangle - \langle u_N, e_i\rangle\\
>&=\langle u, e_i\rangle-\langle u, e_i\rangle\\
>&=0\end{align*}$$
>
>Since the orthonormal sequence is maximal, $w-u=0$.





