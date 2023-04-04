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
\int _ {z+\partial \omega} \beta = \int _ {z} \, \beta+{ \int _ {\partial \omega} \, \beta } =     \int _ {z} \, \beta.
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

A finite-dimensional vector space has the same dimension as its dual space. Thus

**Corollary.** If $M$ is compact then $H_ {p}$ finitely generated and the dimension of $R^{p}$ is the same as the $p$-th Betti number $b_ {p}$. Thus $b_ {p}$ is also the maximal number of closed p-forms on $M$ of which no linear combination is exact. 

The proof of de Rham's theorem is too long and difficult to be given here. Instead, we shall illustrate it with two examples. 

- - -

**The 2-torus.** The 2-torus $\mathbb{T}^{2}$ is the rectangle with identifications on the boundary. $R^{0} = F^{0} / E^{0}$, where $E^{0}$ is empty since 0-forms can't be the exterior differential of anything, there is no $(-1)$-form. The 0-closed forms are just constant functions. Thus $R^{0}$ consists of constant functions. 

$R^{1}$ consists of closed 1-forms quotient exact 1-forms. This case is more interesting. We have two closed but not exact forms at hand, namely $d\theta$ and $d\phi$. They seem exact since they are of the form $d(\text{something})$, but it is not true, since $\theta$ and $\phi$ are not **globally** defined on the 2-Torus, after going a full circle all of them will increase by $2\pi$, thus not globally well defined. Since $H_ {1}(\mathbb{T}^{2};\mathbb{R}) = \mathbb{R}A + \mathbb{R}B$, where $A,B$ are the $\theta$-circle and $\phi$-circle. $A$ and $B$ give a basis for the 1-dimensional (real) homology. Then $\int_ A \, d\theta = \int_ B \, \phi=2\pi$, thus $d\theta / 2\pi$ and $d\phi / 2\pi$ form two basis of $R=H^{1}=H_ {1}^{\ast}$. 

$R^{2}$ consists of 2-forms quotient the exact 2-forms. Note that all 2-forms are closed on a 2-dimensiona manifold by construction. There is again an obvious candidate for a closed-but-not-exact two form, namely $d\theta \wedge d\phi$. It is the basis of $H^{2}$ up to a constant, which turns out to be $4\pi$.

This was all too easy because $\theta$ and $\phi$ are almost global coordinates on $\mathbb{T}^{2}$.
