---
tags:
  - measure
---
Fix $(\mathbb{S},\mathcal{F},\mu)$. Each non-negative measurable function $f$ on $(\mathbb{S},\mathcal{F})$ induces a new measure, denoted as $f\mu$.

**Fact 1**
Every $f\in m\mathcal{F}+$ induces a measure $f\mu$ on $(\mathbb{S},\mathcal{F})$ via $(f\mu)(A)=\mu(fI_A)$. These measures satisfy the compositional relation $(hf)\mu=h(f\mu)$.

>[!Proof] (Apply the Standard Integration Machine)
>Let $f\in m\mathcal{F}^+$. 
>
>We start with an **indicator** $h=I_E$. Then
>$$(hf)(\mu)(A)=\mu(fI_EI_A)=(f\mu)(I_EI_A)=(h)(f\mu)(A)$$
>
>Now let $h$ be the **simple function** $\sum\limits_{n=1}^N c_n I_{E_n}$. Then 
>$$\begin{align*}
>(hf)(\mu)(A)&=\mu\left(f\sum\limits_{n=1}^Nc_nI_{E_n}I_A\right)\\
>&=\sum\limits_{n=1}^Nc_n\mu(fI_{E_n}I_A)\\
>&=\sum\limits_{n=1}^N c_n(f\mu)(I_{E_n}I_A)\\
>&=(f\mu)\left(\sum\limits_{n=1}^N c_nI_{E_n}I_A\right)\\
>&=(h)(f\mu)(A)
>\end{align*}$$
>
>Now let $h\in m\mathcal{F}^+$ be a **non-negative** measurable function. We can choose a sequence of increasing simple functions $h_n$ such that $h_n\rightarrow h$. Then by Monotone Convergence,
>$$\begin{align*}(hf)(\mu)(A)&=\mu(hfI_A)\\&=\lim\limits_{n\rightarrow\infty}\mu(h_nfI_A)\\&=\lim\limits_{n\rightarrow\infty}(h_n)(f\mu)(A)\\&=(h)(f\mu)(A)\end{align*}$$
>
>Now let $h\in m\mathcal{F}$ and express it as $h=h^+-h^-$ where $h^+,h^-\in m\mathcal{F}^+$. By linearity, 
>$$\begin{align*}
>(hf)(\mu)&=\mu(f(h^+-h^-)I_A)\\
>&=(h^+)(f\mu)(A)-(h^-)(f\mu)(A)\\
>&=(h)(f\mu)(A)
>\end{align*}$$


**Fact 2**
$h\in L^1(\mathbb{S},\mathcal{F},\mu)$ if and only if $fh\in L^(\mathbb{S},\mathcal{F},\mu)$ and then $(f\mu)(h)=\mu(fh)$.

>[!Proof]
>Something here.

## Restricted Measure

Let $D\in \mathcal{F}$. Then $\mathcal{F}_D=\{A\in\mathcal{F}:A\subset D\}$ is a $\sigma$-algebra *over* $D$. We denote $\mu_D$ as the *restriction of* $\mu$ to $(D,\mathcal{F}_D)$. Using Fact 1, we can express integrals with respect to $\mu_D$ in terms of the original measure $\mu$.

If $f$ is a function defined on $\mathbb{S}$, then $f{\bf{1}}_{D}$ is the restriction to $D$. Observe $\mu(f{\bf{1}}_D)=\mu_D(f_D)$. Using the notation from above, this is
$$(I_D\mu)(h)=\mu_D(h_D)$$
The expression $\mu(f1_D)$ is a fancy way of denoting $\int_D f\;\mathrm{d}\mu$. We can also denote it as $\mu(f;D)$.