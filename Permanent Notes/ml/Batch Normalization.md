---
tags:
  - ML
  - training
---

Batch normalization normalizes mini-batches.

## Internal Covariate Shift
Training changes the weights of each layer, which in turn changes the *distribution* of their outputs. This makes it hard to learn.
-  [[Covariate Shift]] usually refers to the a change in the input distribution as a whole system, but it can apply to individual layers as described here. [^1]

## Solving Internal Covariate Shift
Whitening (zero mean, unit variance) helps the network train faster. Do this for *every* layer.

The optimizer (e.g. SGD, etc) must be aware of these parameters too.

## Normalization via Mini-Batch Shift
Full whitening is costly. It requires computing
- Covariance matrix $\Lambda$
- $\Lambda^{-1/2}$
- Derivatives of $\Lambda^{-1/2}(x-E[x])$

Instead of jointly normalizing all features, we do so independently. This does mean that the features are not necessarily decorrelated.

For $x\in \mathbb{R}^d$, the normalization of *dimension* $k$ is 
$$\hat{x}^{(k)}=\frac{x^{(k)}-E[x^{(k)}]}{\sqrt{\text{Var}[x^{(k)}]}}$$

In general, normalization can affect what the output distribution looks like on each layer. To capture to identity, batch normalization adds two additional learned parameters $\gamma^{(k)}$ and $\beta^{(k)}$. The final activation is
$$y^{(k)}=\gamma^{(k)}\hat{x}^{(k)}+\beta^{(k)}$$
>[!question]- For what assignment of $\gamma^{(d)}$ and $\beta^{(d)}$ gives the identity?
>$\gamma^{(d)}=\text{Var}[x^{(k)}]$ and $\beta^{(k)}=E[x^{(k)}]$

**Input**: Values of $x$ over a mini-batch: $\mathcal{B}={x_{1\ldots m}}$ ; Parameters to be learned: $\gamma$, $\beta$
**Output**: $\{y_i=\text{BN}_{\gamma, \beta}(x_i)\}$
$$
\mu_\mathcal{B}\leftarrow\frac{1}{m}\sum\limits_{i=1}^m x_i
$$
$$\sigma_\mathcal{B}^2\leftarrow\frac{1}{m}\sum_{i=1}^m (x_i-\mu_\mathcal{B})^2$$
$$\hat{x}_i\leftarrow \frac{x_i-\mu_\mathcal{B}}{\sqrt{\sigma_\mathcal{B}^2+\epsilon}}$$
$$y_i\leftarrow \gamma \hat x_i + \beta\equiv \text{BN}_{\gamma,\beta}(x_i)$$
>[!danger]
>Q: Why don't we use the unbiased estimator for the variance?

>[!note] 
>Batch normalization doesn't just depend on $x_i$. It depends on $x_i$ *and* the other examples in the training batch.

The parameters $\gamma$ and $\beta$ are learned by taking the gradient of the loss with respect to them. We have
$$\frac{\partial \ell}{\partial \hat x_i}=\frac{\partial \ell}{\partial y_i}\gamma$$
$$\frac{\partial \ell}{\partial \sigma_\beta^2}=-\sum\limits_{i=1}^m \frac{1}{2}\frac{\partial \ell}{\partial \hat x_i}(x_i-\mu_\beta)(\sigma_\beta^2+\epsilon)^{-3/2}$$
$$\frac{\partial \ell}{\partial \mu_\beta}=-\sum\limits_{i=1}^m \frac{\partial \ell}{\partial \hat x_i}\frac{\partial \hat x_i}{\partial \mu_\beta}+\sum\limits_{i=1}^m\frac{\partial \ell}{\partial \hat x_i}\frac{\partial \hat x_i}{\partial \sigma_\beta^2}\frac{\partial \sigma_\beta^2}{\partial \mu_\beta}\quad(3)$$
$$
\frac{\partial \ell }{\partial x_i}=\frac{\partial \ell}{\partial \hat x_i}\left(\frac{\partial \hat x_i}{\partial x_i}+\frac{\partial \hat x_i}{\partial \sigma_\beta^2}\left(\frac{\partial \sigma_\beta^2}{\partial x_i}+\frac{\partial \sigma_\beta^2}{\partial \mu_\beta}\frac{\partial \mu_\beta}{\partial x_i}\right)+\frac{\partial \mu_\beta}{\partial x_i}\right)\quad (4)$$
$$\frac{\partial \ell}{\partial \gamma}=\sum\limits_{i=1}^m\frac{\partial\ell}{\partial y_i}\hat x_i$$
$$\frac{\partial \ell}{\partial \beta}=\sum\limits_{i=1}^m\frac{\partial \ell}{\partial y_i}$$
## Batched-Normalized Networks - Inference
When doing inference, we do not normalize by the test batch (otherwise the output for a given $x_i$ would be stochastic). Instead, we batch normalize using the *population* statistics $E[x]$ and $\text{Var}(x)$.

## Batch Normalization for CNNs
In general, consider an affine transform $z=g(Wu+b)$ for input $u$. Then 


[^1]: [Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift](https://arxiv.org/pdf/1502.03167)