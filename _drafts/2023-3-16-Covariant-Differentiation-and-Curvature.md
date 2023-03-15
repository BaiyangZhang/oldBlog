---
layout:     post   				    # 使用的布局（不需要改）
title:     Covariant Differentiation and Curvature			# 标题 
subtitle:   
date:       2023-12-1 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/lib1.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

Consider a surface $M^{2}$ in $\mathbb{R}^{3}$. We then define a `covariant derivative` as follows. Let $\mathbf{v}$ be a tangent field defined in the neighborhood of a point $p$. Let $\mathbf{X}$ be a tangent vector defined at $p$. The covariant derivative is defined by 
$$
\nabla_ {\mathbf{X}}\mathbf{v} = \mathbf{X}(\mathbf{v})+\Gamma^{\alpha}_ {\beta \gamma} \mathbf{X}^{\beta} \mathbf{v}^{\gamma}\; \partial _ {\alpha}.
$$

We have thus constructed the notion of a derivative of a tangent vector field $\mathbf{v}$ with respect to a vector $\mathbf{X}$ at $p$. The result is again a tangent vector at $p$. It is furthermore clear that if $\mathbf{X}$ is itself a tangent vector field, then $\nabla_ {\mathbf{X}}\mathbf{v}$ is again a vector field. 