---
layout:     post   				    # 使用的布局（不需要改）
title:     Fibre Bundles			# 标题 
subtitle:   
date:       2023-1-14 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt7.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - FibreBundle
    - Notes
---

*Disclaimer: Nothing in this note is original.*

### Tangent and Cotangent Bundles

For a didactic point of view, it is helpful to first look at some examples of fibre bundles before dive in the abstract definitions. The bundle of tangent spaces provides a good starting point.

Let $M$ be a smooth $n$-dimensional manifold and $T_{x}M$ be the tangent space at point $x\in M$. Define the set $TM$ to be the collection of all tangent spaces at all points of $M$, 
$$
TM:=\bigcup_{x\in M} T_{x}M
$$
i.e. all vectors at all points $x\in M$ are regarded as points of a new set $TM$. Conceptively we "glued" a tangent space to every point of $M$, thus constructed a new geometric object, where each "point" is a vector in some tangent space. We have a `canonical projection`
$$
\pi:TM\to M,\quad v\in T_{x}M \mapsto x
$$
that maps a vector in $T_{x}M$ to its point of tangency $x\in M$. Say the coordinates of $x$ in a chart $U\subset M$ is given by $(x^{i},i=1,\dots,n)$, then the vector basis of $T_{x}M$ is given by $n$ basis $\partial_{j}\equiv \partial / \partial x^{j}, j=1,\dots,n$. Thus to define a point in $TM$ we need $2n$ coordinates. From here it is straightforward to find how the coordinate of a point in $TM$ changes under a change of coordinates.

In a very similar way we can glue to each point $x$ of $M$ the cotangent space of that point $T^{\ast}_{x}M$, the collection of all `cotangent spaces` is denoted
$$
T^{\ast }M:= \bigcup_{x\in M} T_{x}^{\ast }M.
$$
An element of the cotangent space is a $1$-form in basis $dx^{i},i=1,\dots,n$. Just like for tangent spaces, we can also define the `canonical projection`. 

- - -

We first defined a manifold $M$, then glued to each point $x\in M$ some geometric object, such as tangent or cotangent vector space, then collected them together and regard it altogether as a new geometric object, which has some nice properties, for example we have smoothness, and we know how to write down the coordinates of a points in this new geometric object. It is the general idea of fibre bundles. Our previous examples represent part of structures called the `tangent bundle` or `cotangent bundle`. 

Generally speaking, we can paste at each point $x \in M$ another manifold $F_{x}$, at different point we could have different "pasted" manifold, but they should all be diffeomorphic to a common manifold $F$, i.e. for $x,y\in M$ we require $F_{x}\cong F_{y}\cong F$. The manifold $F$ is called a `typical fibre` or just a `fibre` for short. $F_{x}$ is called a `fibre over a point` $x$. $M$ is called the `base`, or `base space`, or `base manifold`. The entire thing is called the `total space` $E$, 
$$
E:= \bigcup_{x\in M}F_{x}.
$$

There is a projection that maps elements in $F_{x}$ to $x$. It is easy to see that $\pi$ is surjective. $\pi$ is called the `canonical projection`, or just `projection` map. The fibre over $x$ can also be denoted by 
$$
F_{x} = \pi^{-1}(x).
$$
$F_{x}$ are required to be a `submanifold` in $E$, so it is to be nicely placed in $E$. 

Thanks to the smoothness of the fibre bundle, we can always find a chart $U$ on $M$ containing $x$ that is small enough so that $\pi^{-1}(U)$ is a simple direct product of $F$ and $U$, since nothing interesting can be happening with the fibers over $U$, since $U$ is too small. Thus we have `local product structure`: there exists a covering $\mathcal{O}_{\alpha}$ of the base $M$ and a system of diffeomorphism 
$$
\psi_{\alpha}:\pi^{-1} (\mathcal{O}_{\alpha})\to \mathcal{O}_{\alpha}\times F.
$$
This is the so-called `local trivialization` of the fiber bundle. We can think of local trivialization as something like coordinate system, just like a coordinate system of some manifold $N$ is a 1-2-1 map from $N\to \mathbb{R}^{n}$, the local trivialization is a 1-2-1 map between (part of) the fiber bundle and a product space $\mathcal{O}\times F$, where $F$ is the typical fiber. 

There also exists a Lie group $G$ called the `structure group`, which acts on $F$ **on the left**. For example, if $F$ is $\mathbb{R}$, the structure group could be the group of translation.

In geometry we can usually "glue" together simple pieces to construct a more complicated object, the simple pieces are usually topologically trivial while the global object has some nontrivial topological properties. For example we can glue two rectangles together to make a Mobius strip. Here we can do the same, the thing we glue together is the fibre. The "gluing" operation is realized by `transition functions`.  Note that $\psi^{-1}_{x}$, namely the trivialization with the base point $x$ fixed, is a map from $F_{x}\to F$, mapping a point on the   Given two charts $U_{\alpha},U_{\beta}$ both containing $x$, there exists a transition function $t_{\alpha \beta}$ such that $t_{\alpha \beta}F_{x}$






All of these elements, when taken together, constitute a structure called a `fibre bundle`, also `fibered manifold` or just a $bundle$ for short. 

