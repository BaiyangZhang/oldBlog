---
layout:     post   				    # 使用的布局（不需要改）
title:     Associated bundles and connection			# 标题 
subtitle:   
date:       2023-08-23 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background7.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - bundle
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

### Associated Bundles

Let $P\to M$ be a principal bundle, being principal means that the fiber is the same as the structure group, 
$$
\text{fiber } F = \text{group} = G.
$$
Let $c_ {UV}$ be the transition function 
$$
U \cap V \to G
$$
and let $\rho$ be the representation of $G$,  to be specific the $N\times N$ general linear matrix 
$$
\rho : G\to GL(N)
$$
that acts on $\mathbb{C}^{N}$. 

We then define a new vector bundle **associated to $P$**,
$$
\pi: E_ {\rho}\to M \text{ or }P_ {\rho}\to M
$$
through the representation $\rho$. 

The fiber of the associated group is $\mathbb{C}^{N}$. Let $\psi_ {U}$ be the fiber "coordinate" on patch $U$, similarly for patch $V$, we introduce the transition function by making the identification
$$
(x,\psi_ {U}) \sim (x,\psi_ {V}) \iff \psi_ {V} = \rho(c_ {VU}(x))\psi_ {U}.
$$
Simply put it, we just defined the transition function to be the representation of $G$. 

Recall that given a rank-$K$ vector bundle $E\to M$ and local trivialization (which works like a parametrization, instead of coordinate) 
$$
\Phi_ {U}: F \times  M \to \pi ^{-1} U, \quad \mathbb{C}^{n}\times M \to \pi ^{-1} U
$$
Then we can introduce a set of basis using $\Phi_ {U}$ by mapping for instance
$$
\Phi_ {U}(x,-): (1,0,\dots,0) \mapsto \mathbf{e}_ {U,1},\quad  \text{etc.}
$$
The transition function is 
$$
c_ {UV}\in G \subset GL(K).
$$
Then we can regard it as the associated vector bundle 
$$
E\to M := E_ {\rho}\to M
$$
of a principal bundle, let's denote it by $P\to M$. This principal bundle has for fiber $G$, with representation $GL(K)$.

The transition function of $P\to M$ is what? A general element of $P$ is 
$$
\mathbf{f} = \mathbf{e}_ {U} g_ {U} = \mathbf{e}_ {V} g_ {V},
$$
as we know from the property of the *vector bundle*, the basis transforms as 
$$
\mathbf{e}_ {V}  = \mathbf{e}_ {U} c_ {UV}
$$
then we have 
$$
g_ {U} = c_ {UV} g_ {V}
$$
to keep $\mathbf{f}$ basis-independent.

