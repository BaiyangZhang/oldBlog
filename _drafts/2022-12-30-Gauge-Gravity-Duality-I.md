---
layout:     post   				    # 使用的布局（不需要改）
title:     Note on gauge/gravity duality I			# 标题 
subtitle:   
date:       2023-1-8 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt5.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - PureMath
    - duality
    - Notes
---

This note is mostly meant for myself, thus the content is not organized in a pedagogical fashion. Furthermore, the note originates from the book *Gauge/Gravity Duality* by Martin Ammon and Johanna Erdmenger, interested readers should refer to the original work.

### Preliminary

The energy-momentum tensor we got from Noether's flow derivation $T^{\mu \nu}$ may not be symmetric in $\mu$ and $\nu$. We can achieve the symmetry by adding to the original $T^{\mu \nu}$ a total derivative. The symmetric energy-momentum tensor is the `Belinfante` or `canonical` energy-momentum tensor.

Given a classical theory, we can in general quantize it in two ways, i) canonical quantization and ii) path integral quantization. Canonical quantization is mathematically clearer maybe, just like in quantum mechanic, we upgrade the c-numbers to q-numbers and bestow on them certain commutation relation. Where do we get the commutation relations from? Dirac was inspired by Poisson bracket, but why that works? I am not sure. Maybe it is because the map from quantum theory to classical theory somehow preserves the relation between conjugate variables somehow... Anyway, once we have the commutation relations, we can work out scattering amplitudes, things like that. Although the mathematical operation is more or less clear to us, the physical meaning of canonical quantization is quite obscure, at least to me. To be honest anything dubbed with "canonical", may it be physics or religion, are more or less incomprehensible to me. By incomprehensible I mean that, take religion for example, I claim to understand the conviction of the believers but actually never fully experienced it my self, so I really shouldn't say I understand it. 

In contrast, the path integral is mathematically quite messy, the functional integral may not even be mathematically well defined, and we invented a lot of remedies on the fly. To name a few, if some mathematician says that the path integral does not converge, then we say, OK, let's replace $m^{2}$ with $m^{2}-i\epsilon$ and set $\epsilon$ to zero at the final step. The measure is not well defined? Who cares, we just focus on the saddle points! Richard Borcherds, from the mathematical point of few, said that he is trying to understand path integral, if even a Fields medal  laureate considers it hard to understand, who am I to say anything different. However, the physics idea behind all the messy mathematics is strikingly intuitive, the path integral is closely related to the statistical nature of quantum field theory. Instead of path integral quantization, maybe it is more suitable to call it statistical quantization. Just like in quantum mechanics, what could happen in principal all has a contribution in the final result, in QFT all the possible field configurations are supposed to be considered and has its own contribution to the final result, in many times results in a deviation from the classical result, dubbed the quantum effects.

In the following we will go to more details. 

Given a scalar field, we can add to the Lagrangian density (which we will just call Lagrangian for short) a source term *by hand*, the source term can be used to generate correlation functions and are in general set to zero at the end of the calculation. Forget about the possible interactions, consider a free theory to start with, if we integrate out the scalar field $\phi$, we get the propagating connecting two source terms. The propagator is also a Green's function for the equation of motion (EOM).









