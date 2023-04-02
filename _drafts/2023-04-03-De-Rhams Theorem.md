---
layout:     post   				    # 使用的布局（不需要改）
title:     De Rhams Theorem			# 标题 
subtitle:   When is a closed form exact?
date:       2023-04-03 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background10.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

In this note we shall only be concerned with homology with real coefficients $\mathbb{R}$ for a manifold $M^{n}$. The singular chains $C_ {p}$, cycles $Z_ {p}$, boundaries $B_ {p}$ and homology groups $H_ {p}$ then form real vector spaces. The "taking the boundary" operation is a linear map $\partial: C_ {p}\to C_ {p-1}$, the kernel consists of the cycles $Z_ {p}$ (by definition) and the image consists of the boundaries $B_ {p-1}$ (by definition).

We also have the real vector spaces of `differential forms` on the manifold $M$, including the smooth p-forms $\Omega^{p}$, the closed forms $F^{p}$ and the exact forms $E^{p}$. The exterior derivative $d$ is a linear transformation $d: \Omega^{p} \to \Omega^{p+1}$, whose kernel are the closed forms $F^{p}$ and image the exact forms $E^{p+1}$. It yields a group 
$$
\boxed{
R^{p} := \frac{F^{p}}{E^{p}} = \text{(closed p-forms)} / \text{(exact p-forms)}.
}
$$

It is sometimes called the `de-Rham` vector space. It is a group quotient. $R^{p}$ is the collection of equivalence classes of closed p-forms, two p-forms are identified iff they differ by an exact p-form. **De Rham's theorem is a relation between $R^{p}$ and $H_ {p}$.**

Integration allows us to associate to each p-form $\beta \in\Omega^{p}(M)$ a `linear functional` $I_ {\beta}$, $I$ for integral, that acts on a p-chain $c \in C_ {p}(M)$ by 
$$
I_ {\beta}(c) := \int_ {c} \, \beta.
$$
We shall, however, only be interested in this linear functional when $\beta$ is closed, $d\beta=0$, and when the chain $c$ is a cycle, $\partial c=0$. We thus think of integration as giving a linear transformation from the vector space of closed forms $F^{p}$ to the dual space $Z^{\ast}$ of the cycles (seen as a vector space here)
$$
I : \text{closed p-forms} \to \text{dual cycles},\quad I:\beta\mapsto I_ {\beta}
$$
where dual cycles takes a cycle and spits out a (real) number. It is realized by integral, 
$$
I_ {\beta}(z) := \int _ {z} \, \beta, \quad  z \in  Z_ {p}.
$$

Actually, $I_ {\beta}$ is a linear functional on the **equivalence classes** of cycles mod the boundaries, since 
$$
\int _ {z+\partial \omega} \beta = \int _ {z} \, \beta+\cancel{ \int _ {\partial \omega} \, \beta } =     \int _ {z} \, \beta.
$$

Thus the functional really gives a linear functional on $H_ {p}$,
$$
I : F \to H_ {p}^{\ast }.
$$

Furthermore, the linear functional $I_ {\beta}$ is the same as the functional $I_ {\beta+d\alpha}$, since the integral of an exact form over a cycle vanishes. In other words, the integral really defines a linear transformation from $F^{p} / E^{p}$ to $H_ {p}^{\ast}$, that is, from the de Rham vector space to the dual space of the homology $H_ {p}$. This latter dual space is commonly called the `p-th cohomology` vector space, written $H^p$,
$$
\boxed{
H^{p}(M;\mathbb{R}) := H_ {p}(M;\mathbb{R})^{\ast }.
}
$$

Thus the integral functional $I$ is a map
$$
I: \text{de Rham space }R^{p} \to \text{cohomology }H^{p}.
$$

Poincare conjectured, and in 1931 de Rham proved 
**de Rham's Theorem.** $I: R^{p}\to H^{p}$ is an isomorphism. First, $I$ is onto, this means that any linear functional on homology classes is of the form $I_ {\beta}$ given by some closed p-form $\beta$. In particular, if $H_ {p}(M;\mathbb{R})$ is finite-dimensional, as it is when $M$ is compact, and if 
$$
z^{(1)}, \dots,z^{(b)}, \quad  b = \text{the p-th Betti number}
$$
is a p-cycle basis of $H_ {p}$, and if $\pi_ {1},\dots,\pi_ {b}$ are arbitrary real numbers, then there is a closed form $\beta$ such that 
$$
\int _ {z^{(i)}} \, \beta = \pi^{i}, \quad  i = 1,\dots,b. 
$$
Second, $I$ is one-to-one. This means that if $I_ {\beta}(z)=0$ for all $z$, then $\beta$ is the equivalent class of zero, meaning that $\beta$ is exact. 

The numbers $\pi_ {i}$ are called the `periods` of the form $\beta$ on the cycle $z^{(i)}$s. Thus **a closed p-form is exact iff all of its periods on p-cycles vanish.**

