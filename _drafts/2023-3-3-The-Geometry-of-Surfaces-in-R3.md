---
layout:     post   				    # 使用的布局（不需要改）
title:     The Geometry of Surfaces			# 标题 
subtitle:   Theodore Frankel
date:       2023-3-3 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/lib2.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*


### Fundamental Forms, the First and Second

Let $M^{2}\subset \mathbb{R}^{3}$ be a 2D surface in 3D space, $M^{2} = F(U)$ where $U$ is a subset of $\mathbb{R}^{2}$ and $F_ {\ast}$ is a map of rank two. Denote the coordinates of $U$ as $u_{1}=u,u_{2}=v$.

A curve on $M^{2}$ is denoted by $x(t) = x(u(t))$, where $u(t)$ is a curve on $U\subset \mathbb{R}^{2}$. The basis vectors for the tangent space on $M^{2}$ at each point can be inherited from the basis vector of $U$, by defining
$$
X_ {\alpha} := \frac{ \partial x }{ \partial u^{\alpha} }.
$$
We can then introduce the metric tensor
$$
g_ {\alpha \beta}=\left\langle X_ {\alpha},X_ {\beta} \right\rangle
$$
and use it to calculate the inner product of any pair of vectors,
$$
ds^{2} = \left\langle dx,dx \right\rangle =g_ {\alpha \beta}du^{\alpha}du^{\beta}.
$$
This quadratic form associated to the metric tensor is called the `first fundamental form`. Note that here we are considering $u^{\alpha}$ and $u^{\beta}$ as functions on $U$ and $du^{\alpha,\beta}$ are 1-forms, not infinitesimals. Thus $ds^{2}$ is a tensor, 
$$
ds^{2} = g_ {\alpha \beta} \;du^{\alpha}\otimes du^{\beta}.
$$

Consider the sphere of radius $a$ which can be parametrized by colatitude $\theta$ and the longitude $\phi$. We then have 
$$
ds^{2}=a^{2}(d\theta^{2}+\sin ^{2}\theta d\phi^{2}).
$$

Once we know the metric, we can evaluate the total length of a curve, the angle between two vectors, etc.

For *element of area*, we state without proof that 
$$
ds = \sqrt{ g }du\wedge dv.
$$

- - -

We would like to make a remark on how to look at $d\mathbf{x}$, which is short for $dx^{i}$ with $i$ takes value in $1,2,3$. Here $\mathbf{x}$ is supposed to denote a vector, hence the bold font. Classically, $d\mathbf{x}$ is considered as an infinitesimal displacement, or infinitesimal vector. Let $\mathbf{x}$ be a *position vector* (so we are **not** talking about affine space) starting from the origin and end at some point on $M^{2}$, which is a surface in $\mathbb{R}^{3}$, then $\mathbf{x}+d\mathbf{x}$ gives us another vector, whose endpoint is $d\mathbf{x}$ away from $\mathbf{x}$, and $d\mathbf{x}$ is a infinitesimal vector which lies in the tangent plane at $\mathbf{x}$. 

However, in our language, $d\mathbf{x}$ is mixed tensor. Let $u^{I},I=\{1,2\}$ be the local coordinates. It means that, see the surface in $\mathbb{R}^{3}$ as the image of mapping $F(U)$ where $U$ is the subset of $\mathbb{R}^{2}$, then $u^{I}$ is the flat coordinates of $\mathbb{R}^{2}$. Then 
$$
d\mathbf{x} = \mathbf{x_ {i}} \otimes du^{i}, \quad   \mathbf{x}_ {i}=\frac{ \partial \mathbf{x} }{ \partial u^{i} } .
$$
The vector $\mathbf{x}_ {i}$ is the (components of) induced vector in $\mathbb{R}^{3}$ by $\partial / \partial u^{i}$ in $U$. Classically the tensor product sign is omitted. We shall think of the mixed tensor as a `vector valued 1-form`, that is, a 1-form whose value on any tangent vector $\mathbf{v}\in TU$ is a vector, rather than a scalar. For this particular vector valued 1-form, we have 
$$
d\mathbf{x}(v) = \mathbf{x_ {i}} \otimes du^{i}(v) = \mathbf{x_ {i}} v^{i} = {\mathbf{\widetilde{v}}}
$$
where $\widetilde{v}$ is the image of $\mathbf{v}\in TU$ which is a vector in $\mathbb{R}^{3}$.

- - -
**The second fundamental form**

Whenever we discuss the normal to a surface we shall assume that one of the two possible local normal fields has been chosen.

