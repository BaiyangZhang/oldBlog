---
layout:     post   				    # 使用的布局（不需要改）
title:     (Vector) Fibre Bundles			# 标题 
subtitle:   
date:       2023-5-15 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt16.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
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

In geometry we can usually "glue" together simple pieces to construct a more complicated object, the simple pieces are usually topologically trivial while the global object has some nontrivial topological properties. For example we can glue two rectangles together to make a Mobius strip. Here we can do the same, the thing we glue together is the fibre. The "gluing" operation is realized by `transition functions`.  Note that $\psi^{-1}_ {x}$, namely the trivialization with the base point $x$ fixed, is a map from $F_ {x}\to F$, mapping a point on the fiber over $x$ to the "standard" copy of fiber space. 

### Vector Bundles

A (real or complex) vector bundle $E$ of rank $k$ is a $k$-dimensional vector space as fiber over a manifold $M^{n}$. Locally it is a product space of some subset of $M$ and the $k$-dimensional vector space. All fiber bundles are trivial locally so this should not come as a surprise. 

A cross section, or just section, is a map from the base to the fiber bundle 
$$
s: M\to E
$$
such that the range of $p\in M$ is its fiber $\pi^{-1}(p)$, in other words section $s$ must satisfy
$$
\pi\;\circ\;s=\mathbb{1}.
$$

The `frame` of sections $e_ {\alpha}$ are the inverse trivialization $\phi^{-1}(p,\overline{e}_ {\alpha})$ where $\overline{e}_ {\alpha}$ are the basis of the vector fiber. 

### Normal bundles

Consider a manifold $E^{m+n}$, let $M^{m}\subset E$ be a subset of $E$. Define the normal bundle $N(M)$ to $M$ in $E$ to be consist of the vectors tangent to $E$ that are orthogonal to $M$. 

The normal bundle to $\mathbb{S}^{2}$ as a subset of $\mathbb{R}^{3}$ is trivial, $N(\mathbb{S}^{2})=\mathbb{S}^{2}\times\mathbb{R}$.

## Poincare's theorem and Euler characteristic

Consider the question, can you comb the hair on a sphere so that the directions vary smoothly and such that no hair sticks straight out radially? The answer is not obvious at all.

The most important result about vector bundles based on a surface is the Poincare's theorem. There are so many theorems named after him I am getting confused now. 

Let $M$ be a closed surface, that is, compact and without boundary. A tangent vector field on $M$ will generically have finite zero points. This is because the two coordinates $v^{1,2}$ can be regarded as two scalar functions on $M$, there zero locus are usually 1-dimensional varieties and they intersect at points. Then the closeness of $M^{2}$ makes it that there are only finite number of intersections.

Let $p\in M$ be a zero point of vector field $v$ defined on $M$. Close to $p$ choose a small circle 
$$
S=\left\{ (x,y) \,\middle\vert\, x^{2}+y^{2}=\epsilon^{2} \right\}
$$
small enough so that there is only one zero point $p$ inside the circle. In the circle we can introduce a Riemannian metric and local coordinates $(x,y)$. The coordinate will introduce basis vectors $\partial_ {x},\partial_ {y}$. On the circle $S$, we can calculate the angle between $v(S)$ and the $x$-basis $\partial_ {x}$. Call it $\theta(x,y)=\text{angle}(v(x,y),\partial_ {x})$. Consider a abstract $\mathbb{R}^{2}$ and a unit circle $S_ {0}$ defined around the origin, then there is a map $S\to S_ {0}$ that maps $(x,y)\in S$ to a point on $S_ {0}$ with polar angle $\theta(x,y)$. With this map, we can evaluate the Brower degree of it. The degree, call it $j(p)$, just counts as we go round $S$, how many time $v(x,y)$ rotates. As such
$$
j(p) = \frac{1}{2\pi}\int_ {S} d\theta(x,y).
$$
The degree is called the index of $v$ at $p$. Note that the index is independent of the details of our choice of the metric, coordinate system, etc.

Note that we may compute the index even when the field $v$ does not vanish inside the curve $S$, but the index will then be $0$.

In fact the index is not only defined for zeros of $v$ but also for singularities. For example, the electric field goes singular where the charge is at, we can still define and evaluate the index around such singularities, namely point charges. Just to be clear, by singularity of a vector field we mean any point at which the vector field is not `smooth`. However, in this note singularities can be regarded equally to zeros, thus we will define **singularities here as any point at which $v$ is not smooth or at which $v=0$**. Again, a zero of a vector field is not a singularity in the ordinary sense. In our present situation it is called a singularity because the `direction` field defined by the vector is undefined at zero.

**Poincare Theorem.** Given a vector field $v$ on a closed surface $M^{2}$, with possibly finite numbers of singularities $p\in M$ (include `ordinary singularities` where the vector field is not smooth and `zeros`), the sum of the indices satisfy
$$
\sum_ {p}j(p)=\chi(M)
$$
where $\chi(M)$ is a topologically invariant quantity. In the next section we will see that it is the Euler characteristic.

Before looking at the proof, let us look at some examples on the 2-sphere. The vector field $\partial_ {\theta}$ tangent to the lines of longitude on the 2-sphere has a singularity at the north and south poles. At the north pole the field looks like the "source" of index 1 while the south pole is a "sink," also of index 1 . Thus $\chi(\mathbb{S}^{2})=2$ in this case. We can also consider the vector field $\partial_ {\phi}$ tangent to the parallels of latitude, again with singularities at the poles. The indices are easily seen again to be both + 1, verifying the theorem. Poincare's theorem implies the following:

Every vector field on $\mathbb{S}^{2}$ has a singularity. Thus *every smooth section of the tangent bundle of the 2-sphere must be zero somewhere, and hence this bundle is not a product bundle.*

This can be paraphrased as "**You can't comb the hair on a 2-sphere**."

