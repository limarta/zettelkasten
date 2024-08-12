---
tags:
  - inverse
  - linear_algebra
---
## Schur's Complement

Schur's complement the blocks of a matrix $A$ to the blocks of the inverse $A^{-1}$. Suppose we can express a matrix $M$ as
$$M=\begin{bmatrix}A & B\\
C & D\end{bmatrix}$$
Then the *Schur's Complement* is defined as $M\backslash A=D-CA^{-1}B$. Similarly $M\backslash D=A-BD^{-1}C$.
## Inverses
Given the block matrix $M$ above and it's inverse
$$M^{-1}=\begin{bmatrix}E&F\\G&H\end{bmatrix}$$it is not necessarily true that $A^{-1}=E$ as $E$ is dependent on each block of $M$. Instead, it turns out that $E=(M\backslash D)^{-1}$. More generally given the Schur's complement $M\backslash D$,
$$M^{-1}=\begin{bmatrix}
(M\backslash D)^{-1} & -(M\backslash D)^{-1}BD^{-1}\\
-D^{-1}C(M\backslash D)^{-1} &D^{-1}+D^{-1}C(M\backslash D)^{-1}BD^{-1}
\end{bmatrix}$$

>[!Note] Schur's Complement viewed as Gaussian Elimination
>Something here.