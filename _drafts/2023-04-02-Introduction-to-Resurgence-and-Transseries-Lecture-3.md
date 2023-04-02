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

The `standard valuation`, or sometimes called the `order`, on $\mathbb{C}[\![z^{-1}]\!]$ is the map
$$
\text{val}: \mathbb{C}[\![z^{-1}]\!] \to \mathbb{N} \cup \infty
$$
defined by $\text{val }(0)=\infty$ and 
$$
\boxed{
\text{val }(\phi) := \text{min } \left\{ n\in \mathbb{N} \,\middle\vert\, a_ {n}\neq 0 \right\} ,\quad  \phi =\sum a_ {n} z^{-n} \neq 0.

}
$$

For $\nu \in\mathbb{N}$, we will use the notation 
$$
z^{-\nu}\mathbb{C}[\![z^{-1}]\!] = \left\{ \sum_ {n\geq \nu} a_ {n}z^{-n} \,\middle\vert\, a_ {\nu},a_ {n+1},\dots \in  \mathbb{C} \right\}.
$$

This is the set of all the complex polynomials in $z^{-1}$ such that the standard valuation is no less than $\nu$. 

From the viewpoint of the ring structure, ${\frak I} = z^{-1}\mathbb{C}[\![z^{-1}]\!]$ is the maximal ideal of the ring $\mathbb{C}[\![z^{-1}]\!]$. It is often referred to as the *formal series without constant term*. 

It is obvious that 
$$
\text{val }(\partial \phi) \geq  \text{val }(\phi)+1
$$
with equality iff there is no constant term.

- - -

With the help of the standard valuation, we can introduce the concept of `distance` into the ring of the formal series. Define
$$
d(\phi,\psi) := 2^{-\text{val }(\phi-\psi)},\quad  \phi,\psi \in \mathbb{C}[\![z^{-1}]\!]
$$
as the distance between $\phi$ and $\psi$. It can only take discrete values, such as $1, 1 / 2, 1 / 4,$ etc. 

With the definition of distance, $\mathbb{C}[\![z^{-1}]\!]$ becomes a `complete metric space`. The topology induced by this distance is called the `Krull topology` or the `topology of the formal convergence` (or the ${\frak I}$-adic topology). It provides a simple way of using the language of topology to describe certain algebraic properties.

We mention that a sequence $\phi_ {n}$ of formal series is a Cauchy sequence iff for each $i\in\mathbb{N}$, the $i$-the coefficient is stationary, namely the $i$-th coefficient of $\phi_ {n}$ becomes a constant when $n$ is larger than certain natural number. 

