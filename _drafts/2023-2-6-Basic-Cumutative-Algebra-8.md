---
layout:     post   				                    # 使用的布局（不需要改）
title:      Basic Commutative Algebra Class 8		# 标题 
subtitle:   Integral Ring Extension
date:       2023-2-6 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt4.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Commutative Algebra
    - Notes
---

### Ring extension

First let's review `field extension` as a motivating example. Let $k$ be any field. A field extension $k\subset k'$ is said to be `algebraic` if each $a\in k'$ is algebraic over the original field $k$, i.e. $P(a)=0$ for some polynomial function $P$. We may assume that $P$ is `monic`, meaning it is univariate and the leading coefficient is $1$. A natural consequence is that $k'$ is finite dimensional field extension, just take the field extension $\mathbb{R}\subset \mathbb{C}$ for example.

What about ring extensions? The definition is rather trivial, a ring inclusion $R\subset R'$ is called a `ring extension`, and $R'$ an `extension ring` or $R$. 

Our goal here is to define an study an analogy of algebraicity for ring extensions.

### Integral ring extensions

Let $R\subset R'$ be a ring extension. An element $a\in R'$ is said to be `integral` over $R$ if $P(a)=0$ where $P\in R[T]$ is a monic polynomial with coefficients in $R$. 

If each of $a\in R'$ is integral, we say $R'$ is integral over $R$.

The following example helps to explain the terminology. 

Consider the ring extension $\mathbb{Z}\subset\mathbb{Q}$, where $\mathbb{Q}$ is the set of rational numbers. What are the integral elements in $\mathbb{Q}$? As the name suggests, the integral elements in $\mathbb{Q}$ should be integers, Right? It indeed is true! Assume where $s,t$ are **coprime** integers and $s / t \in\mathbb{Q}$ is the solution of some monic polynomial equation,
$$
\left( \frac{s}{t} \right)^{n}+c_ {n-1}\left( \frac{s}{t} \right)^{n-1}+\dots=0
$$
then
$$
s^{n}=t\times (\text{some integer})\implies t\mid s^{n}
$$
but $s,t$ are coprime, so we must have $t=1$ and $s / t$ is an integer.

The key important thing is that the polynomial has to be **monic**.

### Finiteness and integrality

**Proposition.** The ring $R'$ over $R$ is `finite` if and only if $R'=R[x_{1},\dots,x_{n}]$ where $x_{1},\dots,x_{n}$ are integral over $R$. 

Take $\mathbb{Z}\subset\mathbb{Z}[i]$ where $i^{2}=-1$ for example, $\mathbb{C}=\mathbb{Z}[i]$ where $i$ is integral over $\mathbb{R}$ since $i^{2}+1=0$ is monic.

Another way to say it is that $R'$ is finite over $R$ if $R'$ is a finitely generated $R-$module.
Keep in mind the difference between finitely generated $R$-algebra and $R$-module. For example, $R[x]$ is a finitely generated $R$-algebra whit a single generator $x$, but it is **not** finitely generated as a $R$-module since the basis of the module would be $x,x^{2},x^{3},\dots$

Lets look at one example of integral and non-integral ring extension. Consider $R=\mathbb{C}[T]$, and extend it by introducing another variable $S$, namely $R[S]$, and quotient some vanishing ideal $I[\text{sth}]$. Even after the quotient the resulting ring is still a ring extension. However, depending on the ideal, the ring extension may be integral or non-integral.
- Let $R'= R / (S^{2}-T^{2})$, then $R'$ is integral since $R'=R[S]$ and $S$ is integral over $R$.
- Let $R'=R / (ST-\lambda)$ with $\lambda \in\mathbb{C}$, then $R'$ is not integral since $T$ is in general not invertible.

Some basic properties of ring extension.
- if $R\subset R'$ and $R'\subset R''$ are both integral then so is $R\subset R''$.
- if $R\subset R'$ and $R'\subset R''$ are both finite then so is $R\subset R''$.

### Integral closure and normality

Let $R\subset R'$ be a ring extension. The set $\overline{R}$  of all the integral elements over $R$ in $R'$ is a ring, called the `integral closure` of $R$ in $R'$. 

$\overline{R}$ is a ring because if $a,b\in R'$ are integral over $R$ then $R[a,b]$ is also integral over $R$, then $a\cdot b$ and $a+b$ are integral, hence they form a ring. 

We say that $R$ is `integrally closed` in $R'$ if $R=\overline{R}$.

If $R$ is an integral domain, then we say that $R$ is integrally closed or `normal` if $R$ is integrally closed in its `field of fractions`.

As a trivial example, an integral closure of $R$ is integrally closed in some bigger ring $R'$. 

Unique factorization domains (UFDs) are normal. 

### Prime ideals in ring extension

Let $R\subset R'$ be a ring extension. The question we want to ask is, what are the relations between the prime ideals in $R$ and $R'$? Geometrically, prime ideals corresponds to irreducible varieties, so the question become, what are the properties between the irreducible varieties in $V(R)$ and $V(R')$?

More precisely, we know that
- If $J\subset R$ is an ideal, then $JR'$ is an ideal in $R'$,
- If $J\subset R'$ is an ideal in $R'$, then $J\cap R$ is an ideal in $R$. If $J$ is prime in $R'$ then so is $J\cap R$ in $R$.

The question is, given any ideal in $R$, is there always a bigger ideal in $R'$ such that its intersection with $R$ is the original ideal? Is there only one or multiple such ideals in $R'$?

- - -

