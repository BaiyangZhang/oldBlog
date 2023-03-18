---
layout:     post   				    # 使用的布局（不需要改）
title:     Riemann's Theorem and the Horizontal Distribution			# 标题 
subtitle:   
date:       2023-3-17 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt11.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

Linear algebra tells us that a constant quadratic form $Q = Q_ {ij}dx^{i}dx^{j}$ can always be diagonalized by an orthogonal change of coordinates. We can furthermore make the coordinates orthonormal by scaling. We may say that a constant Riemannian metric can always be reduced to the "flat" or "Euclidean" form. Suppose now that we have a variable Riemannian metric $g_ {ij}(x)$, then we can only make the metric orthonormal **at a single point**, say the origin. We we find a coordinate transformation, nonlinear maybe, to make the metric flat in some neighborhood of the origin? If we can, then the Riemann curvature tensor would be zero in this neighborhood, but Riemann tensor is a tensor, if it is zero in some coordinate system then it must also be zero in other coordinate systems. We shall now discuss all these matters from a more geometrical viewpoint.

### The Horizontal Distribution of an Affine Connection

Here we will make use of the geometric picture of tangent bundle. Recall that a tangent bundle $TM$ to a differential manifold $M$ is, by definition, the collection of all the tangent vectors of all the points of $M$. A point of the new space consists of a pair $(p,\mathbf{v})$. 

Recall that `covariant differential` $\nabla\mathbf{v}$ is a **vector-valued** 1-form given by 
$$
\nabla\mathbf{v} = \partial _ {i} \otimes dx^{j}  \nabla_ {j}v^{i}.
$$
For example, $\nabla v$ acting on a vector $X$ gives
$$
\nabla v(X) = \left\langle \partial _ {i} \otimes dx^{j}  \nabla_ {j}v^{i},X \right\rangle 
= \partial _ {i} \otimes X^{j}\nabla_ {j}v^{i} = \nabla_ {X}\mathbf{v}.
$$
In particular, if $\mathbf{e}$ is any frame of tangent vectors, we have 
$$
\nabla\mathbf{e}_ {j}(\mathbf{e}_ {i})=\nabla_{i}\mathbf{e_ {j}} =\omega^{k}_ {ij}\otimes \mathbf{e}_ {k} ,
$$from which we can construct a vector-valued 1-from 
$$
\mathbf{e}_ {k}\otimes \omega^{k}_ {rj}\sigma^{r}
$$
since
$$
\left\langle \mathbf{e}_ {k}\otimes \omega^{k}_ {rj}\sigma^{r},\mathbf{e}_ {i} \right\rangle =\mathbf{e}_ {k}\otimes \omega^{k}_ {ij},
$$
called the `connection 1-form`. We can write the connection 1-form as 
$$
\omega^{k}_ {\;\; j} = \omega^{k}_ {ij}\sigma^{i}.
$$

In terms of the tangent bundle, the connection 1-form is a form defined on the base manifold $M$. Since there is already a map from $TM$ to $M$, namely the projection map $\pi: TM \to M$, we can talk about the pullback of the connection 1-form by $\pi$. The pull-back of the connection forms $\omega$ on $M$ to $TM$ is given by the same expression as $\omega$ in $M$,
$$
\pi^{\ast }: \omega^{i}_ {\;k} =\omega^{i}_ {jk}dx^{j}\mapsto \omega^{i}_ {jk}dx^{j}\in \Omega^{1}(TM)
$$
where $\Omega^{1}(TM)$ denotes 1-forms defined on $TM$. 

For this reason we shall frequently omit the pull-back symbol $\pi^{\ast}$. 

- - -

Parallel displacement of a vector $\mathbf{v}$ along a parameterized path $C$ in a $n$-dimensional manifold $M$ defines a curve $C'$ in the tangent bundle $TM$ to $M$, parametrized by $(x(t),\mathbf{v}(t))$. Since the parallel displacement requires
$$
\frac{dv^{i}}{dt} + \omega^{i}_ {jk} v^{j} \frac{dx^{k}}{dt} =0,
$$
the lifted curve $C'$ in $TM$ satisfies that the following 1-form in $TM$
$$
\mu^{i} := dv^{i} + \omega^{i}_ {\; k} v^{k}
$$
vanishes when restricted to $C'$,
$$
\left\langle \mu^{i}, \frac{dx^{r}}{dt} \frac{\partial}{\partial x^{r}}+\frac{dv^{r}}{dt} \frac{\partial }{\partial v^{r}} \right\rangle =0.
$$
We write simply 
$$
\mu^{i} = 0
$$
as the equations **describing parallel displacement**.

The Pfaffian equations $\mu^{i}=0,\,i=1,\dots,n$ describes a distribution $H$ in $TM$. Notice that the $n$ $\mu^{i}$s are linear independent since $d\mu^{1}\wedge\dots \wedge d\mu^{n}\neq 0$, thus the Pfaffian kills $n$ dimensions. In the $2n$ dimensional space $TM$, we instead get a $n$ dimensional distribution. Furthermore, since there is a $dv^{i}$ component in $d\mu$, the distribution does not contain $\partial / \partial v^{i}$. $\partial / \partial v^{i}$ are what we call `vertical` vectors, since they are tangent to the fiber $\pi^{-1}(x)$. This implies that the distribution is complementary to the vertical n-planes that are tangent to the fibers. We don't say the distribution is orthogonal to the vertical vectors because there is usually no naturally defined metric on the bundle $TM$, thus it makes no sense to talk of $H$, the distribution as being orthogonal to the fibers. Still, we shall refer to $H$ as the `horizontal distribution`. 

Although the distribution $H$ is given by a local Pfaffian equation in terms of some specific coordinates, in some specific chart, but the distribution have global meaning, since it is after all constructed using parallel displacement. Intuitively, we can glue the horizontal distribution together where two different charts overlap. 

To summarize, a connection for $M$ yields a distribution of $n$-planes $H$ in $TM$, called the horizontal distribution, that is transverse to the fibers. A curve $C'$ in $TM$ represents a parallel displacement, or parallel translation, of some vector $\mathbf{v}$ along a curve $C$ in $M$ if 1) $C'$ is a lift of $C$, meaning that $\pi C'=C$ and 2) $C'$ is tangent to the horizontal distribution. 

**Theorem.** In a Riemannian manifold, one can introduce local coordinates $y$ such that the metric assumes the Euclidean or ''flat'' form
$$
ds^{2} = dy^{i} dy^{i}
$$
iff the curvature vanishes. 

