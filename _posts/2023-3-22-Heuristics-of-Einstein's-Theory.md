---
layout:     post   				    # 使用的布局（不需要改）
title:     Heuristics of Einstein's Theory			# 标题 
subtitle:   
date:       2023-3-22 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/lib2.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

### The Metric Potentials

Einstein assumed that the actual space-time universe is some pseudo-Riemannian manifold $M^{4}$ and is thus a generalization of Minkowski space. We may assume that we have chosen units in which the speed of light is unity when time is measured by the local atomic clocks, rather than the zero-th coordinate $t$. 

We imagine that we have massive objects, such as stars, that are responsible in some way for the preceding metric, and we also have a very small `test body`, a planet, that is so small that it doesn't appreciably affect the metric. We shall assume that the universe is `stationary` in the sense that it is possible to choose the local coordinates so that the metric coefficients do not depend on the coordinate time $t$. We shall also assume that the metric has the further property that the mixed temporal-spatial terms vanish, $g_ {0i}=0$. Such a metric is called a `static metric`. 

Along the world line of the test particle, the planet, we may introduce its proper time parameter $\tau$ by
$$
d\tau^{2} := ds^{2}
$$
or minus $ds^{2}$, depending on the metric convention. Unlike $dt$, $d\tau$ is the really physical quantity, it is assumed that proper time is the time kept by an atomic clock moving with the particle. 

Einstein assumed then that a test body that is subject to no external forces (except the fictitious force of gravity) should have a world line that is a geodesic in the space-time manifold $M$. In the weak gravity limit, the geodesic equation then connects the zero component of the metric $g_ {00}$ with the Newtonian gravitational potential in classical physics. 

In general ,we have the following comparison:
1. Newtonian gravitation is governed by a single potential $\phi$. Newtonian gravitation is a scalar theory.
2. Electromagnetism is governed by a 4-vector potential $A$. Electromagnetism is a vector theory.
3. Einstein 's gravitation is governed by the 10 "metric potentials" $g_ {\mu \nu}$. Gravitation is then a symmetric covariant second-rank tensor theory.

In case 1, the potential $\phi$ satisfies a field equation, namely Poisson's equation
$$
\nabla^{2}\phi = - 4\pi \kappa \rho
$$
where $\kappa$ is the gravitational constant and $\rho$ the density of matter. 

In case 2, in a certain gauge, $A$ satisfies the field equation of the form of a wave equation
$$
\partial _ {\mu}\partial ^{\mu} A = 4\pi J
$$
where $J$ is the source. 

The question is, what are the field equations satisfied by the metric $g_ {\mu \nu}$?

 - - -

For future use, let us first introduce the stress-energy-momentum tensor for fluid. Let $\rho$ be the rest mass-energy density of the fluid and let $u = dx^{\mu} / d\tau$ be the velocity 4-vector of the fluid particles. The `stress-energy-momentum tensor` for the fluid is defined by
$$
T^{ij} := \rho u^{i} u^{j} + p(g^{ij}+u^{i}u^{j})
$$
where $p$ is the pressure.

The `Einstein's equations` reads
$$
R_ {\mu \nu}-\frac{1}{2}g_ {\mu \nu}R = 8\pi \kappa T_ {\mu \nu}.
$$
In this equation we have introduced a second contraction of the Riemann tensor, the `scalar curvature`
$$
R:=g_{\mu \nu}R_ {\mu \nu}.
$$


In order to handle the Einstein equations effectively we shall have to learn more about "tensor analysis," which was developed principally by Christoffel (covariant differentiation, the curvature tensor) and by Ricci.

- - -

We have already defined the covariant derivative of a vector $\nabla \mathbf{v}$, and we also have introduced the `exterior` covariant differential of a vector-valued p-form which gives us a vector-valued $(p+1)$-form. We are now going to define, in a different way, the covariant derivative of a general tensor of type $(p, q)$, the result being a tensor of type $(p, q + 1)$. 

The covariant derivative of a scalar field $f$ is defined to be the differential, $\nabla f = df$. 

We define the covariant derivative $\nabla_ {j}a_ {i}$ of a covector field $a_ {i}$ so that the "Leibniz" rule holds,
$$
\nabla_ {j} a_ {i} = \frac{ \partial a_ {i} }{ \partial x^{j} }  - a_ {j}\omega^{k}_ {ji} 
$$
where $\omega$ is again the general connection.

Finally, we define the covariant derivative of a tensor of type $(p, q)$ by generalizing the above rules.

One can show that this operation does indeed take a tensor field into another whose covariance has been increased by one. Furthermore it has the following two important properties.

1. Covariant differentiation obeys the Leibniz rule.
2. Covariant differentiation commutes with contractions.

- - -

**Riemannian Connections and the Bianchi Identities**

The principal property of the Riemannian connection is that 
$$
\nabla g^{\mu \nu}=0.
$$
We define the divergence of a symmetric contravariant $p$-tensor field $T$ to be the symmetric $(p - 1 )$-tensor
$$
(\text{div } T)^{j_ {2}\dots j_ {p}} = \nabla_ {j_ {1}}T^{j_ {1}j_ {2}\dots j_ {p}}.
$$