Let 
$$
\mathbf{N} = \frac{\mathbf{x}_ {u} \times \mathbf{x}_ {v}}{\left\lvert \mathbf{x}_ {u} \times \mathbf{x}_ {v} \right\rvert }
$$
be the unit normal to $M^{2}$ at a point $(u^{1},u^{2})$. Given any tangent vector $\mathbf{X}$ at the same point, let $u^{\alpha}(t)$ be a curve on $M^{2}$ having $\mathbf{X}$ as tangent at $u(0)$; $du(t) / dt = \mathbf{X}$. Then, since $\mathbf{N}$ is a unit vector, the derivative of it is tangent to $T_ {(u^{1},u^{2})}(M^{2})$. Then
$$
\frac{d}{dt} \mathbf{N} = \frac{ \partial \mathbf{N} }{ \partial u^{i} } \frac{du^{i}}{dt} =: \mathbf{N}_ {i} \frac{du^{i}}{dt} = \mathbf{N}_ {i} \mathbf{X}^{i}.
$$
The assignment (The minus sign being conventional)
$$
\mathbf{X} \mapsto - \mathbf{N}_ {i} \mathbf{X}^{i} =: b(\mathbf{X})
$$
defines a linear transformation
$$
b: TM^{2} \to TM^{2}.
$$

Its matrix form $b^{\alpha}\, _{\beta}$  in the basis $\mathbf{x}_ {\alpha}$ works as 
$$
b(\mathbf{x}_ {\beta}) = \mathbf{x}_ {\alpha} b^{\alpha} _ {\beta} = -\mathbf{N}_ {\beta}.
$$
These are called the `Weingarten equations`.

The bilinear form $B$ associated to $b$ is given by
$$
B(X,Y) = \left\langle X,b(Y) \right\rangle,
$$
as a tensor, $B$ is given by the `second fundamental form`
$$
-\left\langle d\mathbf{x},d\mathbf{N} \right\rangle =-\left\langle \mathbf{x}_ {\alpha},\mathbf{N}_ {\beta} \right\rangle du^{\alpha}\otimes du^{\beta} .
$$

After some derivation we find that, along a curve $u(t)$, the change of the normal vector is given by the second fundamental form 
$$
\frac{d\mathbf{N}}{dt} = -\mathbf{x}_ {\alpha} b^{\alpha}_ {\beta} \left( \frac{du^{\beta}}{dt} \right).
$$
For example, if $b=0$ then $d\mathbf{N} / dt=0$, the space is flat.

We may write for the second fundamental form 
$$
B = b_ {\alpha \beta}du^{\alpha}du^{\beta}
$$
where 
$$
b_ {\alpha \beta}=g_ {\alpha \gamma}b^{\gamma}_ {\beta}.
$$
We shall exhibit a more useful form to calculate $b_ {\alpha \beta}$. Put
$$
\mathbf{x}_ {\alpha \beta} := \frac{ \partial ^2\mathbf{x} }{ \partial u^{\alpha}\partial u^{\beta} }.
$$
Since $\mathbf{N}$ is normal thus $\mathbf{x}_ {\alpha} \cdot \mathbf{N}=0$, and 
$$
0= \frac{ \partial  }{ \partial u^{\beta} } \left\langle \mathbf{x}_ {\alpha},\mathbf{N} \right\rangle = \left\langle \mathbf{x}_ {\alpha \beta},\mathbf{N} \right\rangle+\left\langle \mathbf{x}_ {\alpha},\mathbf{N}_ {\beta} \right\rangle   =\left\langle \mathbf{x}_ {\alpha \beta},\mathbf{N} \right\rangle -b_ {\alpha \beta},
$$
that is, 
$$
\boxed{
\left\langle \mathbf{x}_ {\alpha \beta},\mathbf{N} \right\rangle = b_ {\alpha \beta}
}
$$
which is the formular to calculate $b_ {\alpha \beta}$. We can also see that $b_ {\alpha \beta}$ is symmetric w.r.t. $\alpha$ and $\beta$, which means $B$ as a bilinear form is self-adjoint, of which we will say more next.


### Gaussian and Mean Curvature

**Symmetry and Self-Adjointness**

In general, let $\hat{a}$ be an operator, then the `adjoint` of $\hat{a}$, denoted $\hat{a}^\ast$, is another operator defined by 
$$
\left\langle X,\hat{a}Y \right\rangle =\left\langle \hat{a}^\ast X,Y \right\rangle .
$$
If $\hat{a}=\hat{a}^\ast$ then $\hat{a}$ is said to be `self-adjoint`. In terms of bilinear form $A$ associated with $\hat{a}$, $A$ is self-adjoint provided
$$
A(X,Y) = \left\langle X,\hat{a}Y \right\rangle  = \left\langle \hat{a}X,Y \right\rangle = \left\langle Y,\hat{a}X \right\rangle  = A(Y,X).
$$
That is, **the linear transformation (operator) $\hat{a}$ is self-adjoint iff the associated bilinear form $A$ is symmetric.** 

Note that when we say $A$ is symmetric, in terms of coordinates we are saying $A_ {\alpha \beta}=A_ {\beta \alpha}$, note the position of the indices! They must all be downstairs, or up-stairs, it doesn't matter, as long as they are at the same position! It doesn't make sense to say that two indices at different positions are symmetric or not. The reason is that, *only when the two indices are both up-stairs or down-stairs, then their symmetry is independent of the choice of basis*.

