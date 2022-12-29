---
layout:     post   				    # 使用的布局（不需要改）
title:     Holonomic and Nonholonomic Constraints			# 标题 
subtitle:   
date:       2022-12-12 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt3.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Duality
    - QFT
    - Notes
---

### The Frobenius nonholonomic constraints

Given a **smooth nonvanishing** vector field in $\mathbb{R}^{3}$, one can always find a smooth family of integral curves, that is, a family of curves that are 1) **non-intersecting** and 2) **always tangent to the given vector field**. 

What about instead of vector field, one is given a family of 2-planes $\Delta$ in $\mathbb{R}^{3}$? At every point, instead a vector, now we have an infinitesimal 2 dimensional plane. Can we always find a family of surfaces, call it the integral surfaces, which are non-intersecting and everywhere tangent to $\Delta$? 

Suppose we can. Let $C:t\mapsto x(t)$ be a parametrized curve that is transverse to the family of supposed integral planes everywhere, as shown in the figure below. As can be seen, at each $t$ the curve $C$ is perpendicular to the integral plane. Then, at least locally, we can always define a function $f(\mathbf{x})$ such that its level surfaces are the integral surfaces, that is, the level surface given by $f=t$ consists of the supposed integral surface that is pierced by $C(t)$ at time $t$.

![integralSurface](img/fig61.png)

Then the normal vector of the integral domain must be parallel to $\nabla f(\mathbf{x})$. Write $\mathbf{n}=\lambda(x)\nabla f$ for some function $\lambda$. In Cartesian coordinates, there is a simple connection between vector and covector, we can write the **normal covector** $\nu$ from the normal vector, 
$$
\nu:= \lambda df = n_{i} dx^{i}.
$$
The derivative of $\nu$ is 
$$
d \nu = d(\lambda)\wedge df = \left( \frac{1}{\lambda}d\lambda \right)\wedge (\lambda df)=d\ln \lambda \wedge \nu,
$$
in short words we have $d\nu=(\text{sth})\wedge\nu$ itself. Then we have **Euler's integrability condition**, if such integral plane exists then 
$$
\boxed{
\nu \wedge d\nu=0,\quad \text{i.e. } \mathbf{n}\cdot \text{curl }\mathbf{n} =0.
}
$$

This condition is a necessary condition for the integral surface to exist.

The trick here is that, when dealing with 2-surfaces, it is usually (I dare not say *always*) simpler to consider the normal vectors.

As a trivial example, consider the case where $d\nu=0$. Locally we can always find a $\beta$ such that $\nu=d g$, in the language of vectors it would be $\nabla \times \mathbf{v}=0 \implies \mathbf{v}=\nabla g$. The normal vector is perpendicular to the surface $g=\text{const}$.

As a counter example, consider the planes $\Delta$ normal to the vector 
$$
\mathbf{n} = y\partial_{x}-x\partial_{y} +z\partial_{z}
$$
where $\partial_{x,y,z}$ are the vector basis. Direct computation shows that 
$$
d\nu = d(ydx-xdy+zdz) = -2dx\wedge dy,\quad \nu d\nu=-2z dx\wedge dy\wedge dz\neq 0,
$$
the Euler's integrability condition is not satisfied, there can't be integral surfaces.

- - -

Consider the normal vector $\mathbf{n} = y\partial_{x}-x\partial_{y} +\partial_{z}$, *classically* the infinitesimal plane that is orthogonal to this vector at point $(x_{0},y_{0},z_{0})$ is given by the collection of the infinitesimal vectors that are perpendicular to $\mathbf{n}$, define
$$\mathbf{A}=(x-x_{0},y-y_{0},z-z_{0})\equiv (a_{1},a_{2},a_{3}), $$
then $\Delta$ is given by the condition 
$$
\mathbf{A} \cdot \mathbf{n}(x_{0},y_{0},z_{0})=0
$$
which is sometimes written as 
$$
ydx-xdy+dz=0
$$
where $dx,dy,dz$ are now infinitesimal incrementations instead of the basis of differential forms.

Now, let us regard $\nu=ydx-xdy+dz$ **as a 1-form**.

**Definition.** The collection of all the planes given by vectors $\mathbf{A}$ such that
$$
i_{\mathbf{A}}\nu=0
$$
is called the distribution associated to the 1-form $\nu$. 

This is not to be confused with the generalized functions also called distributions.

