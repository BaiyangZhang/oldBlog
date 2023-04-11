---
layout:     post   				        # 使用的布局（不需要改）
title:      Confinement in Toy Models 	# 标题 
subtitle:   Lecture 3      # 副标题
date:       2023-04-11			        # 时间
author:     Baiyang Zhang 				# 作者
header-img: img/mathArt118.jpg 	        # 这篇文章标题背景图片
catalog: true 						    # 是否归档
tags:								    # 标签
    - math
    - quantum field theory
    - confinement
---

### The dual description of 3D gauge field

In 3D spacetime, a photon, if considered as a oscillating electromagnetic field, has only one direction of oscillation thus only one physics degree of freedom, thus can be descried using a scalar field. That's the rough idea. In the following we will talk about the dual fields of electromagnetic fields in 3D, IR, SU(2) field. 

Remember that in our theoretical construction the $W$ bosons are too heavy thus decouples from the model, we are left with an abelian $U(1)$ gauge field $A_ {\mu}$, and possibly a light Higgs boson, if $\lambda$ is considered small. Focus on the pure Yang-Mills part of the Lagrangian, we have 
$$
\mathcal{L}_ {\text{eff}} = \int d^{3}x \,  \frac{1}{4g^{2}}F^{2}+\dots.
$$
Now consider the path integral. To find the partition function we need to path-integral over all the fields, over their physically inequivalent configurations. In our case we have 
$$
Z = \int_ {A / G} \mathcal{D}A_ {\mu}\mathcal{D}\dots \, e^{ iS[\mathbf{A}..] }.
$$
where $G$ is the gauge transformation. However, here we can regard the field strength $F = dA$ as the degree of freedom, and do the path integral in terms of 
$$
Z = \int \mathcal{D}F\dots \, e^{ iS[F, \dots] }.
$$
On the one hand, a merit of trading $A$ for $F$ is that, the gauge redundancy is automatically taken care of, since two gauge fields differ by a gauge transformation $A \sim A' = A+dg, g\in G$ yields the same field strength $F$. On the other hand, the Bianchi identity $dF = ddA\equiv 0$ is not automatically  satisfied anymore. We have traded one redundancy for another! 

The solution to that problem is to force the Bianchi identity via a Lagrange multiplier, which is a scalar field in our case, denoted by $\sigma(x)$. In 3D Minkowski spacetime with metric $g=(+,-,-)$, the action reads
$$
S[F_ {\mu \nu},\sigma] = -\frac{1}{4g^{2}}\int d^{3}x \,  F_ {\mu \nu}F^{\mu \nu}- \frac{1}{8\pi}\int d^{3}x \,  \partial _ {\mu}\sigma F_ {\nu \lambda}\epsilon^{\mu \nu \lambda}
$$
where the integral by parts has been performed. If we integrate over $\sigma(x)$ first we restore the Bianchi identity for $F$ thus the original theory. 

**However, we could also choose to integrate over $F$ first**, leaving as a theory in terms of $\sigma(x)$. Solve the equation of motion for $F$ we get
$$
F_ {\mu \nu} = -\frac{g^{2}}{4\pi}\epsilon^{\mu \nu \lambda}F_ {\nu \lambda}
$$
and substitute it back to the action we have 
$$
\boxed{
S[\sigma] =  \frac{g^{2}}{16\pi^{2}}\int d^{3}x \, (\partial \sigma) ^{2}.
}
$$
We will call $\sigma$ the `dual photon field` and the action the `magnetic description` or `dual description`, the use of magnetic in the calling will become clear in the future.

