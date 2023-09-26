---
layout: post
title: Introduction to Higher Form Symmetry
subtitle: Lecture 2
date: 2023-09-18
author: Baiyang Zhang
header-img: img/lib18.jpg
catalog: true
tags:
  - PureMath
  - GeneralizedSymmetry
  - Notes
---

## Ordinary symmetries

Before going to the generalized symmetries, let's first review some aspects of ordinary symmetries in quantum field theory (QFT).

### Noether current

Noether theorem says that each continuous, physical symmetry (physical symmetry, as opposed to nonphysical symmetry, such as gauge symmetry) gives rise to a conserved current. The derivation of Noether current is most familiar to every physicist, so I won't waste time to derive it here. The traditional, or standard way to obtain it is to follow the below given steps.
1. The action is invariant under an *infinitesimal, continuous, global* transformation. However it doesn't mean the the Lagrangian has to be strictly invariant under the same transformation, it can still vary by a total derivative, since its contribution is a surface terms, and for most theoretical setups, everything is set to be zero at the boundary of space time, so the surface terms contributes nothing. 
2. Substitute the varied Lagrangian into the action, with the help of various mathematical tools, such as integral by part, etc., we can extract the variation of the actions that is proportional to the variation of the fields, which must be identically zero, since the field variation is arbitrary. Along the process the *equation of motion* must be applied. 
3. Eventually we arrived at the conserved current $\partial_ {\mu}J^{\mu}=0$. 