In general in $\mathbb{R}^{3}$ one would describe a family of planes by writing 
$$
\nu=P_{1}dx^{1}+P_{2}dx^{2}+P_{3}dx^{3} = 0
$$
where $P_{1,2,3}$ are smooth function, thus $\nu$ can be seen as a smooth 1-form field. To find the integral surfaces is to find the solution of the above equation. Such a plane can be parametrized by two variable $s:(u^{1},u^{2})\mapsto\mathbf{x}(u^{1},u^{2})$, the equation becomes
$$
\left\langle \nu, \frac{ \partial \mathbf{x} }{ \partial \mathbf{u} } d\mathbf{u} \right\rangle =\nu_{i} \frac{ \partial x^{i} }{ \partial u^{j} }  u^{j}=0 \text{ for all }u^{j},
$$
we can pullback $\nu$ to the $\left\{ u^{I} \right\}$ coordinate system and claim that $s^{\ast}\nu=0$. We have seen that $\nu \wedge d\nu$ is a necessary condition for $s^{\ast}\nu=0$ to have a 1-parameter family of solutions. We will show that it is also a sufficient condition. 

Before we go further it is convenient to introduce the definitions of $k$-distribution and $k$-integral manifold,

**Definition.** A **$k$-dimensional distribution** $\Delta_{k}$ on $M^{n}$ assigns in a smooth fashion to each $x \in M^{n}$ a $k$-dimensional subspace $\Delta_{k}$ of the tangent space to $M^{n}$. An **$r$-dimensional integral manifold** of $\Delta_{k}$ is a $r$-dimensional submanifold of $M$ such that it is tangent to $\Delta_{k}$ everywhere. The $k$-distribution $\Delta_{k}$ is said to be **(completely) integrable** if locally there are coordinates $x^{1},\dots,x^k,y^{1},\dots,y^{n-k}$ for $M$ such that the **coordinate slices** $y^{1}=\text{const},\dots,y^{n-k}=\text{const}$ are $k$-dimensional integral manifolds of $\Delta_{k}$. Such a coordinate system $\left\{ x,y \right\}$ will be called a **Frobenius chart** for M.

Roughly speaking, a $k$-dimensional distribution $\Delta_{k}$ is a smooth field of $k$-dimensional subspace of the tangent space.

**The fundamental question is, when is $\Delta_{k}$ integrable?**

- - -

Suppose we are given a distribution $\Delta_{k}$, and a pair of vector fields $X$ and $Y$ such that at every point in an open set $X,Y\in\Delta_{k}$. Suppose $\Delta_{k}$ is integrable, then both $X$ and $Y$ are tangent to the integral manifold, since $\Delta_{k}$ itself is tangent to the integral manifold. Then, some theorem tells us that the Lie bracket $[X,Y]$ is also in the distribution. We can denote this symbolically by 
$$
boxed{
[\Delta,\Delta]\subset \Delta.
}\tag{1}
$$

**We will see that this condition is also sufficient for showing integrability.**

- - -

Let $\theta \in\Omega^{1}(x)$ be a non-zero $1$-form at $x$, $\theta$ defines a special vector basis $X$ by $\left\langle \theta,X \right\rangle=1$. All the other vector basis such that $\left\langle \theta,V \right\rangle=0$ expand a $n-1$ dimensional subspace of $n$-dimensional manifold $M$, called the `annihilator` or `null space` of $\theta$ at $x$. In other words, the null space of $\theta$ at $x$ is expanded by the vectors $V$ such that $\left\langle \theta,V \right\rangle=0$. Classically one writes $\theta=0$ for this null space. When discussing distributions it is common to call a 1-form $\theta$ a `Pfaffian`, $\theta=0$ is called the `Pfaffian equation`.

Let $\theta_{1},\dots,\theta_{r}$ be $r$ linear independent $1$-forms at each point of an open subset of $M$, being linear independent means that $\theta_{1}\wedge\dots \wedge\theta_{r}\neq {0}$. The second you see the words "open subset" you should realized that we are talking about local properties and might not hold globally. Anyway, with given $\theta_{1},\dots,\theta_{r}$, each of them has an associated null space, the intersection of all the null spaces form a $k=n-r$ dimensional vector space, which is also a distribution since it is smooth, which follows from the smoothness of the $1$-forms. Call this distribution $\Delta_{k}$ as before, we have
$$
X\in \Delta_{k} \quad\text{ iff }\quad \theta_{1}(X) = \theta_{2}(X) = \dots=0.
$$

We may again write this distribution as $\theta_{1}=\dots=\theta_{r}=0$. Note that **we do not claim that every distribution can be globally defined by $r$ Pfaffians.**

**Definition.** If the distribution $\Delta$ is closed under Lie brackets, $[\Delta,\Delta]\subset\Delta$, then $\Delta$ is said to be in `involution`.

**If a distribution is integrable, then it is in involution.**

Interesting enough, since the year 2020, *involution* has taken Chinese media by storm, especially among younger people. Translated as "内卷", it implies the growing feeling that the struggle to succeed is futile in conditions of economic precarity and structural unfairness. But it is another topic for another time.


