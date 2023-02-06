---
layout:     post   				                    # 使用的布局（不需要改）
title:      Basic Commutative Algebra Class 9		# 标题 
subtitle:   Dimension 
date:       2023-2-6 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt5.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Commutative Algebra
    - Notes
---

### Dimension

Our goal here is to extend the notion of dimension from vector spaces, to affine varieties that fits into our intuition.  We will also study dimension globally and locally, and try to express dimension algebraically.

One way to think about dimension in vector space is to study the inclusion relation. For example, given $\mathbb{R}^{3}$, the smallest "subspace" is a point, the next smallest subspace containing a point is a line, then a plane, then $\mathbb{R}^{3}$ itself. This is an approach we can adopt for varieties.

**Definition.** The `dimension` $\text{dim }X$ of a Noetherian topological space $X$ is the `supremum` of all $n$ having a chain
$$
X_{0}\subsetneq X_{1}\subsetneq\dots\subsetneq X_{n}\subsetneq X
$$
of non-empty `irreducible` `closed` subspaces of $X$.

Note that we are talking about Zariski topology here.

The `codimension` $\text{codim }_ {X}Y$ of a non-empty irreducible subspace $Y$ in $X$ is the supremum of all $n$ with a chain
$$
Y\subset X_{0}\subsetneq\dots\subsetneq X_{n} \subsetneq X
$$
of irreducible closed subsets of $X$. 

For example, a point is closed in Zariski topology. Let $X$ be a point, then the dimension of $X$ is zero since you can't find another closed space containing it. The dimension of a line is one since 
$$
\text{point} \subsetneq \text{line}
$$
and terminates at the line. 

As an interesting exercise, reader can think about the dimension of a plane pierced by a ling. In $\mathbb{A}^{3}$ the variety $V(X_{1},X_{2})$ is the $X_{3}$ axis, namely a straight line, and the variety $V(T_{3})$ is the $X_{1}\times X_{2}$ plane, think about the dimension of the union of these two varieties and the codimension of some points on it. 

**Definition.** A noetherian topological space is said to have `pure dimension n` if each irreducible component has dimension $n$. 

An affine variety is said to be a curve if it has pure dimension $1$, a plane if pure dimension is $2$, a hypersurface if it is of pure codimension $1$.

Note that there exists infinite-dimensional noetherian topological spaces (but not varieties). 

- - -

We have talked about dimension of noetherian topological spaces, the approach is rather geometric. Next we would like to study dimension algebraically. Recall that an irreducible variety is given by a prime ideal, or put it in other words, the coordinate ring of an irreducible variety is a prime ideal. This motivates the following definition.

**Definition.** The `Krull dimension`, $\text{dim }R$ of a ring $R$ is the supremum of all $n$ with a chain
$$
P_{0}\subsetneq P_{1}\subsetneq\dots \subsetneq P_ {n}
$$
of prime ideals in $R$.

The `codimension` of a prime ideal $P$ in $R$, sometimes called the `height` of $P$, denoted $\text{codim}_ {R}P$, is the supremum of all $n$ with a chain
$$
P_{0}\subsetneq P_{1}\subsetneq\dots \subsetneq P_ {n}\subset P
$$
of prime ideals contained in $P$.

For example, fields all have dimension $0$ since the only prime ideal fields have is the trivial ideal $0$. Principal ideal domains (PIDs) have dimension $1$.

- - -

Now, having introduced the dimension from both geometric and algebraic side, it would be sad if they don't agree with each other. Thankfully they do, thanks to the $1:1$ correspondence between irreducible varieties and prime ideals.

