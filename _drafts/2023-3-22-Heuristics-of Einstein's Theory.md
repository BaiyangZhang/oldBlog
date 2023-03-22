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

In case 1, the potential $\phi$ satisfies a field equation, namely Poisson's equation. 