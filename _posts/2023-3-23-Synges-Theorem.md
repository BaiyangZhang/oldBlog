---
layout:     post   				    # 使用的布局（不需要改）
title:     Synge's Theorem			# 标题 
subtitle:   
date:       2023-3-23 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/lib3.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

The Gauss-Bonnet connects the local, varying from point to point property, namely the curvature, with the global, topological property, namely the genus. It claims that, for a `closed` surface in $\mathbb{R}^{3}$,
$$
\frac{1}{2\pi}\int _ {M} \, KdS = 2(1-g).
$$

In this brief chapter we will discuss a relation between curvature and the topological notion of simple connectivity, namely the theorem of J. L. Synge, one of the most beautiful results in global differential geometry of the twentieth century. 
![[Pasted image 20230322222151.png]]
In the picture, we have drawn a closed geodesic $C$ on two different surfaces, first on the surface with a negative curvature and second on the surface with a positive curvature. Consider small variation of the geodesics by smooth `closed`curves, then the length functional in the first picture increases and that in the second picture decreases, thus the first geodesic is stable while the second is not. 

**Synge's Formula for Second Variation**

It answers the question that, what does curvature have do with the stability of a geodesic?

I'll save the tedious mathematics and just jump to the conclusion. **In a negatively curved Riemannian manifold , each closed geodesic is stable.**

- - -

### Curvature and Simple Connectivity

**Theorem.** Let $M^{2n}$ be an even-dimensional, orientable manifold with positive sectional curvatures. Then any closed geodesic is unstable, that is, can be shortened by a variation.

This is called the Synge's theorem. 

A corollary says that:

A compact, orientable, even-dimensional manifold with positive sectional curvatures is simply connect.

