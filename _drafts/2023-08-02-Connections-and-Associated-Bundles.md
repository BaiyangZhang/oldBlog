---
layout:     post   				    # 使用的布局（不需要改）
title:     Connections and Associated Bundles			# 标题 
subtitle:   
date:       2023-08-01				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background7.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

### The Maurer-Cartan form

Let $E\to M$ be a fiber bundle and let $G$ be the transition group. As usual, use the gothic letters ${\frak  g}$ to denote the Lie algebra of $G$. On the bundle we can define connection and curvature. It is usually quite helpful to regard connection and curvature as Lie-algebra valued, or ${\frak g}$-valued object, to be specific ${\frak g}$-valued differential forms. So, what is ${\frak g}$-valued form?

Let $M$ be a $n$-dimensional manifold, and $\phi$ a locally defined exterior form on $M$, taking values in the fixed vector space ${\frak g}$. Note now we have switched to the geometrical viewpoint of a Lie group, where ${\frak g}$ is a vector space, and $G$ itself a manifold.

First we define a ${\frak g}$-valued 1-form on $G$ itself. By definitions, given a tangent vector on $G$, namely a vector in $TG$, a ${\frak g}$-valued 1-form should take this vector to an element of ${\frak g}$, which is a vector at the identity $e$. Now let's see how this idea is realized. 

Let $E_ {R}$ be the basis of ${\frak g}$ and $X_ {R}$ be the left invariant vector fields of $E_ {R}$, where $R=1,\dots,\text{rank}(G)$. In our convention we use the capital Latin letter to label the Lie algebra indices. Let $\sigma^{R}$ be left invariant 1-forms on $G$ forming a basis dual to $X_ {R}$.  Then
$$
\Omega := E_ {R}\otimes \sigma^{R}
$$
defined by 
$$
\Omega(Y_ {g}) := E_ {R} \otimes \sigma^{R}(Y_ {g}) = E_ {R}Y^{R}
$$
is a ${\frak g}$-valued 1-form. *What $\Omega$ does is that it takes the vector $Y$ at $g\in G$ and left translate it back to the identity!* This is the `Maurer-Cartan 1-form` on $G$.

Classically this would be written as 
$$
g^{-1}dg
$$
which might look rather weird at the first look. Here $dg$ is better thought of as a vector at $T_ {g}M$ and $g^{-1}$ the induced map of $g^{-1}$ that sends a vector at $T_ {g}M$ to $T_ {e}M$, where $e$ is the identity of the group. We should write
$$
\Omega = L(g^{-1})_ {\ast }\,\circ\,dg.
$$

I admit all this is rather confusing, because by the look of it $dg$ should be a form not a tangent vector, but here it is best to think of $dg$ as a vector. I can't think of a better way to interpret it.

For a matrix group, each $E_ {R}$ is just a generator matrix, we can apply the usual matrix algebra, including the matrix multiplication and inverse, to construct $\Omega$, interested readers can work it out for $SO(2)$ group for example. 

**Theorem.** In any matrix group, $g^{-1}dg$ is a matrix with left invariant $1$-form entries.

The left invariantness is a little tricky, try to convince yourself that it is the case for $SO(2)$ group.

### from 1-form to $p$-form

