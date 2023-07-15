---
layout:     post   				    # 使用的布局（不需要改）
title:     Bundles and Coset Spaces			# 标题 
subtitle:   
date:       2023-07-14 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background12.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

### Cosets

Let $G$ be a Lie group and $H$ a subgroup of $G$, denoted as $H<G$. By the way we use $H\lhd G$ to denote that $H$ is a normal subgroup of $G$. Let $g\in G$ and $h \in H$ be the elements. The `left coset space` is the space of the equivalent classes $[g]$, where the equivalence relation is defined as 
$$
\sim: g\sim g' \text{ iff } g = g' h \text{ for some } h \in  H.
$$
So left means that $G$ acts from the left to $H$. Thus 
$$
g \sim g' \text{ iff } g^{-1} g' \in H.
$$
In the case of abelian group we usually write $g+g'$, not $g g'$. We use 
$$
gH := \left\{ gh \,\middle\vert\, h \in  H \right\} 
$$
to denote the left translation of $H$ by $g$. The rule is quite straightforward, $H$ is a set thus $gH$ is also a set.

Now we've got ourselves a bundle, 
$$
\pi: G\to G / H, \quad  g\mapsto [g].
$$

Many familiar spaces are in fact coset spaces! Let's say that $G$ acts on a space $M$ as a transformation group, provided there is a map
$$
G \times  M \to M,\quad  (g,x)\mapsto gx.
$$
Of course we require the various group properties to be satisfied, for example $g (g'x) = (g g') x$, etc.

**Transitivity.** We say  that $G$ acts on $M$ `transitively` if for all $x,y \in M$ there exists a $g \in G$ such that $g x = y$. $G$ touches every and all the elements of $M$.

For example, $SO(3)$ acts transitively on $\mathbb{S}^{2}$.

**Fundamental Principal.** This principal gives a 1-2-1 correspondence between coset space and $M$. Let $G$ acts transitively on $M$, let $x_ {0}\in M$ and $H < G$ is the group that keeps $x_ {0}$ invariant, $H x_ {0} = x_ {0}$. $H$ is called the `stability, or isotropy, or little` (sub)group of $x_ {0}$. Then the points of $M$ are in 1-2-1 correspondence with the left coset $G / H$. 

The notation $G / H$ does not seem to tell us that it is the left coset, rather than right. I guess the left in left coset is just part of the definition then, a matter of convention maybe. Note that, if $G$ is not abelian, then in general $G / H$ is not itself a group. 

As an example, convince yourself that 
$$
SO(3) / SO(2) \cong \mathbb{S}^{2}.
$$

Before we mentioned on the fly the connection between coset space and bundle. The following theorem states the connection in a mathematically strict sense.

**Theorem.** Let $H < G$ be the subgroup of a *Lie group* $G$, we require $H$ to be a *closed* subgroup, namely $H$ includes all its *accumulation*, or *limiting* points. Then the coset $G / H$ can be made into a manifold of dimension $\text{dim}G - \text{dim}H$. Furthermore, $G$ is a principal bundle with structure group $H$ and base space $G / H$, the projection $\pi$ sends $g \in G$ to its equivalence class $[g]$. 

A coset space $G / H$ of a Lie group is called a `homogeneous space`.

For example, $\mathbb{S}^{2}$ is a homogeneous space. It is the coset space $SO(3) / SO(2)$ of dimension $3-1=2$.

### Grassmann manifold

The readers should not be unfamiliar with the real projective space $\mathbb{R}P^{2}$, if so please refer to my other notes. We'd like to study the connection between $\mathbb{R}P^{2}$ and $SO(3)$ group. Given a point in $\mathbb{R}P^{2}$, say the line of real axis (recall that a point in a real projective space are unoriented lines passing the origin), what is the little group that keeps it invariant? We have the familiar $SO(2)$ group which is the rotations about $x$-line, but we also have a discrete transformation $z \leftrightarrow -z$ which also keeps $z$-line invariant, so the little group is 
$$
\mathbb{Z}_ {2}\times SO(2),
$$
So the coset space is 
$$
SO(3) / (\mathbb{Z}_ {2}\times SO(2)),
$$
which according to the fundamental principal we introduced before is isomorphic to $\mathbb{R}P^{2}$.

The dimension of a Cartesian product $G \times G'$ is $\text{dim}(G)+ \text{dim}(G')$, thus $\text{dim}(\mathbb{Z}_ {2}\times SO(2))=0+1$. Then as you can show that the dimension of $\mathbb{R}P^{2}$ is indeed $2$.

**Grassmann manifold.** The space of $k$-dimensional un-oriented planes through the origin of $\mathbb{R}^{n}$ is called a Grassmann manifold and is frequently denoted by $\text{Gr(k,n)}$. Thus $\text{Gr}(1,3)=\mathbb{R}P^{2}$.