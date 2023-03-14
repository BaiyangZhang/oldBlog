---
layout:     post   				    # 使用的布局（不需要改）
title:     Covariant Differentiation and Curvature			# 标题 
subtitle:   
date:       2023-3-15 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background2.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

### Covariant Derivative

A covariant differentiation operation, defined fully in a moment, is also called a `connection`. 

The connection in a Riemannian manifold in which the $\Gamma^{i}_ {jk}$ are given by the Christoffel symbols is called the `Levi-Civita connection`. 

It is important that we develop the concept of covariant derivative even when the manifold is not Riemannian. If we differentiate things much more general than merely tangent vector fields, the Christoffel symbol will be replaced by something else. For example, *if we differentiate the wave functions, the Christoffel symbol will be replaced by the gauge connectoin $A$!* In general, the role of Christoffel symbol will be played by various physics fields. But for now, we focus on tangent vector fields $\mathbf{v}$. 

Let $M^{n}$ be a manifold. An affine `connection` or `covariant differentiation` is an operator $\nabla$ that assigns to each pair consisting of a vector $\mathbf{X}$ at $p$ and a vector field $\mathbf{v}$ defined near $p$, a vector $\nabla_ {\mathbf{X}}\mathbf{v}$ at $p$ that satisfies
$$
\nabla _ {\mathbf{x}}(a\mathbf{v}+b\mathbf{w}) = a \nabla _ {\mathbf{x}} \mathbf{v} +b\nabla _ {\mathbf{x}}\mathbf{w},
$$
and 
$$
\nabla _ {a\mathbf{X}+b\mathbf{Y}}(\mathbf{v})=a \nabla _ {X}\mathbf{v} + b\nabla _ {Y}\mathbf{v},
$$
and the Leibniz rule
$$
\nabla _ {X}(f\mathbf{v}) = X(f)\mathbf{v}+f\nabla _ {X}(\mathbf{v}).
$$
We also demand that if $\mathbf{X}$ is a smooth field then $\nabla_ {\mathbf{X}}\mathbf{v}$ is also a smooth vector field.


