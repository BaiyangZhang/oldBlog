---
layout:     post   				        # 使用的布局（不需要改）
title:      Confinement in Toy Models 	# 标题 
subtitle:   Lecture      # 副标题
date:       2023-3-21			        # 时间
author:     Baiyang Zhang 				# 作者
header-img: img/background3.jpg 	        # 这篇文章标题背景图片
catalog: true 						    # 是否归档
tags:								    # 标签
    - math
    - quantum field theory
    - confinement
---

First let's take a look at the SU(2) Georgi-Glashow model defined on **Euclidean** $\mathbb{R}^{3}$. This is the so-called `Polyakov model`. 

The ingredients for the Polyakov model is as follows.
1. The gauge group is set up to be SU(2). That is the simplest gauge group possible that admits non-trivial soliton solutions in $\mathbb{R}^{3}$. 
2. The degrees of freedom, namely the basic "particles", are the massless SU(3) gauge bosons and **adjoint, real** Higgs bosons, which lives in the adjoint representation of the gauge group. At least it is the case at high energy. At low energy we will have a spontaneous symmetry breaking and the spectrum (namely, the particles content of the theory) will be different.

As usual the gauge field is denoted $A_ {\mu}^{a}$ where $a$ is the group index and $\mu$ the space-time index. The real scalar is usually labeled $\phi$, but for further convenience we may also label it $A_ {4}$, in this note we will use then interchangeably. Note that $\phi$ is not just one scalar field but three, come in the triplet of the gauge group. There are three generator for SU(2) group thus we have three Higgs scalars, denoted $\phi^{1,2,3}$. They can be concisely written as $\phi = \phi^{a} T^{a}$, where $T^{a}=\sigma^{a} / 2$ are the three 2-dimensional generators for SU(2), which are half the Pauli matrices. For more conventions about the notation, refer to the other note I wrote titled something like "Conventions".

The Lagrangian (we don't distinguish Lagrangian from Lagrangian density) is defined to be
$$
\mathcal{L} = \frac{1}{g^{2}} \left( \frac{1}{2}\mathrm{Tr}\,F^{2} + \mathrm{Tr}\,(D\phi)^{2}+\lambda(\phi^{a}\phi^{a}-v^{2})^{2}\right)
$$
where $g$ is the gauge coupling, trace is defined in the group space, namely it is over $T^{a} \phi^{a}$, and $\lambda$ is another coupling. The Einstein summation conventions is understood.

Let us look at the dimensions in $d$-dimensional spacetime. In our convention, we have $D = \partial - iA$ thus $A_ {\mu}$ always has the dimension of the mass, let's write it is $[A]=1$. We know that $[S] = \left[ \int d^{d}x \, \mathcal{L} \right]=0$, thus $[\mathcal{L}]=d$ in units of mass dimension. Let's take a look at the gauge boson self-energy term, 
$$
d = \left[ \frac{1}{g^{2}} \mathrm{Tr}\,F^{2} \right] = -2[g] + 2[F] = -2[g] + 2[\partial A] = -2[g]+2(1+[A])
$$
but we know $[A]=1$ thus
$$
d = -2[g]+4 \implies [g] = - \frac{d-4}{2}.
$$
In our case, $d=3$ thus $[g^{2}]=1$. Then the dimension of the rest operators follows directly. As a result we have
$$
\boxed{
[A]=1,\quad [g^{2}]=4-d,\quad [\phi]=1,\quad [\lambda]=d-3.
}
$$
This result is different in the conventions used by, e.g., Peskin&Schroeder, where $[\phi]=(d-2) / 2$. **In our convention, only the dimension of couplings depends on the spacetime dimension $d$.**

In our case the Polyakov model, we have $[A]= [g^{2}]=[\phi]=1$ and $[\lambda]=0$. 

Note the position of $g^{2}$, it replaces $\hbar$ in the front of the Lagrangian! We are tempted to say that $g^{2}$ plays the role of $\hbar$, namely when $g^{2}$ is small, then the quantum effects are suppressed. But not quite so, the problem is the dimension, $\hbar$ has dimension zero, but $g^{2}$ is dimension one! Thus the role of $\hbar$ must not be played by $g^{2}$ alone but rather some combination such as $g^{2} L$ where $L$ is some length scale. But what is this length scale? We will say more about it later. 

### Perturbative analysis

We will assume $\lambda$ to be small. 

The vacuum configuration for $A$ is simple, it must be uniformly zero everywhere. The vacuum configuration for $\phi$ is slightly more tricky, to minimize the potential we need
$$
\phi^{a} \phi^{a} =v^{2},\quad  a = 1,2,3
$$
thus the vacuum manifold for $\phi$ is $\mathbb{S}^{3}$ with radius $v$. 

The routine of perturbative analysis is that, we first choose one specific vacuum point in the vacuum manifold, any point would do. Then we expand all the fields about that chosen vacuum point, thus obtain the perturbative Lagrangian. Now let's do that. 

Choose the vacuum $\phi^{1}=\phi^{2}=0, \phi^{3}=v$. Expanding around it is easy to see that 
- The gauge symmetry is broken $SU(2)\to U(1)$,
- Only one massless gauge boson left, namely $A_ {\mu}^{3}$,
- $\phi^{1,2}$ are eaten and results to massive $W^{\pm}$ bosons appear, given by $A^{1}\pm A^{2}$, with mass of order $\sim v$.
- The massive Higgs boson has mass of order $\sim \sqrt{ \lambda }v$. If $\lambda \sim 1$ then it is of the same order as the W bosons.

The philosophy is that, the original SU(2) Lagrangian describes a system at high energy. Higher the energy, stronger the fluctuation of the fields, further will $\phi^{i}$ deviate from (any of) its vacuum configuration in average, larger the variance $\left\langle \phi^{2}-\left\langle \phi \right\rangle^{2} \right\rangle$. This is similar to what happens to the Ising model, when the temperature increases, the fluctuation of the spins also gets stronger and eventually causes the phase transition. In the Polyakov model, at high energy the vev of $\phi$ could be any value and it doesn't make a lot of sense to expand it about the vev; while the energy decreases, the fluctuation gets smaller and two things are different from the high energy case, 1) the vev of $\phi$ approaches some vacuum point and 2) it starts to make sense to expand $\phi$ about its vev. As a result we have a smaller gauge group at lower energy. The parameter $v$ can be used to signature the transition scale approximately, thus is sometimes called the `abelianization` scale. 



