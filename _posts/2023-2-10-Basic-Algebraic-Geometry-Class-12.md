---
layout:     post   				                    # 使用的布局（不需要改）
title:      Basic Algebraic Geometry Class 12		# 标题 
subtitle:   Projective varieties
date:       2022-2-10 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt8.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Commutative Algebra
    - Notes
---

### Projective varieties

We learnt about projective algebraic sets, studied its topological properties, like what we did with affine varieties. Our goal in this note is to define a nice ringed space structure on projective varieties, making them into prevarieties. Then we will study its properties. It includes defining the structure sheaf on a projective variety thus making it into a prevariety, and show that the prevariety is separated, and study its properties.

The difficulty is that, for affine varieties we just have to deal with polynomial functions, however with projective varieties, we are forced to deal with a special kind of polynomials, i.e. the homogeneous polynomials, which form a graded ring, with graded ideals. A homogeneous polynomial or a quotient of homogeneous polynomials does not provide well defined functions on a subset of $\mathbb{P}^{n}$. To be more specific, a homogeneous polynomial function (in $\mathbb{A}^{n+1}$) satisfies
$$
f(\lambda x) = \lambda^{d} f(x), \quad \lambda \in k,
$$
but $\lambda x$ is identified with $x$ in the projective space! Thus the function $f(x)$, though well-defined in $\mathbb{A}^{n+1}$, is not single-valued in the projective space. Or consider $\mathbb{P}^{n}$ as the space of lines in $\mathbb{A}^{n+1}$, then a well-defined function in projective space would be, in the plus one dimensional affine space, a function well-defined on lines, and homogeneous functions are not.

The way out of the problem is to find a way to cancel the factor $\lambda^{d}$. This factor is universal for all homogeneous polynomials of degree $d$, thus we can cancel it by not focusing on the polynomials themselves, but quotients of them. For that purpose, we introduce regular functions.

### Regular functions

Let $U$ be an open set of a projective algebraic set $X$. We will denote the coordinate ring on $X$ by $S(X)$, and denote the homogenous polynomials in $S(X)$ by $S(X)_ {d}$.

A `regular function` on $U$ is a map 
$$
\phi: U\to k
$$
such that for any $a\in U$ there is an open neighborhood $U_ {a}\subset U$ of $a$ and *homogenous* polynomials $f,g\in S(X)_ {d}$ such that 
$$
\phi(x) = \frac{g(x)}{f(x)}, \quad f\neq 0
$$
for all $x \in U_ {a}$.

Now $\phi(\lambda x) = \phi(x)$, so $\phi$ is well defined on the equivalence classes $x\sim \lambda x$. 

We denote the set of regular functions on $U$ by $\mathcal{O}_ {X}(U)$.

The functor $\mathcal{O}_ {X}$ is a sheaf of $k$-algebra on $U$. We call it the `structure sheaf` of $X$.

Let $X = V_ {p}(J) \subset\mathbb{P}^{n}$ be an algebraic set. The claim is that if you remove from $X$ the set where some coordinate is zero $V(X_ {i})$, all such sets $U_ {i} = X-V(X_ {i})$ is an open cover of $X$. Thus the ringed space $X$ is a prevariety. It is not a variety yet since we have not shown it is separated.

### Morphisms defined by homogeneous polynomials

Now we have shown that projective, algebraic sets are prevarieties, we'd like to define morphisms between them. 

First let us look at morphisms between homogeneous polynomials. Again let $X$ be an projective algebraic set. The claim is that, if 
$$
f_{0},\dots,f_ {m} \in  \mathcal{S}(X)_ {d}
$$
are $m+1$ regular functions on $X$, then 
$$
f: X - V(f_{0},\dots,f_ {m}) \to\mathbb{P}^{m},\quad x\mapsto[f_{0}(x): \dots : f_ {m}(x)]
$$
is a morphism of prevarieties.

This map is well defined since, first, none of the $f_0,\dots,f_ {m}$ is zero; second, it maps $x$ and $\lambda x$ to the same point, thus it is truly a map from a line to a line. 

To show $f$ is a morphism, it suffices to prove it locally, namely on an open cover, thanks to the gluing property. To simplify notations define
$$
W := X - V(f_{0},\dots,f_ {m})
$$
and the open cover $W_ {i}$ of $W$, where
$$
W_ {i} := \left\{ x \in W \,\middle\vert\, f_ {i}(x)\neq 0 \right\} .
$$
Using this open cover one can show that $f$ is indeed a morphism. 

As an example, consider the projective automorphisms of $\mathbb{P}^{n}$. Let $A$ be invertible $(n+1)\times(n+1)$ matrices. It can be regarded as a automorphism 
$$
A: \mathbb{P}^{n} \to \mathbb{P}^{n},\quad  x\mapsto Ax,
$$
where $x$ is a row vector of $n$ elements, with the equivalence relation $x\sim \lambda x$. 

### The Segre embedding

In this section we will talk about the embedding of the product of two projective varieties into a higher dimensional variety. For affine spaces it is much simpler, for the product of two affine spaces of dimension $m$ and $n$ is just the affine space of dimension $m+n$. For projective varieties, due to the homogeneous polynomial quotient property, it is more difficult. 

We will embed $\mathbb{P}^{m}\times\mathbb{P}^{n}$ as a subvariety of $\mathbb{P}^{N}$ with
$$
N = (m+1)\times (n+1) -1
$$
with coordinates $[z_ {0,0},\dots,z_ {m,n}]$ via
$$
f: ([x_{0},\dots,x_ {m}] , [y_{0},\dots,y_ {n}]) \mapsto [x_ {0}y_{0},\dots,x_ {m}y_ {n}].
$$

**Proposition.** The map $f$ is an isomorphism onto 
$$
V_ {p}(z_ {i,j}z_ {k,l}-z_ {i,l}z_ {j,k}).
$$
To show that, just show that the map is both surjective and injective. 

The map $f$ is called the `Segre embedding`. The coordinates $z_ {i,j}$ are called the `Segre coordinates` on $\mathbb{P}^{m}\times\mathbb{P}^{n}$.

One special example of this is the map
$$
\mathbb{P}^{1}\times \mathbb{P}^{1}\to\mathbb{P}^{2}.
$$
In coordinates the map takes 
$$
([x_{0}: x_{1}],[y_{0}: y_{1}]) \mapsto [x_{0}y_{0}:x_{0}y_{1}: x_{1}y_{0}: x_{1}y_{1}].
$$

This helps to show that projective prevarieties are separated, thus they are varieties. We will leave that to another class.