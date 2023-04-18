---
layout:     post   				        # 使用的布局（不需要改）
title:      Confinement in Toy Models 	# 标题 
subtitle:   Lecture 3      # 副标题
date:       2023-04-11			        # 时间
author:     Baiyang Zhang 				# 作者
header-img: img/mathArt118.jpg 	        # 这篇文章标题背景图片
catalog: true 						    # 是否归档
tags:								    # 标签
    - math
    - quantum field theory
    - confinement
---

### The dual description of 3D gauge field

In 3D spacetime, a photon, if considered as a oscillating electromagnetic field, has only one direction of oscillation thus only one physics degree of freedom, thus can be descried using a scalar field. That's the rough idea. In the following we will talk about the dual fields of electromagnetic fields in 3D, IR, SU(2) field. 

Remember that in our theoretical construction the $W$ bosons are too heavy thus decouples from the model, we are left with an abelian $U(1)$ gauge field $A_ {\mu}$, and possibly a light Higgs boson, if $\lambda$ is considered small. Focus on the pure Yang-Mills part of the Lagrangian, we have 
$$
\mathcal{L}_ {\text{eff}} = \int d^{3}x \,  \frac{1}{4g^{2}}F^{2}+\dots.
$$
Now consider the path integral. To find the partition function we need to path-integral over all the fields, over their physically inequivalent configurations. In our case we have 
$$
Z = \int_ {A / G} \mathcal{D}A_ {\mu}\mathcal{D}\dots \, e^{ iS[\mathbf{A}..] }.
$$
where $G$ is the gauge transformation. However, here we can regard the field strength $F = dA$ as the degree of freedom, and do the path integral in terms of 
$$
Z = \int \mathcal{D}F\dots \, e^{ iS[F, \dots] }.
$$
On the one hand, a merit of trading $A$ for $F$ is that, the gauge redundancy is automatically taken care of, since two gauge fields differ by a gauge transformation $A \sim A' = A+dg, g\in G$ yields the same field strength $F$. On the other hand, the Bianchi identity $dF = ddA\equiv 0$ is not automatically  satisfied anymore. We have traded one redundancy for another! 

The solution to that problem is to force the Bianchi identity via a Lagrange multiplier, which is a scalar field in our case, denoted by $\sigma(x)$. In 3D Minkowski spacetime with metric $g=(+,-,-)$, the action reads
$$
S[F_ {\mu \nu},\sigma] = -\frac{1}{4g^{2}}\int d^{3}x \,  F_ {\mu \nu}F^{\mu \nu}- \frac{1}{8\pi}\int d^{3}x \,  \partial _ {\mu}\sigma F_ {\nu \lambda}\epsilon^{\mu \nu \lambda}
$$
where the integral by parts has been performed. If we integrate over $\sigma(x)$ first we restore the Bianchi identity for $F$ thus the original theory. 

**However, we could also choose to integrate over $F$ first**, leaving as a theory in terms of $\sigma(x)$. Solve the equation of motion for $F$ we get
$$
F^{\mu\nu} = - \frac{g^{2}}{4\pi}\epsilon^{\mu \nu \lambda}\partial _ {\lambda}\sigma
$$
and substitute it back to the action we have 
$$
\boxed{
S[\sigma] =  \frac{g^{2}}{32\pi^{2}}\int d^{3}x \, (\partial \sigma) ^{2}.
}
$$
**Notice the change of the position of the coupling!** We will call $\sigma$ the `dual photon field` and the action the `magnetic description` or `dual description`, the use of magnetic in the calling will become clear in the future.

We notice that the spatial derivative of $\sigma$
$$
\partial _ {i} \sigma = \frac{g^{2}}{2\pi}\epsilon^{ij}E_ {j}
$$
corresponds to the electric field, similar to the potential. The time derivative of $\sigma$, on the other hand, represents the $F^{12}$ component, the only magnetic field component on $\mathbb{R}^{1,2}$. 

