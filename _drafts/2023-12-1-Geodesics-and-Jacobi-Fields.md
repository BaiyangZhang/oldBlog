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
since the two entries in the bracket are not vector fields on $M$, they are only defined along the surface $\mathbf{x}$, not in some bulk of $M$. 