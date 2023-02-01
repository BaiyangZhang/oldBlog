---
layout:     post   				    # 使用的布局（不需要改）
title:     Minkowski Space			# 标题 
subtitle:   
date:       2023-1-17 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt8.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

### Curvature and Special Relativity


Given a curve $C:= \mathbf{x}=\mathbf{x}(t)$ in $\mathbb{R}^{3}$, its tangent vector is a column vector, denoted by $\dot{\mathbf{x}}(t)=(\dot{x},\dot{y},\dot{z})^{T}$. $t$ can be considered as time in physics problems and $\dot{\mathbf{x}}(t)$ would be the velocity. Introduce the arc length $s$ by means of 
$$
\left( \frac{ds}{dt} \right)^{2} = \left\lvert \dot{\mathbf{x}} \right\rvert^{2} = v^{2}, \quad s(t) = \int_{0}^{t} du \, \left\lvert \dot{\mathbf{x}}(t) \right\rvert.
$$

We then have the `unit tangent vector` $T:= d\mathbf{x} / ds=\dot{\mathbf{x}}dt / ds = \mathbf{v} / v$, that is $\mathbf{v}= v\mathbf{T}$. Then the acceleration is given by 
$$
\mathbf{a} = {\dot{v}}\mathbf{T} + v\mathbf{\dot{T}} = \dot{v}\mathbf{T} + v^{2} \frac{d\mathbf{T}}{ds}.
$$
Since $\mathbf{T}$ has constant length, ${d \mathbf{T}} / {ds}$ must be orthogonal to $\mathbf{T}$. The direction of ${d \mathbf{T}} / {ds}$ defines a unique unit vector normal to  the curve called the `principal normal` $\mathbf{n}$,
$$
\frac{d\mathbf{T}}{ds} = \kappa(s) \mathbf{n}(s)
$$
where $\kappa(s)$ is the `curvature` of curve $C$ at $s$. Then the acceleration is 
$$
\mathbf{a} = \dot{v}\mathbf{T} + v^{2}\kappa(s)\mathbf{n}.
$$
The plane spanned by $\mathbf{T}$ and $\mathbf{n}$ is called the `osculating plane`. There is an easy way to compute $\kappa$ in terms of the original parameter $t$ rather than $s$, note that 
$$
\mathbf{v}\times \mathbf{a} = v^{3}\kappa \mathbf{T}\times \mathbf{n},
$$
so 
$$
\kappa = \frac{\left\lvert \mathbf{v}\times \mathbf{a} \right\rvert }{v^{3}}.
$$

We define the `curvature vector` by
$$
\boxed{
\kappa=\frac{d\mathbf{T}}{ds}=\kappa \mathbf{n},
}
$$
note that it is $d\mathbf{T} / ds$ rather than $d\mathbf{T} / dt$.

The curvature $\kappa$ has an intuitive geometric interpretation. Consider three nearby points $\mathbf{x}(s-\epsilon),\mathbf{x}(s),\mathbf{x}(s+\epsilon)$ on a curve $C$. There three points are generically not colinear, and determine a circle. Intuitively speaking, the larger the curvature, the smaller the determined circle. Under mild conditions, it is shown that at $\epsilon\to {0}$ limit, the determined circle lies on the osculating plane and the radius of the circle $\rho(x)=1 / \kappa(s)$ is called the `radius of the curvature` of $C$ at $s$. The accelerator is 
$$
\mathbf{a} = \dot{v}\mathbf{T} + \left( \frac{v^{2}}{\rho} \right)\mathbf{n}.
$$


### Electromagnetism in Minkowski Space




