---
title: Triangulation
---

## Linear Triangulation
### We wish to create a solvable linear system that can give us an initial guess for the 3D position of our feature. To do this, we take all the poses that the feature is seen from to be of known quantity.
### This feature will be triangulated in some anchor camera frame $\{A\}$ which we can arbitrary pick. If the feature $\mathbf{P}_f$ is observed by pose $1\cdots m$ , given the anchor pose $A$, we can have transfromation from any camera pose $C_i,i=1\cdots m$:
####
$$\tilde{\mathbf{x}}_{k|k-1} = \mathbf{\Phi}_{(k,k-1)}~\tilde{\mathbf{x}}_{k-1|k-1} + \mathbf{G}_{k}\mathbf{w}_{k}$$
####
$$\tilde{\mathbf{z}}_{k} = \mathbf{H}_{k}~\tilde{\mathbf{x}}_{k|k-1}+\mathbf{n}_{k}$$
#### where the state contains the inertial navigation state and a single environmental feature 
(noting that we do not include biases to simplify the derivations):
####
$$\mathbf{x}_k =
	\begin{bmatrix}
	{}_G^{I_{k}} \bar{q}{}^{\top}
	& {}^G\mathbf{p}_{{I}_{k}}^{\top}
	& {}^G\mathbf{v}_{{I}_{k}}^{\top}
	& {}^G\mathbf{p}_{f}^{\top}
	\end{bmatrix}^{\top}$$
####
#+BEGIN_NOTE
We use the left quaternion error state 
#+END_NOTE
###