The most general ${\frak g}$-valued $p$-form on a manifold $M$ is 
$$
\phi := E_ {R}\otimes \phi^{R},\quad  \phi^{R}\in \Omega^{p}(M).
$$
Since the $E_ {R}$'s do not vary, it is natural to define the 
$$
d\phi := E_ {R}\otimes d\phi^{R}.
$$
The multiplication of two such ${\frak g}$-valued p-forms are not so clear. We want the so-defined multiplication still be a ${\frak g}$-valued p-form. Take ${\frak o}(n)$ for example, the Lie-algebra vectors are anti-symmetric matrices, but the product of two anti-symmetric matrices may not be anti-symmetric anymore, so we can't adopt the naïve matrix multiplication. The solution is to take the Lie bracket of the Lie algebras, namely the commutator and define
$$
[\phi,\psi] = [E_ {R}\otimes \phi^{R},E_ {S}\otimes \psi^{S}] := [E_ {R},E_ {S}]\otimes \phi^{R}\wedge \psi^{S}.
$$
As an example, consider the Maurer-Cartan 1-form on $M=G$, we have
$$
[\Omega,\Omega]=[E_ {R}\otimes \sigma^{R},E_ {S}\otimes \Omega^{S}] = [E_ {R},E_ {S}]\otimes \sigma^{R}\wedge \sigma^{S}=C_ {RS}^{T}E_ {T}\otimes \sigma^{R}\wedge \sigma^{S}.
$$
From the Maurer-Cartan equation
$$
d \sigma^{A} = -\sum_ {R<S} C^{A}_ {RS}\sigma^{R}\wedge \sigma^{S}
$$
we have
$$
d\Omega + \frac{1}{2} [\Omega,\Omega]=0
$$
which is again called the Maurer-Cartan equation.

We have some immediate consequences from the definition, for $\phi \in\Omega^{p}$ and $\psi \in\Omega^{q}$
$$
[\phi,\psi] = (-1)^{pq+1}[\psi,\phi]
$$
and 
$$
d[\phi,\psi] = [d\phi,\psi]+(-1)^{p}[\phi,d\psi].
$$

If we regard the Lie algebra vectors as matrices, then ${\frak g}$-valued forms are matrices with forms as entries, the product
$$
\phi \wedge \psi = E_ {R}\phi^{R} \wedge E_ {S}\psi^{S}
$$
is defined as matrix multiplication but using the *exterior product* of the entries. Then it can be shown that we have a relation between the Lie algebra product 
$$
[-,-]: {\frak g} \times {\frak g} \to {\frak g}
$$
and the exterior product, 
$$
[\phi,\psi] = \phi \wedge \psi - (-1)^{pq}\psi \wedge \phi.
$$

For example, for $p,q$ odd, we have 
$$
[\phi,\phi]=2\phi \wedge \phi.
$$

### Connection in a principal bundle

Let $E\to M$ be a real or complex vector bundle of rank $K$. Let $G$ be the structure group. By this we mean that, in each trivializing patch $U$ of $M$, there exists a collection of distinguished frames (e.g., orthonormal), which we may call $G$ frames, and such that any two such frames $e_ {U}$ and $e_ {V}$ in an overlap $U \cap V$ are related by $e_ {V} = e_ {U} c_ {UV}$ where $c_ {UV}\in G$. 

A $G$-connections essentially means that given a distinguished frame $\mathbf{f}$, we can use the $G$ connection to parallel transport it along any curve, the transported frame at any point of any curve is still a distinguished frame. This requires the connection to be ${\frak g}$-valued (1-form). Then of course the curvature is also ${\frak g}$-valued, 
$$
\theta = d\omega+\omega \wedge \omega.
$$

Under a change of frame, namely in the overlap of two trivializing patches $U$ and $V$, we require that (the compatibility condition) the following two operations to be equivalent (or in the terminology of category theory, to be commute)
- parallel transport in $U$ first, then convert to $V$ patch;
- convert to $V$ first, then parallel transport in $V$.
This gives us the transition property of the connection and curvature under the change of patches,
$$
\omega_ {V} = c_ {VU}(\omega _ {U} + d) c_ {UV}
$$
and 
$$
\theta_ {V}  = c_ {VU}\omega_ {U}c_ {UV}.
$$
This should be familiar to readers.

Given a vector bundle $E$, consider the principal bundle $P$ of frames of sections of the vector bundle. The bundle $P\to M$ has for fiber $F$ the structure group $G$ and the transition function $c_ {UV}$ are the same as for $E$. 

