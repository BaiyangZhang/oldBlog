---
layout:     post   				    # 使用的布局（不需要改）
title:     The Electromagnetic Connection			# 标题 
subtitle:   question?
date:       2023-07-3 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background7.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Curvature
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

Is this note we discuss the profound connection between the electromagnetic field and the parallel transportation of wave functions. This will endow the electromagnetic field a geometric interpretation.

### Classical case

In the presence of electromagnetic fields, the charged particle will receive forces not only from a potential $-\nabla V$, but also from the electromagnetic force $q(\mathbf{E}+\mathbf{v}\times \mathbf{B})$. The latter can not be written as a covariant derivative of some potential thanks to the magnetic contribution, so we can't simply include it into a new potential form $V'$. 

Recall that the energy-momentum covector defined on the cotangent bundle of the configuration space is
$$
p_ {\mu} dq^{\mu} = g_ {\mu \nu}p^{\mu}dq^{\nu} = p_ {i}dx^{i}-Edt.
$$
We add to it the electromagnetic covector
$$
\phi dt+A_ {i} dx^{i},
$$
then we have a new total energy-momentum 1-form, from which we can construct a new Lagrangian by Legendre transform, which will tell us how a charged particle moves in EM field.

### Quantum case

Ignore the spin of a electron, it is described by a wave function $\psi(x,t)$. Schrodinger's equation states that the wave function evolves in time according to
$$
i\partial_ {t}\psi = H \psi,\quad  H = T + V = \frac{p^{2}}{2m} + V.
$$

In *Cartesian coordinates*, 
$$
p_ {i} := -i \frac{\partial}{\partial x^{i}}.
$$

With the presence of electromagnetism, the following replacement is needed,
$$
p \to p-eA, \quad  V \to V-e\phi.
$$

Furthermore, we can write the Schrodinger function in terms of the covariant derivatives if we introduce connections by 
$$
\nabla_ {\mu} := \frac{\partial}{\partial x^{\mu}} -ie A_ {\mu}.
$$
The gauge potential has a compact $1$-form expression, 
$$
A = A_ {\mu}dx^{\mu} = \phi dt+A_ {i}dx^{i}.
$$
- - -

The vector potential is not uniquely defined. We may adopt different gauge potentials in different patches, and at the overlapping region the gauge fields (connections) can be glued via gauge transformation. This is precisely the picture of complex line bundle we introduced before, whose covariant derivative is defined via the connection $\omega$ by
$$
\nabla_ {i}\psi = \partial_ {i} \psi + \omega_ {i}\psi.
$$

We find that $\omega_ {i}$ is nothing but the gauge field!

We can again confirm that gauge transformation for $A_ {\mu}dx^{\mu}$ coincides with how a connection should change under a change of coordinates, if we choose the transition function to be 
$$
c_ {VU} = \exp \left\{ -ie f(x) \right\} ,\quad  f(x) \text{ is some function.}
$$

In summary, *a wave function is not to be considered as a single-valued complex function of $\mathbb{R}^{4}$ but rather a collection of functions $\psi_ {U,V, \dots}$ of functions such that in an overlap $U\cap V$ we have* 
$$
\psi_ {V} = c_ {VU} \psi(U) = \exp(ief_ {VU})\psi_ {U}. 
$$
This brings us back to the starting point of gauge theories in quantum mechanics, namely

**Weyl's principal of gauge invariance.** If $\psi$ satisfies the Schrodinger equation with $A$, then 
$$
\exp(ief_ {UV})\psi
$$
satisfies the Schrodinger equation with $A\to A+df$. 

A summary.

- Fiber bundle: complex line bundle.
- Transition function: $U(1)$.
- Structure group: $U(1)$.
- Connection: $A = A_ {\mu}dx^{\mu}$.
- Curvature: $F = dA = -ie (E\wedge dt+B)$.

- - -

In curvilinear coordinates, what form should the Schrodinger equation take? Recall that when there is no electromagnetic field and the spacetime is flat, the Schrodinger equations is simply
$$
i\partial_ {t}\psi = H\psi = \left( \frac{1}{2m} g^{\alpha \beta}p_ {\alpha }p_ {\beta}+V \right) \psi.
$$
In a curvilinear coordinates on an Riemannian manifold $M$, we replace the momentum operator $p_ {\alpha}$ by 
$$
p_ {\alpha}:= -i \nabla_ {\alpha},
$$
where $\nabla$ is the covariant derivative. We can also replace the Laplacian with its corrected form in curvilinear coordinates,
$$
\boxed {
\nabla^{2} = \frac{1}{\sqrt{ g }} \frac{\partial}{\partial x^{\mu}}\left( \sqrt{ g } \,g^{\mu \nu}\frac{\partial}{\partial x^{\nu}} \right)
} 
$$
 refer to my blog [here](http://www.mathlimbo.net/2023/04/10/Electrodynamics-in-Terms-of-Forms/). Inserting this into the Schrodinger equation we get the curvilinear Schrodinger equation, which is left as a homework (to myself).

### Global Potentials

If the space is $\mathbb{R}^{4}$, the second Betti number is zero, then de Rham's theorem assures us that there is a potential form $A$ for the closed 2-form $F$ such that $F=dA$. However, there are usually singularities of $F$, for example at the point charge $F$ blows up, so when talking about geometry we need to take such singularities out, and this will change the topology of the spacetime. The second Betti number will in general be non-zero, but we still we have the following. 

**Theorem.** Consider a region $U$ of a general relativistic space-time $M^{4}$ that has a *global time coordinate*. That is, 
$$
U \cong V^{3} \times  \mathbb{R}
$$
where $V^{3}$ is a spacelike hypersurface. Suppose that the magnetic field $B$ vanishes at time $t=0$, Then $F$ has a global potential $A$ such that $F=dA$ on all of $U$. 

### Dirac monopole

When there is a monopole in spacetime, then we are forced to introduce the bundle and connection. 

Assume there is a monopole sitting at the origin. The magnetic field generated is 
$$
\mathbf{B} = \frac{q}{r^{2}} \partial_ {r}
$$
where $\partial_ {r}$ is the radial vector basis. In the language of forms, $B$ is a two form
$$
B = i_ {\mathbf{B}}\text{Vol}^{3} = d[q(1-\cos \theta)d\phi],
$$
which is obviously not defined on the negative $z$-axis, thus the potential is given by 
$$
A_ {U} = q(1-\cos \theta)d\phi
$$
on $\mathbb{R}^{3}$ minus the negative z-axis. In the complementary region 
$$
V = \mathbb{R}^{3} - \text{positive }z\text{-axis}
$$
the potential is given by $\phi\to-\phi,\theta\to\pi-\theta$ thus
$$
A_ {V} = -q(1+\cos \theta)d\phi
$$
and Maxwell's equation holds everywhere on $\mathbb{R}^{3}-\left\{ 0 \right\}$. The transition function is 
$$
C_ {VU} = \exp\left( - \frac{2ieq\phi}{\hbar} \right)
$$
where $\hbar$ is usually set to zero.

Now the potential is not single valued unless 
$$
2eq / \hbar = \mathbb{Z}
$$
is satisfied. 

In the language of curvature, we have
$$
\frac{i}{2\pi}\int d\theta \, = \mathbb{Z}
$$
where $\theta$ is connected to the magnetic field by
$$
\theta = -ie B.
$$

In summary, if there exists a monopole, then we **must** regard the wavefunction as a section of a complex line bundle.

