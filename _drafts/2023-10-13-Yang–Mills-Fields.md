---
layout: post
title: Yang–Mills Fields
subtitle: 
date: 2023-10-13
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
If $\phi$ is a `critical` section, that is a section satisfies the equation of motion, let $\delta \phi$ be the variation of some symmetry transformation, then we have the 

**Noether's theorem for internal symmetry.**  
$$
\text{div} \left[ \frac{\partial \mathcal{L}}{\partial \nabla\phi^{a}}\delta \phi^{a} \right] = 0.
$$

The *principal* behind Noether's theorem is more important. All internal first-variation problems lead to an expression of the form 
$$
\delta \int_ {U} \, \mathcal{L} \text{ Vol}  = \int_ {U} \,  \left( \frac{\delta \mathcal{L}}{\delta \phi} \right)\delta \phi \text{ Vol} + \int _ {U} \, G(x,\phi,\delta \phi) \text{ Vol} .
$$
Again, if $\phi$ is critical and $\delta \phi$ be the variation of some internal symmetry, then by the definition of internal symmetry, the action is left alone (free from surface contribution), then $G(x,\phi,\delta \phi)=0$. This is sometimes referred to as the `Noether's principal.` 

### Yang–Mills Nucleon

Heisenberg postulated that the proton and the neutron behave identically with respect to the “strong” interactions between nuclei. The isospin group is 
$$
U(2) / U(1) = SU(2),
$$
but why $U(1)$ should be excluded? It is because given a nucleon state, which is a mixture of proton and neutron state, 
a global rotation by a constant $e^{ i\alpha }$ gives the same state!

Yukawa, in 1935, introduced the idea that one should explain the strong nuclear force between nucleons by assuming that the force arises from the exchange of certain particles, mesons, unobserved at that time, just as the force between electrons results from the exchange of photons. Yang and Mills in 1954 suggested that we can arrive at exchange mesons by assuming that the correct Lagrangian for the nucleon will admit $SU(2)$ as a local symmetry group, rather than the global one of Heisenberg. the nucleon field should be considered not as a $\mathbb{C}^{2}$ function on space–time but rather as a section of a $\mathbb{C}^{2}$ vector bundle, whose structure group is $SU(2)$. Bundles has much advantage over functions, besides that it is defined globally, bundle is the most natural language for gauge theories, bundles contain the information of frames, and the free change of frames (gauge transformation). In a bundle, the different choice of frames will result in a extra piece to the curvature, that is why in comparison with the Riemannian manifold curvature, except for $\omega$ curvature which is there in both cases, there is also a $g^{-1}dg$ in the curvature of a bundle. This really comes from the associated bundle of frames. 

### Compact Groups and Yang–Mills Action

The $U(N)$ group is compact. To see that, consider the components $u_ {ij}$ of $U\in U(N)$. The unitarity translates to
$$
\mathrm{Tr}\,U^{\dagger} U = N \implies \sum_ {ij} {u}^{\ast }_ {ij} u_ {ij} = N = \sum_ {ij} \left\lvert u_ {ij} \right\rvert ^{2},
$$
thus all the $u_ {ij}$ live on a complex sphere, hence must be compact.

The advantage of compact group is that 

**Theorem.**  In a compact Lie group, the left and right Haar measures coincide (the Haar measure is bi-invariant).

**Proof.** Let 
$$
\omega = \sigma_ {1} \wedge  \dots \wedge  \sigma_ {n}
$$
be the *left invariant* volume form. To say $\omega$ is *right invariant* is to say the for $g \in G$, 
$$
R_ {g}^{\ast } (\omega {\Large\mid}_ {g} ) = \omega {\Large\mid}_ {1}, \quad  1 \text{ is the identity.} 
$$
Let $e$ be an orthonormal basis of left invariant vector fields and 
$$
\left\langle \omega,e \right\rangle =1.
$$
If $\omega$ is **not** right invariant, we will have 
$$
\left\langle R_ {g}^{\ast }(\omega), e \right\rangle = \left\langle \omega, R_ {g\ast } e \right\rangle =c \neq 1,
$$
where we have omitted some notations. Let's just write 
$$
R_ {g\ast } e = e g.
$$
This would mean that 
$$
\left\langle \omega, g^{-1} eg \right\rangle =c.
$$
Thus under this adjoint action $\text{Ad}(g)$, the orthonormal $e$ at the identity is sent into a frame at the identity with volume $c > 1$. Under $Ad(g^{n})$, the frame $e$ is sent into a frame with volume $c^{n}\to \infty$ as $n\to \infty$. This means that a continuous function 
$$
F: G \to \mathbb{R}, \quad  g \mapsto \omega(g ^{-1}e g)
$$
is not bounded on $G$ (think hard about it!). Here comes the key point: *any continuous real-valued function on a compact space is bounded*! A contradiction. Q.E.D.

Leg $\omega_ {h}$ be the volume form at $h$. For any continuous function $f$ and for all $g$ in the compact group $G$ we have

$$
\int _ {G} \, f(h) \omega_ {h} = \int _ {G} \, f(gh) \omega_ {h} =   \int _ {G} \, f(hg) \omega_ {h}.
$$
This should be intuitive since $g$ is a isomorphism from the group to itself. 

