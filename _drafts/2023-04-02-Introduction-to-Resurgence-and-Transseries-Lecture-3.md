---
layout:     post   				    # 使用的布局（不需要改）
title:     Introduction to Resurgence and Transseries 			# 标题 
subtitle:   Lecture 3
date:       2023-04-02 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt10.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - PureMath
    - CategoryTheory
    - Notes
---

### The differential algebra


It will be convenient for us to set $z = 1/t$ in order to “work at $\infty$” rather than at the origin, since we will often talk about compactified spaces. This means that we shall deal with expansions involving *non-positive* integer powers of the indeterminate. We denote the set of all the `formal power series`, i.e., polynomials in $1 / z$ by 
$$
\mathbb{C}[\![z^{-1}]\!] = \left\{ \phi=\sum_ {n\geq 0}a_ {n}z^{-n} \,\middle\vert\, a_ {i} \in \mathbb{C} \right\}.
$$
This is a vector space with basis $1, z^{-1},z^{-2}$, etc. It is also an algebra when we take into account the Cauchy product
$$
\left( \sum a_ {n}z^{-n} \right) \left( \sum b_ {n} z^{-n} \right) = \sum c_ {n} z^{-n}, \quad  c_ {n} = \sum_ {p+q=n} a_ {p} b_ {q}.
$$

The derivation
$$
\partial  = \frac{d}{d z}
$$
further makes it a *differential algebra*, which simply means $\partial$ is a linear map which satisfied the Leibniz rules. 

This is the derivative in terms of $z$, it is natural to ask what is the derivative in terms of $t$. The answer is straightforward, 
$$
\partial  = \frac{d}{d z} = \frac{d}{d t^{-1}}  = \frac{d}{-t^{-2}dt} =-t^{2} \frac{d}{d t} .
$$
Then, in mathematical terminology, there is an isomorphism of differential algebra between $(\mathbb{C}[\![z^{-1}]\!],\partial)$ and $(\mathbb{C}[\![t]\!],\partial)$. 

- - -

It turns out that 