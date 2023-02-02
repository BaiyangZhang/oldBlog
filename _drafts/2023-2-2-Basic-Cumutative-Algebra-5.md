---
layout:     post   				                    # 使用的布局（不需要改）
title:      Basic Commutative Algebra Class 5		# 标题 
subtitle:   Zariski Topology
date:       2023-2-2 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt1.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Commutative Algebra
    - Notes
---

### Zariski Topology

Rings are purely algebraic structures, it was to my surprise that, in a very direct manner, we can endow it with topological structures, called Zariski topology. This has a feeling of unity of algebra and geometry, with topology represents the geometry side. It makes people wonder why is it possible to define a topology on rings so naturally... The answer I do not know, let me know if you have any ideas.  

First, an overview of the ideal of topological space. Given a set $X$, we want to introduce a geometric structure on $X$ by defining what the it means for a subset to be `closed` and `open`. Namely we classify all the subsets of $X$ into two categories, open and closed. They don't have to me mutual exclusive, a subset can be both open and closed, contrary to people's common sense, such sets are sometimes called clopen but I seldom see living human being ever utter that word. No need to make the terminology more complicated than it already is.

A topology on $X$ is a collection $\mathcal{T}$ of the subsets of $X$ called `closed` subsets, such that the following holds:
1. The empty set $\emptyset$ and whole set $X$ are closed, 
2. `finite` unions of closed sets are closed,
3. `arbitrary` (meaning finite and infinite) intersections of closed sets are closed.

The reason why we require **finite** unions of closed sets to be closed, rather than arbitrary unions, is that infinite unions of closed sets may be open. Take $\mathbb{R}$ for example, Let the topology on $\mathbb{R}$ be the usual topology, for example $(1,2)$ is a open set and $[1,2]$ is closed. However, the infinite union of closed sets
$$
\bigcap_{n\to \infty}\left[ 1+\frac{1}{n},2-\frac{1}{n} \right],\quad n\in \mathbb{N}
$$
is nothing but the open set $(1,2)$.

The set $X$ with topology $\mathcal{T}$ is called a `topological space`. It is a quite weak (or should I say abstract) sense of "space", since there is not necessarily the concept of distance, or metric. If the topology is clear from the contest you just say that $X$ is a topological space, without mentioning $\mathcal{T}$ explicitly. 

A set $U$ is called an open set if its complement, denoted by $X-U$ (or $X \backslash U$ ) is closed.   

This is how you define topology in terms of closed sets. More often the topology is defined by specifying which sets are open. Then the condition also changes from "finite union, arbitrary intersection" for closed sets to "finite intersection, arbitrary union" for open sets.

Once we have defined which sets are open, we can define which maps are `continuous.` A continuous map is a map between two topological spaces such that the pre-image of any closed sets is closed, equivalently (convince yourself of it) the pre-image of any open sets is open. 

Then we can further define `homeomorphism` (note the spelling is different from homomorphism in, for example, group theory). A homeomorphism is a continuous map with continuous inverse. By the way, there is a nice article online discussing the difference and connection between homeomorphism and homomorphism, sadly I am too lazy to put the link here, interested readers can google it. 

Whenever you need examples for these definitions, just think of $\mathbb{R}$ with usual topology. 

- - -

Now let's come back to algebraic sets and try to endow it with a topological structure. There are two ways to define the topology, one geometric and one algebraic. We will start with the geometric one.

**Proposition.** Let $X\subset \mathbb{A}^{n}$ ($\mathbb{A}$ for affine) be an `algebraic set` and $\mathcal{T}$ to be the collection of all `algebraic subsets` of $X$, then $\mathcal{T}$ is a topology of $X$ and $\mathcal{T}$ is the set of closed sets. 

In other words, a subset $U\subseteq X$ is closed if $U$ itself is algebraic, that is if $U$ is the variety of some ideals of $I(X)$, where $I(X)$ is the coordinate ring of $X$, namely the ring of non-zero polynomial functions on $X$.

