---
layout:     post   				    # 使用的布局（不需要改）
title:     Introduction to Resurgence and Transseries			# 标题 
subtitle:   Lecture 1
date:       2023-3-20 				# 时间
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

- - -

H. Poincare mentions the so-called "a kind of misunderstanding between geometers and astronomers about the meaning of the word convergence", He proposed a simple example, the two series
$$
\sum \frac{1000^{n}}{n!} \text{ and }\sum \frac{n!}{1000^{n}},
$$
Poincare says that for geometers, namely mathematicians in his time, the first one converges because at large $n$ the terms gets smaller and smaller. But for astronomers the first one is as good as divergent since the next terms doesn't get smaller until $n$ is larger than $1000$. For them the second series diverges because the first $1000$ terms decreases quickly. 

He then proposes to reconcile both points of view by clarifying the role that divergent series (in the sense of geometers) can play in the approximation of certain functions. This is the origin of the modern theory of asymptotic expansion. 

- - -

In this note we shall focus on `formal power series`, such as the Stirling series. Thus the previous example should be written as 
$$
\sum \frac{1000^{n}}{n!}t^{n} \text{ and }\sum \frac{n!}{1000^{n}}t^{n}
$$
where the first one has **infinite** **radius of convergence** while the second one has **zero radius of convergence**. For us, `divergent series` will usually mean a formal power series with zero radius of convergence.

First we will speak of the `Borel-Laplace sumamtion`, which obtains a function from a divergent formal series. The relation between the obtained function and the original power series is an example of `asymptotic expansion of Gevrey type`. We shall also introduce the phenomenon for which J. Ecalle coined the name  `resurgence` at the beginning of the 1980s.

- - -

### An example by Poincare

