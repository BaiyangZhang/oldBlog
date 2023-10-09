---
layout: post
title: Yang–Mills Fields
subtitle: 
date: 2023-10-08
author: Baiyang Zhang
header-img: img/background19.jpg
catalog: true
tags:
  - Geometry
  - Frankel
---

*Disclaimer: Nothing in this note is original.*

### Noether's theorem revisited

Consider the variation of some integral
$$
\delta\int _ {M} \,  L_ {0}(x,\phi,\phi_ {x}) dx^0 \wedge \dots \wedge dx^{n} =0
$$
where both the fields and the *domain of integration* varies. The variation $\delta x$ of the domain is call `external variation` and the variation of the field $\delta \phi$ is called the `internal variation`. 

Let $M$ be a $n+1$ dimensional pseudo-Riemannian manifold and $E\to M$ be a $\mathbb{R}^{n}$ vector bundle over $M$. Let $U\subset M$ be a patch of $M$, let $\phi$ be a section over $U$. The `Lagrangian` is a functional 
$$
L_ {0} = L_ {0}(x, \phi,\phi'),\quad  x \in  U.
$$
We are concerned with the `action` integral
$$
S = \int_ {M} \, L_ {0}(x,\phi,\phi _ {x}) \,d^{n+1}x,\quad  d^{n+1}x := dx^{0}\wedge \dots \wedge dx^{n}.
$$
In order to introduce the volume form, we write
$$
L_ {0} dx  = \mathcal{L}_ {0}(x,\phi,\phi') \sqrt{ g }\, dx^{0}\wedge \dots \wedge dx^{n}.
$$
where $\sqrt{ g }=\sqrt{ \left\lvert g \right\rvert }$, I just feel lazy to write the whole thing. $\mathcal{L}_ {0}$ is a true scalar, called the Lagrangian `density`. We want $\mathcal{L}_ {0}$ to be a scalar, but usually when the fiber bundle is not "flat", the ordinary derivative is not enough. Let the structure group be $G$ with Lie algebra ${\frak g}$, then the connection is ${\frak g}$-valued 1-form, with which we can construct the covariant derivative $\nabla \phi$. Given the metric $g_ {\mu \nu}$ we can then construct a truly scalar function $\mathcal{L}$, with $\phi'$ replaced with $\nabla_ {\mu}\phi$, 
$$
\mathcal{L} = \mathcal{L}(x,\phi,\nabla \phi).
$$
However this is not always the case, for example in General relativity the Lagrangian is the scalar curvature $R$, with no covariant derivative but only regular derivative.

From $\nabla \phi=\partial \phi+\omega \phi$ and $\delta \partial=\partial \delta$ and from the assumption that the connection is unaffected by a variation of $\delta \phi$, we see immediately that 
$$
\delta (\nabla \phi) = \nabla (\delta \phi).
$$

It can be shown that if $\phi_ {U}^{a}$ is a section on $E$, then $\partial \mathcal{L} / \partial \phi_ {U}^{a}$ define a section of the **dual bundle** $E^{\ast}$. The difference between $E$ and $E^{\ast}$ can be distinguished from how the transition functions act on the sections, whether it is from the left or from the right. 

Recall that $\delta \phi$ is a section of $E$, so if $\partial \mathcal{L} / \partial \phi$ is a section of $E^{\ast}$ then
$$
\frac{\partial \mathcal{L}}{\partial \phi} \delta \phi \text{ is a scalar.}
$$
If there are more than one $\phi$ we just sum over all of them. 

Spare the details, we finally arrive at the equation of motion:
$$
\frac{\delta \mathcal{L}}{\delta \phi} = \frac{\partial \mathcal{L}}{\partial \phi}-\nabla_ {\mu} \frac{\partial \mathcal{L}}{\partial(\nabla_ {\mu}\phi)}=0.
$$

That is, if we choose the `essential` or `imposed` boundary condition to be that $\delta \phi$ vanishes on the boundary. 

Assume the Lagrangian is invariant under the fiber motion $\phi\to \phi(\alpha)$, we shall mainly be interested in the case where there is a 1-parameter subgroup 
$$
g(\alpha) = e^{ \alpha E }
$$
where $E$ is an element of the Lie algebra of the transition group, $E \in {\frak g}$. The fiber transformation is 
$$
\phi \mapsto g(\alpha) \phi.
$$
