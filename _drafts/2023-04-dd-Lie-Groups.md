---
layout:     post   				    # 使用的布局（不需要改）
title:     Lie Groups, Invariant Vector Fields, and Forms		# 标题 
subtitle:   
date:       2023-04-dd 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background14.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

Let $M(n,\mathbb{R})$ be the set of all $n\times n$ real matrices, it has $n\times n$ elements thus is topologically isomorphic to a $n\times n$ dimensional real space $\mathbb{R}^{n\times n}$. The *real general linear group* $\text{GL}(n,\mathbb{R})$ is the group of all *invertible* (with non-zero determinant) $n\times n$ real matrices. We can regard such matrices as a point $x$ in some space, with the coordinates given by all its elements $x_ {ij}$, then $\text{GL}(n,\mathbb{R})$ is a sub-space in $\mathbb{R}^{n\times n}$. The question is, what exactly is this subspace? Is it a codimension one open set or something? To answer this question, notice that the determinant is a map from $M(n,\mathbb{R})$ to $\mathbb{R}$ which is **continuous**. The image of $GL(n,\mathbb{R})$ under the map is $\mathbb{R} - 0$ and is open in regular topology, thus the preimage of determinant function is also open, namely $GL(n,\mathbb{R})$ is a open subspace of $M(n,\mathbb{R})$. The product and inverse are also continuous functions defined on $GL(n,\mathbb{R})$, thus when we consider $GL(n,\mathbb{R})$ as a manifold and the matrix points, product and inverse are smooth functions on this manifold. This brings as to the definition of a `Lie group`:

**Definition.** A `Lie group`$G$ is a manifold endowed with a product, that is, a map 
$$
G\times G \to G,\quad  (g,h)\mapsto gh
$$
making $G$ into a group. We demand that this map, as well as the "inversion map" be **differentiable**. 

For example, $\mathbb{R}$ is a Lie group under addition. This group is commutative, or `abelian`. The positive real numbers $\mathbb{R}^{+}$ also form a abelian group under multiplication. The real and complex general linear matrices $GL(n,\mathbb{R})$ and $GL(n,\mathbb{C})$ are also Lie groups under the usual matric multiplication. The `special linear` group, $SL(n,\mathbb{R})$ is the subset of $GL(n,\mathbb{R})$ that have determinant one. For any matrix group, the adjective **special** means that the determinant is equal to one. Other examples include $\mathbb{T}^{n}$ the $n$-torus group, which is the abelian group of diagonal matrices of the form 
$$
z = \text{diag }\left\{ \exp i \theta_ {1},\dots,\exp i \theta _ {n} \right\} .
$$
The $\mathbb{T}^{n}$ group is topologically homeomorphic to $\mathbb{S}^{1}\times\dots \times \mathbb{S}^{1}$, $n$ copies of them. Since the circles are connected, it follows that $\mathbb{T}^{n}$ is also connected.

As a manifold, a Lie group is very special for the following reason. A Lie group always has two families of diffeomorphisms, the left and right translations. For $g\in G$, these translations are defined by
$$
L_ {g}: G \to G, \quad  h \mapsto gh, \text{multiply from the left}
$$
and similarly 
$$
R_ {g}: G \to G, \quad  h \mapsto hg, \text{multiply from the right.}
$$

**Theorem.** $U(N)$ is connected.

To see it, just notice that any unitary matrix can be diagonalized to a $\mathbb{T}^{n}$ under some similar transformation, we casually write it as $\mathbb{T}^{n} = g U(N) g^{-1}$ for some $g\in U(N)$. Then $U(N)=g^{-1}\mathbb{T}^{n}g$ is connected to $\mathbb{1}$ smoothly by varying $\mathbb{T}^{n}$ smoothly from $\mathbb{1}$. 

