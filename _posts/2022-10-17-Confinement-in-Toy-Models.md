---
layout:     post   				        # 使用的布局（不需要改）
title:      Confinement in Toy Models 	    # 标题 
subtitle:   The role of Instantons                   #副标题
date:       2022-10-17 				    # 时间
author:     Baiyang Zhang 				# 作者
header-img: img/mathArt13.jpg 	        #这篇文章标题背景图片
catalog: true 						    # 是否归档
tags:								    #标签
    - math
    - quantum field theory
    - confinement
---

### The abelian Higgs model

The usual way to find the spectrum of a model, once given the Lagrangian, is easy. We write down the Lagrangian in terms of effective degrees of freedom, namely particles, and look for terms that looks like $+\frac{1}{2} m^2 \phi^2$, where $\phi$ is the degree of freedom and $m$ would be the mass. However, the non-perturbative effects, especially instantons, which are soliton solutions living in the Euclidean spacetime, might change that picture entirely. Originally massless particles might develop mass due to instanton induced effects. 

First we look at essentially abelian gauge theory in $1+1$ and $2+1$ dimensions, "essentially" because we also consider the situation where non-abelian symmetries spontaneously are broken to $U(1)$. 

Consider in $1+1$ spacetime the below Lagrangian,
$$
\mathcal{L} = \left\lvert D_{\mu}\phi \right\rvert^2 - \frac{\lambda}{4}(\phi^\ast \phi)^2-\frac{\mu^2}{2}\phi^\ast  \phi-\frac{1}{4e^2}F_{\mu \nu} F^{\mu \nu}.
$$
As for the definition of the covariant derivative, please see the other note I wrote on conventions, which I copied from David Tong's notes. The position of the coupling $e^2$ also follow from his convention. Of course if you like you can absorb $e^2$ to the definition of the gauge field $A^\mu$, which would be the convention preferred in Peskin and Schroeder.

We have a $U(1)$ gauge transformation given by a $U(1)$-valued function $g(x,t)$, for example under the gauge transformation $\phi$ transforms as 
$$
\phi(x,t) \to g(x,t) \phi(x,t).
$$
To have a finite total energy, we can require $g(x,t)\mid_{x=\infty} = 0$. Then, in the eyes of $g(x,t)$, the boundary of space is compactified to one point. For example, supposed the space is a two dimensional plane, then in the eyes of $g$, the boundary of the plane, namely a $\mathbb{S}^1$ is effectively the same as a point for $g(x,t)$ is force to take the same value everywhere on the $\mathbb{S}^1$, then the topology of the space is just $\mathbb{R}^2$ with its boundary compactified to a single point, namely $\mathbb{S}^2$. 

Depending on the sign of $\mu^2$ in the Lagrangian, there are two possibilities. If $\mu^2$ is positive, we have a massive scalar $\phi$ and a massless gauge field $A^\mu$. The interaction is usual Coulomb interaction, except for $1+1$ dimension, where the Gauss's law suggest that the interaction between two charges does not decrease as the distance increases, consequently it costs infinite energy to separate two charges infinite far away, which is called confinement. Note that different people might use different definitions of confinement and sometimes it becomes pointless to discuss whether there exists confinement or not. 

In $1+1$ dimensions there is also no photon. An easy way to see this is to go back to the classical electrodynamics, where photons are electro-magnetic waves vibrating in the transverse direction as opposed to its propagating direction. However in 1-dimensional space there is no such thing as "transverse direction", thus there can be no electro-magnetic wave solutions. This suggests that there is also no photon in $1+1$ dimension. 

The spectrum in $1+1$ dimension consists of bound states of particle-anti-particle pairs, which are stable due to the confinement, and the fact that they cannot decay into pair of photons, for there exists no photon.

For the other case where $\mu^2<0$ the potential takes the shape of a double well in $1+1$ dimension, or a Mexico hat in $2+1$ dimension. The spontaneous symmetry breaking has many consequences,
- the scalar particle has mass $\frac{\mu}{\sqrt{ 2 }}$,
- the gauge boson has mass $\frac{\mu e}{\sqrt{ \lambda }}$.

Since the medium of the interaction is massive, we expect a Yukawa-kind interaction, $V(r) \sim e^{ -r/M }$.

Again, this conclusion is altered by instanton-induced effects.




### Georgi-Glashow Model

