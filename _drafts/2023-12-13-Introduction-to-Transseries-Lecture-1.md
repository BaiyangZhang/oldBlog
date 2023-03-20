---
layout:     post   				    # 使用的布局（不需要改）
title:     Introduction to Transseries Lecture 1			# 标题 
subtitle:   
date:       2023-12-12 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt14.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Transseries
    - Notes
---

### Motivation

Because they are super interesting!

But I should maybe say more about it, so that in the future if I were to apply for some research grant, when someone who knows absolutely nothing about resurgence and its application but who decides whether to give me the money, asks me why is this project important, what use does it have and, eventually, why should I give you the money, then I can come back here and just copy the answer. I would say that god knows I have already wasted too much time on grant applications... but thank god I am atheist. 

The following is an incomplete list of the potential applications of resurgence theory.
-   Normal forms for dynamical systems
-   Gauge theory of singular connections
-   Quantization of symplectic and Poisson manifolds
-   Floer homology and Fukaya categories
-   Knot invariants
-   Wall-crossing and stability conditions in algebraic geometry
-   Spectral networks
-   WKB approximation in quantum mechanics
-   **Perturbative expansions in quantum field theory (QFT)**

The most surprising result, at least for me, of resurgence theory in QFT is that one can uncover the non-perturbative results from perturbative expansion alone! Usually to find the non-perturbative results one need to use anything but perturbative results, such as the topology of the vacuum manifold, the homotopy of the solutions to the equation of motion (instanton solutions, etc.), on and on. But resurgence theory lets us to get the non-perturbative results, for instance the contribution of instantons, from analytical continuation of the perturbative results! On the one hand, it is like black magic; on the other hand, I guess I shouldn't be too surprised since if we know all the perturbative expansions then we know everything about the equation of motion, which eventually contains all the non-perturbative results, so in principal the perturbative expansion should be able to generate the non-perturbative results. But that is only in principal. It is still jaw-dropping to see it actually happen.

And I guess it is impossible to make sense out of perturbation theory **without** knowing some of the resurgence theory. After all, is we consider enough terms in perturbative expansion, the power series in coupling actually diverges, so why would it make any sense to just consider the first few terms? Claiming they give the dominant results would also be ridiculous. The answer lies in resurgence theory.