An particularly clever way to derive the Noether current is to *gauge* the global symmetry. By gauging something it is meant that making some global symmetry local, for example, the wavefunction has a global symmetry $\psi\to e^{ i\theta }\psi$, where $\theta$ is a constant, hence this transformation is global; we can gauge this transformation by making $\theta$ position-dependent, namely $\psi\to e^{ i\theta(x) }\psi$. Gauging a symmetry is the same thing as gauging a transformation, we will use them interchangeably. The gauging method to derive the Noether current works as follows.
1. Under the infinitesimal global symmetry transformation $\phi\to \phi+\epsilon \phi$, the action is still invariant (otherwise it won't be a symmetry would it), $S\to S$. Now we gauge $\epsilon$, making it spacetime-dependent, $\epsilon\to\epsilon(x)$.
2. Under a gauged symmetry transformation, the action will receive extra contribution coming from the derivative of $\epsilon$, at the leading order this contribution should be proportional to (linear in) $\partial_ {\mu}\epsilon(x)$, that is $\delta S =\int \, J^{\mu}\partial_ {\mu}\epsilon(x)$. Here $J^{\mu}$ is just the proportional coefficient, and the upper index $\mu$ is needed to contract with the lower index $\mu$ in $\partial_ {\mu}$. 
3. Now let us take the field configuration to be a physical one, that is, the configuration satisfies the equation of motion. Such configurations has an crucial advantage: it is a saddle point, any field variation about it will leave the action invariant, including the before defined gauged symmetry transformation. Thus we have something like $\delta S = \int  \, J^{\mu}\partial_ {\mu}\epsilon(x)=0$. Apply the integral by part and neglect the surface term, we arrive at $\partial_ {\mu}J^{\mu}=0$, we have found the conserved current $J^{\mu}$!

- - -

As an excursion, I just like to mention some of my own philosophical understandings about the connection between a symmetry transformation and conserved current, feel free to skip this paragraph. They are like the two sides of the same coin, but what is this coin? A conserved quantity *shows certain blindness to the physical system*, *the incompetent of identifying the situation*. For example, conservation of energy means that the total energy is the same at any minute, so we can not use the total energy to identify time, as a clock. Interesting enough, the corresponding symmetry transformation, namely the time translation, has the same effect, it says that we can perform our experiment at any time, as long as it is the same experiment then we will get the same results, we are blind to the time at which the experiment is performed. In mathematics, we meet various obstructions to do things, for example it is the case in homology, and things become more interesting when such obstructions are present, maybe here it is similar, the conserved current, or symmetry transformation, can be regarded as a obstruction of identifying certain property of the physical system, for instance, the pair (time translation symmetry, energy conservation) is an obstruction for us to use it to tell the time of a system, simply because it is not time-dependent; the pair (space translation symmetry, momentum conservation) both suggests the blindness to the absolute position. But this picture also has lots of shortcomings, for example we not only have a conserved quantity but a conserved current, the latter is a stronger condition, it says that the way the conserved quantity moves is actually continuous, it can not just disappear somewhere and at the same second re-appear somewhere else, in other words the causality is preserved, I don't know how to fit the importance of conserved currents into the "obstruction" language. Anyway, it is interesting to think of symmetry this way.

- - -

Having found the conserved current, we instantly have the conserved charge,
$$
Q = \int d^{D-1}x \,  J^{0}
$$
where the spacetime is supposed to be $D$-dimensional. The conserved charge in conserved in one spacetime dimension, namely time, thus it must be integrated over *all the other dimensions*, namely the full space. 

Note that contrary to naïve speculations, the conserved current is in fact *not* uniquely defined, for we can add to $J^{\mu}$ any four-divergence of some anti-symmetric tensor $\partial_ {\nu}\Omega^{\mu \nu}$, then obviously
$$
\partial_ {\mu}(J^{\mu} + \partial_ {\nu}\Omega^{\mu \nu}) = 0 + \partial_ {\mu}\partial_ {\nu}\Omega^{\mu \nu} = 0
$$
since $\Omega^{\mu \nu}= -\Omega^{\nu \mu}$. In physics, we sometimes make use of this property to render the energy-momentum tensor $T^{\mu \nu}$ to be symmetric in $\mu$ and $\nu$. Define $J' = J + \partial_ {\nu}\Omega^{\mu \nu}$, $J'$ and $J$ leads to the same conserved quantity (with sensible boundary condition). 

The quantization, to be specific the canonical quantization upgrade the Noether charge to a operator and bestows to it a profound meaning. The conserved charge $Q$, now being an operator, becomes the generator of the symmetry operator! For example, the momentum in the $x$-direction, $p_ {x}$, was classically a function, a so-called classical number or c-number. After quantization $\hat{p}_ {x}$ becomes an operator with certain commutation relation with $\hat{x}$, which is the position operator. Furthermore the translation in the $x$-direction is generated by $\hat{p}_ {x}$, to be specific the translation by distance $l$ is realized by the operator $\exp(-il\hat{p}_ {x})$. I could be wrong by a minus sign in the exponent, never could remember it. 

### Ward identity

The idea is as follows.

1. Under the symmetry transformation, the fields transform as 
$$
\phi\to \phi' = R(g) \phi := 1+\delta \phi = 1+ \varepsilon(x) \Delta \phi(x),
$$
where we used $\delta \phi$ to denote infinitesimal variation of field while $\Delta \phi$ the finite change. $g \in G$ is an element of the symmetry group $G$, which could be either the gauge transformation or some physical transformation. We have made $\varepsilon(x)$ a function of $D$-dimensional space(-time).

2. Regard the transformed field $\phi'$ as the dummy variable in the path integral, then use it to express the partition function *with a source $K$*. Usually the source is denoted by $J$ but we have already used it to denote the conserved current, so to avoid confusion we use $K(x)$. In Euclidean measure
$$
Z[K] = \int D\phi' \, e^{ -S_ {E}[\phi']+\int K\phi'(x) \,   }.
$$
Then substitute the expression of the transformed field, namely $\phi'=\phi+\epsilon(x)\Delta \phi$, we get a new expression of $Z[K]$ in terms of $\phi,\Delta \phi$ and $\epsilon(x)$. Assume the measure is invariant under $\phi\to\phi'$, namely assume the *symmetry is not anomalous*, the new partition function $Z[K]$ is equivalent to the old one. Then we would get
$$
\left\langle e^{ \int d^{D}x' \, K(x')\phi(x') }(\partial_ {\mu}J^{\mu}-K(x)\Delta\phi(x)) \right\rangle=0
$$
where as usual the vev is given by 
$$
\left\langle \bullet \right\rangle := \frac{1}{Z} \int D\phi \,  e^{ -S_ {E} }(\bullet).
$$
Then we can take the functional derivative w.r.t. $K(x)$ then set it to zero, what we get are collectively called the Ward identities. For example, take no derivative and set $K=0$ we get
$$
\left\langle \partial_ {\mu}J^{\mu} \right\rangle =0.
$$
Take one derivative $\delta / \delta K(y)$ and set $K=0$ we get
$$
\left\langle \partial_ {\mu}J^{\mu}(x) \phi(y)\right\rangle-\delta(x-y)\left\langle \Delta\phi(y) \right\rangle =0.
$$
The second term, the so-called contact term, is a quantum correction to the classical result. 

### Symmetries in differential form

In this part we will use the Language of differential forms a lot, for a beginner-friendly introduction please refer to my other [blog](http://www.mathlimbo.net/2023/04/10/Electrodynamics-in-Terms-of-Forms/).

Next let's rewrite what we already know about ordinary symmetry in the language of differential form. Given a conserved current $J_ {\mu}$, we have $\partial_ {\mu}J^{\mu}=0$. We can regard it as a 1-form $J\in \Omega^{1}$, 
$$
J := J_ {\mu} dx^{\mu}, \quad  J_ {\mu} = g_ {\mu \nu}J^{\nu}
$$
then the conservation law is 
$$
d\star J =0.
$$

Let the space-time be a $D$ dimensional manifold with Euclidean metric, with $D-1$ dimensional submanifold denoted as $\Sigma$. $\Sigma$ has co-dimension one.  The Noether charge on $\Sigma$ can be written as 
$$
Q(\Sigma)= \int _ {\Sigma} \,  \star J
$$
 as one can easily verify that this indeed gives the familiar integral of charge when applied on Minkowski spacetime. Now we can generalize Minkowski spacetime to any manifold with arbitrary metric, but for the sake of simplicity we first confine ourselves to Euclidean spacetime, Minkowski results can be obtained from Euclidean spacetime via Wick rotation and path integral. 

The quantum consequence of symmetry is the Ward identity, so let's see what it gives us when we combine (up to a minus sign on the tight hand side)
$$
\left\langle \partial_ {\mu}J^{\mu}(x) \phi(y)\right\rangle = \delta(x-y)\left\langle \Delta\phi(y) \right\rangle.
\tag{0}
$$
with 
$$
Q(\Sigma)= \int _ {\Sigma} \,  \star J.
$$
Let $\Omega$ be a $D$-dimensional manifold whose boundary is $\Sigma$, $\partial \Omega=\Sigma$. 

In term of differential form, 
$$
\left\langle \partial_ {\mu}J^{\mu}(x)\phi(y) \right\rangle = \left\langle d\star J\phi(y) \right\rangle = \left\langle d[(\star J) \phi(y)] \right\rangle = d\left\langle (\star J)\phi(y) \right\rangle
\tag{1}
$$
where $d$ only acts on coordinate $x$, $\phi(y)$ is to be regarded as a constant to $d_ {x}$. That is why we can write $(d \star J)\phi(y)$ as $d[(\star J)\phi(y)]$. 

Integrate Eq. (1) over $\Sigma$, we have 
$$
\int_ {\Omega}  \, d\left\langle \star J \phi(y) \right\rangle = \int_ {\partial \Omega=\Sigma} \, \left\langle \star J \, \phi(y) \right\rangle = \left\langle Q(\Sigma)\,\phi(y) \right\rangle  ,
$$
where we have used the Stokes theorem. But we also have the contact term in the Ward identity, namely the RHS of Eq.(0), integrate it over $\Omega$ we get
$$
\int_ {\Omega}d^{D}x \, \delta(x-y)\left\langle \phi(y) \right\rangle = 
\begin{cases}
\left\langle \Delta\phi(x) \right\rangle & x\in \Omega, \\
0 &  x \notin \Omega.
\end{cases}
$$
In summary,
$$
\left\langle Q(\Sigma)\,\phi(y) \right\rangle =\int_ {\Omega} d^{D}x\, \delta(x-y) \left\langle\Delta \phi(y) \right\rangle,
$$
Note that $\Omega$ has coordinate $x$ while $y$ can be regarded as part of the name of the operator $\phi(y)$. Since $x$ is the coordinate which varies on $\Omega$, the exterior differential $d$ acts on it only, not $y$. 

There is a topological interpretation of $\int_ {\Omega}d^{D}x \,\delta(x-y)$. If $y$ is inside $\Omega$ then the integral gives $1$, if not then the integral gives zero, we call it the `intersection number` of $\Omega$ and $y$. It can be regarded as the `link number` between the boundary of $\Omega$, i.e. $\Sigma$ and the point $y$. This link number between a point and a co-dimensional one object can be regarded as the generalization of the link number between two loops (see *Theodore Frankel*). We have
$$
\boxed { 
\text{Link}(\Sigma,y):= \int_ {\Omega} d^{D}x\, \delta(x-y).
}
$$
The topological picture of link number is more or less intuitive, it tells us if we move a point infinitely far away from a co-dimensional one object, the least number of times that the former has to intersect the latter. Then
$$
\left\langle Q(\Sigma)\,\phi(y) \right\rangle =\text{Link}(\Sigma,y) \left\langle \Delta \phi(y) \right\rangle .
$$
Note that the above relation is *linear with respect to the manifold* $\Sigma$, since it is based on integrals and integrals are linear upon the integral domain. Suppose $\Sigma'$ is another co-dimensional one object which does not contain $y$, then
$$
\left\langle Q(\Sigma+\Sigma')\,\phi(y) \right\rangle =\text{Link}(\Sigma+\Sigma',y) \left\langle \Delta \phi(y) \right\rangle =\text{Link}(\Sigma,y) \left\langle \Delta \phi(y) \right\rangle +\text{Link}(\Sigma',y) \left\langle \Delta \phi(y) \right\rangle 
$$
since $\text{Link}(\Sigma',y)=0$, we have 
$$
\left\langle Q(\Sigma+\Sigma')\,\phi(y) \right\rangle = \left\langle Q(\Sigma)\,\phi(y) \right\rangle
$$
if $\Sigma'$ has zero link number with $y$. This tells us the topological nature of this operator.

Follow the ideas of the construction of symmetry operators in a Hilbert space, we are encouraged to consider 
$$
\boxed { 
U(g,\Sigma^{(d-1)}) := e^{ i \theta(g) Q(\Sigma) },
}
$$
the generator $Q$ carries the information of the support of the "operator", the parameter $\theta(g)$ carries the information of the group element, it can be simply written as $g$ if you like. This is usually by construction a *unitary* operator, since $Q(\Sigma)$ almost always corresponds to some physical observable hence are hermitian. Assume under the group action $g$ the field operator transforms as $\Delta \phi = T\phi$, where $R$ is certain representation of the generator. Assume the linking number between $\Sigma$ and $y$ is $1$, this will greatly simplify our notation. Then 
$$
\left\langle Q(\Sigma)\,\phi(y) \right\rangle =T \left\langle \phi(y) \right\rangle .
$$
Since $R$ is the generator of the group action, it inspires us to treat it as an infinitesimal form of something of finite size. Since 
$$
\left\langle \{1+id\theta \,Q(\Sigma)\}\phi(y) \right\rangle = (1+id\theta T)\left\langle \phi(y) \right\rangle
$$
we have
$$
\begin{align}
\left\langle U(g,\Sigma)\phi(y) \right\rangle &= \left\langle e^{ i\theta(g)Q(\Sigma)} \phi(y)\right\rangle \\
&=\left\langle \lim_{ N \to \infty }\left( 1+i \frac{\theta(g)}{N} Q(\Sigma) \right)^{N} \times \phi(y)  \right\rangle \\
&=\lim_{ N \to \infty } \left\langle (1+id\theta Q(\Sigma))^{N}\times \phi(y) \right\rangle \\
&=\lim_{ N \to \infty } \left\langle (1+i d\theta T)^{N} \phi(y) \right\rangle \\
&= \left\langle \exp(i \theta(g)T) \phi(y)  \right\rangle \\
&=e^{i \theta(g)T} \left\langle  \phi(y)  \right\rangle \\
&=: R(g) \left\langle  \phi(y)  \right\rangle.
\end{align}
$$

Since the group action $R(g)$ acts on an operator $\phi(y)$ whose support is a point, we call this a 0-form symmetry. The operator $U(g,\Sigma)$ is sometimes called a `symmetry defect operator`.

In order for $U(g,\Sigma)$ to enact a symmetry, it must represent a group structure,
$$
U(g,\Sigma) \,\circ\,U(g',\Sigma) = U(g\,\circ\,g',\Sigma).
$$
Indeed it can be shown that 
$$
\left\langle U(g,\Sigma)U(g',\Sigma)\phi(y) \right\rangle = R(g)R(g')\phi(y)=R(g g')\phi(y).
$$

We have talked about the topological nature of charge $Q(\Sigma)$ when put in the vev. The topological nature of $U(g,\Sigma)$ can also be shown as a consequence of the conservation of the current. Let $\Sigma'$ be a homotopic deformation of $\Sigma$, meaning $\Sigma-\Sigma'$ is the boundary of some $D$-dimensional bulk which does not contain $\phi(y)$ or any charged operator. Then 
$$
\begin{align}
U(g,\Sigma)U(g^{-1} \Sigma') &= e^{ i\theta(g) Q(\Sigma) }e^{ i \theta(g^{-1} )Q(\Sigma')  } \\
&= e^{ i\theta(g)\int_ {\Sigma} \, \star J  }e^{ i(-\theta(g))\int_ {\Sigma'} \, \star J  } \\
&= \exp \left\{ i\theta(g)\int_ {\hat{\Sigma}} \,\star J   \right\}  \\
&= \exp \left\{ i\theta(g)\int_ {\partial(\Sigma-\Sigma')} \,\star J   \right\}  \\
&= \exp \left\{ i\theta(g)\int_ {\Sigma-\Sigma'} \,d\star J   \right\}  \\
&=1.
\end{align}
$$

Thus 
$$
U(g,\Sigma)U(g^{-1} ,\Sigma')=1 \implies U(g,\Sigma)=U(g,\Sigma').
$$

This tool even generalized to discrete symmetries. Discrete symmetries, as gauge symmetry (which is *not* a real symmetry), has no Noether current, but the action of such symmetries on Hilbert space can nevertheless be represented as an operator, call it $U(g)$. This time there is no continuous parameter $\theta(g)$ involved. However, there are extra difficulties involving the topology of the spacetime. We will not dwell on this topic here. 

