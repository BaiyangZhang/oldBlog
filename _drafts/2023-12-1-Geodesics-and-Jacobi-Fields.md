---
layout:     post   				    # 使用的布局（不需要改）
title:     Geodesics and Jacobi Fields			# 标题 
subtitle:   Note on Theodore Frankel
date:       2023-3-19 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt12.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

Let $\mathbf{x}: U\subset \mathbb{R}^{2} \to M$ be a map of a rectangle in $\mathbb{R}^{2}$ into the n-dimensional manifold $M$. We call this map a parametrized surface, or just surface, even though we don't ask the induced map $\mathbf{x}_ {\ast}$ to have rank 2 yet. 

A smooth map $\mathbf{v}: U\subset\mathbb{R}^{2} \to TM$ that assigns to each point $(u,v)\in U$ a tangent vector $\mathbf{v}(u,v)$ to $M$ at $\mathbf{x}(u,v)$ will be called a `vector field along the surface` $\mathbf{x}$. Note that the vectors $\mathbf{v}(u,v)$ in general are not tangent to the surface $\mathbf{x}$, instead they live in the tangent vector space of the n-dimensional manifold $M$. Of course we have 
$$
\left[ \frac{ \partial  }{ \partial u } ,\frac{ \partial  }{ \partial v }  \right]=0
$$
on $M$, but in general we can not talk of the commutator
$$
\left[ \frac{ \partial \mathbf{x} }{ \partial u } ,\frac{ \partial \mathbf{x} }{ \partial v }  \right]
$$
since the two entries in the bracket are not vector fields on $M$, they are only defined along the surface $\mathbf{x}$, not defined everywhere in $M$. If they were, then *when the torsion is zero*, the Lie derivative can be written in terms of covariant derivatives. But in our case, we can still connect the Lie algebra and covariant derivative, but only along the surface. The following is an important computational tool.

**Theorem 1.** Let $\mathbf{x}$ be a surface in $M$ with a symmetric connection. Then we have, as vector fields along the surface,
$$
\nabla_ {u} \left( \frac{ \partial \mathbf{x} }{ \partial v }  \right) = \nabla_ {v} \left( \frac{ \partial \mathbf{x} }{ \partial u }  \right).
$$
Another theorem connects the covariant derivative with the curvature,

**Theorem 2.** If $\mathbf{w}$ is a vector field defined along the surface, we have
$$
\nabla_ {u}\nabla_ {v} \mathbf{w} - (u \leftrightarrow v) = R\left( \frac{ \partial \mathbf{x} }{ \partial u } ,\frac{ \partial \mathbf{x} }{ \partial v }  \right) \mathbf{w}.
$$
### Jacobi Fields

Let $C$ now be a geodesic, and let us vary $C$ by curves $C_ {\alpha}$, where each $C_ {\alpha}$ is itself a geodesic, parameterized by a parameter $s$ that is proportional to arc length. The best example to keep in mind is probably the family of great circles on the round 2-sphere all passing through the north pole.

Now we want to talk about the `separation` between two geodesics $C$ and $C_ {\alpha}$ by following the two geodesics by the unit speed. The separation is given by the difference between $x(s,\alpha)$ and $x(s,\alpha=0)$. 

Let us use the notation 
$$
\mathbf{T}=\frac{ \partial \mathbf{x}(s,\alpha) }{ \partial s } 
$$
for the tangents to the geodesics along the curves and 
$$
\mathbf{J} = \frac{ \partial \mathbf{x}(s,\alpha) }{ \partial \alpha }
$$
for the` variation vectors`. They are vector fields along the surface of variation. The `Jacobi's equation of geodesic variation` is the differential equation satisfied by the variation vector field $\mathbf{J}$. It makes use of the fact that geodesics satisfy $\nabla_ {s} T=0$, then from $\nabla_ {\alpha}\nabla_ {s}T=0$ we have
$$
\nabla^{2}_ {s} \mathbf{T} + R(\mathbf{J},\mathbf{T})(\mathbf{T})=0.
$$
Any field $\mathbf{J}$ along a geodesic $C$ that satisfies the above equation will be called a `Jacobi field` along $C$.