The dual photon theory has a global symmetry under which σ shifts by a constant. The corresponding Noether current is 
$$
j^{\mu} \sim  \partial ^{\mu} \sigma
$$
which maps to 
$$
j^{\mu} \sim  \epsilon^{\mu \alpha \beta}F_ {\alpha \beta},\quad  \partial _ {\mu}j^{\mu}= \epsilon^{\mu \alpha \beta} \partial _ {\mu}F_ {\alpha \beta}=0.
$$
This corresponds to the Bianchi identity $dF=0$  in the original theory.

The charge corresponding to the $\sigma$-shift symmetry is
$$
Q\sim \int d^{2}x \, j^{0} \sim \int d^{2}x \, \partial ^{0}\sigma  \sim  \int d^{2}x \, B  
$$
where the integral is over $d^{2}x$ since we are only integrating over the space in 3D spacetime. 

We will see that after the canonical quantization of the dual field theory, the state 
$$
e^{ i\sigma (x)}\left\lvert{0}\right\rangle =\text{ the eigen state of }Q=1.
$$

In quantum mechanics, canonical quantization is a recipe that takes us from the Hamiltonian formalism of classical dynamics to the quantum theory. The recipe tells us to take the generalized coordinates and their conjugate momenta and promote them to operators. The Poisson bracket structure of classical mechanics morphs into the structure of commutation relations between operators, so that
$$
[q_ {a},p^{b}] := i \delta_ {a}^{b}.
$$
In field theory we do the same. A quantum field is an **operator valued function of space** (not space-time!) obeying the commutation relations
$$
[\phi(x),\pi(y)] = i \delta^{d} (x-y), \quad  d \text{ is the space dimension.}
$$
In our case, we have the action 
$$
\boxed{
S[\sigma] =  \frac{g^{2}}{16\pi^{2}}\int d^{3}x \, (\partial \sigma) ^{2}.
}
$$
so let's try to define 
$$
[\sigma(x), \dot{\sigma}(y)]=i\delta^{2}(x-y),
$$
then we have 
$$
Qe^{ \pm i \sigma(x) }\left\lvert{0}\right\rangle  = \pm e^{ \pm i \sigma(x) }\left\lvert{0}\right\rangle ,
$$

thus $e^{ i\sigma(x) }$ acting on the vacuum creates a local state with unit magnetic flux. 

Note the $e^{ i\sigma }$ has no simple, local expression in the electric version of the theory. This is an example of a “disorder” operator which does not have a local expression in terms of the electric theory fields.

The Gauss's theorem tells that the electric charge in a region in $\mathbb{R}^{2}$ circled by loop $C$ is given by $\int_ {C} \,  \nabla \cdot \mathbf{E}$, in the language of the magnetic theory we have $E_ {i} \sim\epsilon_ {ij} \partial_ {j}\sigma$, thus the charge is given by 
$$
Q \sim \int d^{2}x \, \nabla \cdot \mathbf{E} \sim \int d^{2}x \,  \nabla \times (\nabla \sigma)=  \oint_ {C} \nabla \sigma \cdot dl,
$$
where $dl$ is the line segment along the circle. It means that around a charge $Q$, the dual photon field has non-zero monodromy (not single-valued). It is quite natural since 1) $\sigma$ appears in the exponent in the operator and 2) only its derivative appears in the Lagrangian. 

The insertion of a static charge is quite simple in the original theory, by the means of the Wilson loop. However, in the dual theory, it is much complicated. We will have to realized the insertion by allowing only certain types of the $\sigma$ field configuration, namely that give the correct monodromy. It is similar to what we get when we want to insert a monopole in the Yang-Mills theory. 

The claim (not mine) is that the insertion of the operator $e^{ \pm i\sigma(x) }$ where $x\in\mathbb{R}^{3}$ corresponds to the configuration where a monopole-instanton sits at $x$. To begin with, we introduce the source term for $\sigma$ field, and the generating functional in the Euclidean space reads 
$$
\Gamma[\rho(x)]:= \mathcal{N} \int \mathcal{D}\sigma \,  e^{ -S +\int d^{3}x \,\rho(x)\sigma(x)  }
$$
which is a standard procedure in QFT, it yields 
$$
\Gamma[\rho(x)] = \exp\left( -\frac{g^{2}}{8\pi} \int \,   d^{3}xd^{3}y \,\rho(x) \frac{1}{\left\lvert x-y \right\rvert} \rho(y) \right)
$$