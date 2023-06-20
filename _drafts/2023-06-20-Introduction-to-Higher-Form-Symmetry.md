---
layout:     post   				    # 使用的布局（不需要改）
title:     Introduction to Higher Form Symmetry 			# 标题 
subtitle:   Lecture 2
date:       2023-06-20 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/lib16.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - PureMath
    - CategoryTheory
    - Notes
---

### Ordinary symmetries

Before going to the generalized symmetries, let's first review some aspects of ordinary symmetries in quantum field theory (QFT).

Noether theorem says that each continuous, physical symmetry (physical symmetry, as opposed to nonphysical symmetry, such as gauge symmetry) gives rise to a conserved current. The derivation of Noether current is most familiar to every physicist, so I won't waste time to derive it here. The traditional, or standard way to obtain it is to follow the below given steps.
1. The action is invariant under an *infinitesimal, continuous, global* transformation. However it doesn't mean the the Lagrangian has to be strictly invariant under the same transformation, it can still vary by a total derivative, since its contribution is a surface terms, and for most theoretical setups, everything is set to be zero at the boundary of space time, so the surface terms contributes nothing. 
2. Substitute the varied Lagrangian into the action, with the help of various mathematical tools, such as integral by part, etc., we can extract the variation of the actions that is proportional to the variation of the fields, which must be identically zero, since the field variation is arbitrary. Along the process the *equation of motion* must be applied. 
3. Eventually we arrived at the conserved current $\partial_ {\mu}J^{\mu}=0$. 

An particularly clever way to derive the Noether current is to *gauge* the global symmetry. By gauging something it is meant that making some global symmetry local, for example, the wavefunction has a global symmetry $\psi\to e^{ i\theta }\psi$, where $\theta$ is a constant, hence this transformation is global; we can gauge this transformation by making $\theta$ position-dependent, namely $\psi\to e^{ i\theta(x) }\psi$. Gauging a symmetry is the same thing as gauging a transformation, we will use them interchangeably. The gauging method to derive the Noether current works as follows.
1. Under the infinitesimal global symmetry transformation $\phi\to \phi+\epsilon \phi$, the action is still invariant, $S\to S$. Now we gauge $\epsilon$, making it spacetime-dependent, $\epsilon\to\epsilon(x)$.
2. Under a gauged symmetry transformation, the action will receive extra contribution coming from the derivative of $\epsilon$, at the leading order this contribution should be proportional to (linear in) $\partial_ {\mu}\epsilon(x)$, that is $\delta S =\int \, J^{\mu}\partial_ {\mu}\epsilon(x)$. Here $J^{\mu}$ is just the proportional coefficient, and the upper index $\mu$ is needed to contract with the lower index $\mu$ in $\partial_ {\mu}$. 
3. Now let us take the field configuration to be a physical one, that is, the configuration satisfies the equation of motion. Such configurations has an crucial advantage: it is a saddle point, any field variation about it will leave the action invariant, including the before defined gauged symmetry transformation. Thus we have something like $\delta S = \int  \, J^{\mu}\partial_ {\mu}\epsilon(x)=0$. Apply the integral by part and neglect the surface term, we arrive at $\partial_ {\mu}J^{\mu}=0$, we have found the conserved current $J^{\mu}$!

I just like to mention some of my own philosophical understandings about the connection between a symmetry transformation and conserved current, feel free to skip this paragraph. They are like the two sides of the same coin, but what is this coin? A conserved quantity *shows certain blindness to the physical system*, *the incompetent of identifying the situation*. For example, conservation of energy means that the total energy is the same at any minute, so we can not use the total energy to identify time, as a clock. Interesting enough, the corresponding symmetry transformation, namely the time translation, has the same effect, it says that we can perform our experiment at any time, as long as it is the same experiment then we will get the same results, we are blind to the time at which the experiment is performed. In mathematics, we meet various obstructions to do things, for example it is the case in homology, and things become more interesting when such obstructions are present, maybe here it is similar, the conserved current, or symmetry transformation, can be regarded as a obstruction of identifying certain property of the physical system, for instance, the pair (time translation symmetry, energy conservation) is an obstruction for us to use it to tell the time of a system, simply because it is not time-dependent; the pair (space translation symmetry, momentum conservation) both suggests the blindness to the absolute position. But this picture also has lots of shortcomings, for example we not only have a conserved quantity but a conserved current, the latter is a stronger condition, it says that the way the conserved quantity moves is actually continuous, it can not just disappear somewhere and at the same second re-appear somewhere else, in other words the causality is preserved, I don't know how to fit the importance of conserved currents into the "obstruction" language. Anyway, it is interesting to think of symmetry this way.

- - -

The conserved charge is given by 
$$
\text{Charge} = \int _ {M} \, \text{charge density} 
$$