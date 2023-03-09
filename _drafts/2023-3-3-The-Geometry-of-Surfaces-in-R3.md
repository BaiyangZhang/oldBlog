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
The assignment 
$$
\mathbf{X} \mapsto 
$$