The empty set $\emptyset$ is algebraic since it is the variety of $I(X)$ itself, the entire set $X$ is also algebraic since it is the variety of the zero element of $I(X)$. The union of algebraic sets are algebraic since 
$$
\bigcup_{i}V(I_{i}) = V\left( \prod_{i} I_{i} \right)
$$
and the intersection of algebraic sets are algebraic since
$$
\bigcap_{i} V(I_{i}) = V\left( \sum_{i}I_{i} \right).
$$

I'll leave the distinction between "arbitrary" and "finite" to readers.

This topology is called the `Zariski topology`.

From now on, when we talk about topology of an algebraic set, we would always assume Zariski topology, unless stated otherwise. 

Note that Zariski Topology is very different from the usual topology of $\mathbb{R}^{n}$ or $\mathbb{C}^{n}$, where open sets are open balls. For example, consider the complex plane $\mathbb{C}$ with usual metric topology where open sets are open balls
$$
\{ z\in \mathbb{C} \mid \left\lVert z \right\rVert  <1 \} 
$$

However, this open ball is **not Zariski open** for if it were, its complement must be closed, namely its complement must be the variety of some ideal of $\mathbb{C}[z]$, which is not true. Hence the open ball is not Zariski open. In this sense, the usual topology on $\mathbb{C}$ is **finer** than Zariski topology, meaning roughly with more open sets.

- - -

### Connectedness and Irreducibility

The definition of connectedness is quite intuitive: if a set can be written as the disjoint union of two proper subsets, then it is said to be disconnected, otherwise it is said to be connected. To be more specific,

**Definition.** Let $X$ be a topological space. If $X=X_{1} \sqcup X_{2}$ , where $\sqcup$ is the disjoint union and both $X_{1}$ and $X_{2}$ are closed (=algebraic) proper subsets of $X$, then $X$ is said to be `disconnected`, otherwise $X$ is said to be `connected`.

For example, if you put two entirely irrelevant varieties together, let there be no intersection or superposition, and consider then as one big variety, then it is clearly less interesting than to study the individual varieties separately. Thus connected varieties are more interesting to us, since otherwise we can separate the variety into connected parts and study them separately.

Another related yet different concept is reducibility. 

**Definition.** Let $X$ be a topological space and $X_{1},X_{2}$ be two `closed`, `proper` subsets, not necessarily disjoint. If $X=X_{1}\cup X_{2}$ then $X$ is said to be `reducible`. Otherwise it is said to be `irreducible`. 

Think about the difference between connectedness and irreducibility. 

Obviously, irreducibility implies connected but the converse is not true. As an example, consider Zariski topology and $V(xy)$. It is connected but reducible.

Zariski topology is a weird topology, with some uncommon properties. To start with, Zariski topology is `coarse`, meaning it has very few open or closed sets. Consider Zariski topology on the real affine line $\mathbb{A}^{1}$, the closed sets are the zero loci of polynomials in one variable. But every polynomial has but finite zeros, thus the closed sets comprises of finite point, it is a finite set. Then the open sets are the whole affine line with finite points removed. Similarly for a complex line $\mathbb{C}$. 

The problem is that, the definition of `neighborhood` of a point depends on the open sets. So, when taking the neighborhood of a point on $\mathbb{C}$, keep in mind that the open sets are the entire complex plane with finite points removed. Thus given two points on $\mathbb{C}$, you can't find two disjoint neighborhoods of these two points. Then, by definition, $\mathbb{C}$ with Zariski topology is not s Hausdorff space. Recall that in a Hausdorff space, two points, no matter how close they are to each other, can be separated by two **disjoint** open sets.

Another consequence of Zariski topology is that, the affine line $\mathbb{A}$ (or $\mathbb{C}$ in that matter) is not reducible, since a line is not the union of finite points.

Yet another consequence of Zariski topology is that, in any irreducible space $X$, every proper open subset of $X$ is `dense`. Recall that a proper subset $Y\subset X$ is dense in $X$ means the close of $Y$ is $X$.

- - -

We have told the geometric side of the story. On the algebraic side, we talk about the ideals. Let's start with the algebraic view on connectedness.

**Proposition.** If $X$ is a 

