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