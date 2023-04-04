---
layout:     post   				        # 使用的布局（不需要改）
title:      Confinement in Toy Models 	# 标题 
subtitle:   Lecture      # 副标题
date:       2023-04-04			        # 时间
author:     Baiyang Zhang 				# 作者
header-img: img/background13.jpg 	        # 这篇文章标题背景图片
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
\boxed{
\mathcal{L} = \frac{1}{g^{2}} \left( \frac{1}{2}\mathrm{Tr}\,F^{2} + \mathrm{Tr}\,(D\phi)^{2}+\lambda(\phi^{a}\phi^{a}-v^{2})^{2}\right),\quad G=SU(2),\quad \phi=\phi^{a} T^{a} \in {\frak g}
}\tag{1}
$$
where $g$ is the gauge coupling, $T^{a}$ is the generator of the gauge group $G$, the trace is defined in the group space, namely it is over $T^{a} \phi^{a}$, and $\lambda$ is another coupling. The Einstein summation conventions is understood.

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

Formally, as in any theory with dimensionful coupling constant, one can define a dimensionless coupling using an appropriate power of the relevant energy scale. This energy scale can be approximated to the reaction energy, then it tells us how the coupling changes when the energy increases or decreases.

Let's take $v^{2}$ to extremes and see what happens. If $v^{2}\to 0$ or negative, then there will be no spontaneous symmetry breaking (SSB), we have a SU(2) gauge theory in IR, similar to the QCD. The coupling will flow to high values at low energy. On the other hand, if $v^{2}$ is large, much larger than $g^{2}$, it turn out that the **abelianization of the theory stops the running of the coupling towards large values in the IR**. There is only the $A^{3}_ {\mu}$ photon and there are no U(1)-charged particles that are light. At energy much less than $v^{2}$ the theory is weakly coupled, and we claim the effective theory has the form
$$
\mathcal{L}_ {\text{eff}} = \frac{1}{4 g^{2}} \widetilde{F}^{2} \left( 1+C \frac{g^{2}}{v} \right)+\dots,\quad  \widetilde{F}_ {\mu \nu}:=F^{3}_ {\mu \nu},
\tag{2}
$$
where $\widetilde{F}$ is the massless part of the gauge field at low energy, and $C$ is some numerical coefficient. We just ignore the terms involving massive fields since they are assumed to be much much heavier than our working-scale and thus decouples from the dynamics. This is equivalent to the “tree-level” integrating out the heavy fields; here, it amounts to crossing them out. The second term in the brackets can be seen as the result of the calculation of the one-loop graph, where the photon is couple to both $W^{+}$ and $W^{-}$, the vertex contribute a factor $1 / g^{2}$ while the propagator of the $W$ bosons contribute a factor of $g^{2} / (k^{2}+v^{2})$. Thus the one-loop contribution is roughly 
$$
\int  \, \frac{d^{3}k}{(k^{2}+v^{2})^{2}} \sim  \frac{1}{v}.
$$

The higher order terms in Eq.(2) are suppressed by the W-boson mass $v$. 

- - -

**Finite action monopole-instantons in the Polyakov model**

It turns out to be a big surprise that the proliferation in the vacuum that ultimately causes confinement of fundamental charges.

**To simplify the calculation we will work in the $\lambda\to 0$ limit. This is sometimes known as the “Bogomolny-Prasad-Sommerfield,” or BPS limit.** In this limit, we can simplify the expressions further by introducing a four dimensional expression. The Polyakov model is 3-dimensional, but we can treat the scalar field $\phi$ as a component of the gauge field $A_ {\mu}$. To be specific, let's use the capital Latin letters to denote 4D space indices, $M,N=1,2,3,4$. Extend the metric from 3D Euclidean to 4D Euclidean. Then in the $\lambda\to 0$ limit, assuming that $A_ {1,2,3}$ are independent of the fourth dimension, namely $\partial_ {4}A_ {i}=0$ for $i=1,2,3$, we have 
$$
\frac{1}{2g^{2}} \mathrm{Tr}\,F_ {MN}F^{MN} = \frac{1}{2g^{2}} \mathrm{Tr}\,F_ {\mu \nu}F^{\mu \nu}+ \frac{1}{2g^{2}} \mathrm{Tr}\,D_ {\mu}\phi D^{\mu }\phi,\quad  \phi \equiv A_ {4}.
\tag{3}
$$

**The scalar field has become the fourth component of the gauge field.** This is possible because the Higgs field $\phi$, just like the gauge field, are Lie-algebra-valued fields.

Similar to the electro-magnetic case, we can define the non-abelian "magnetic" and "electric" fields as 
$$
\boxed{
E_ {\mu} \equiv F_ {\mu 4}=D_ {\mu}A_ {4},\quad  B_ {\mu} \equiv \frac{1}{2} \epsilon_ {\mu \nu \rho}F^{\nu \rho}.
}
$$
Note that in the non-abelian case, $E$ and $B$ are gauge dependent thus can't be physical observables.

Now we can rewrite Eq. (3) in terms of $E$ and $B$, and we can call Eq. (3) the Lagrangian since we have assumed the $\lambda\to {0}$ limit,
$$
L = \frac{1}{2g^{2}} \mathrm{Tr}\,F_ {MN}F^{MN} = \frac{1}{2g^{2}} \mathrm{Tr}\,F_ {\mu \nu}F^{\mu \nu}+ \frac{1}{2g^{2}} \mathrm{Tr}\,D_ {\mu}A_ {4} D^{\mu }A_ {4}= \frac{1}{g^{2}}\mathrm{Tr}\,(B^{2}+E^{2}),
\tag{4}
$$
then we can adopt the conventional trick, that is to complete the square
$$
g^{2}L = \mathrm{Tr}\,(B^{2} \mp 2BE + E^{2} \pm 2BE) = \mathrm{Tr}\,\left\{ (B \mp E)^{2} \pm 2BE \right\} \geq \pm \,\mathrm{Tr}\,(2BE),
$$
This is the familiar BPS bound for solitons,
$$
S = \int d^{3}x \, L \geq \pm  \frac{1}{g^{2}}\int d^{3}x \, E_ {\mu}^{a} B_ {\mu}^{a} =: S_ {\text{BPS}}  .
$$

To me, it is actually not obvious that Eq. (4) gives the minimum of the actions, since after completing the square we have two parts, $(\dots)^{2}$ and $2BE$, both are variables, both depends on the gauge field $A$. However it can be shown that the integral over $\mathrm{Tr}\,2BE$ gives a topological invariant that is immune to the local, continuous change of the field configuration, Eq.(3) is actually close to something like $(A_ {\mu}\text{-dependent})^{2}+C\times \text{winding number}$ where $C$ is some numerical constant. Hence if the square gives zero, then the action is indeed minimized (in some topological sector, of course). Thus, without specific calculation, we can conclude that the field configuration that minimizes the square, namely that satisfies the so-called BPS equation (called `(anti)-self-dual`, depending on whether it is plus or minus sign in the following expression)
$$
E = \pm B
$$
automatically satisfies the equation of motion since it gives a minimum of the action. There will be other solutions of the equation of motion, such as saddle points, that do not satisfy the BPS equation.

To buttress the claim that $\int  \, EB$ is a topological invariant, notice that, with the equation of motion $D_ {\mu}B_ {\mu}=0$, we have
$$
\int  \,\mathrm{Tr}\, BE = \int  \, \mathrm{Tr}\,B_ {\mu} D_ {\mu}A_ {4} = \int  \, \mathrm{Tr}[\,D_ {\mu}(B_ {\mu}A_ {4})   -  A_ {4}D_ {\mu}B_ {\mu}] = \int  \, \mathrm{Tr}\,D_ {\mu}(B_ {\mu}A_ {4})
$$
Substitute $D = \partial - i[A,-]$ we get
$$
\int  \, \mathrm{Tr}\,(\partial _ {\mu}(B_ {\mu}A_ {4})  - i[A_ {\mu},B_ {\mu}A_ {4}])=\int  \, \mathrm{Tr}\,\partial _ {\mu}(B_ {\mu}A_ {4}) - i \int  \, \mathrm{Tr}\,[A_ {\mu},B_ {\mu A_ {r}}]  
$$
where the last term vanishes due to the cyclic property of trace. Thus we have 
$$
\int d^{3}x  \,\mathrm{Tr}\, BE = \int d^{3}x \, \mathrm{Tr}\,\partial _ {\mu}(B_ {\mu}A_ {4}) = \int  d^{2} S_ {\mu} \, B_ {\mu}A_ {4}\tag{5}
$$
where $d^{2}S_ {\mu}$ is the surface measure. Note that although we used the equation of motion in deriving Eq. (5) above, but since it is a surface term, it is immune to local smooth change to the field configuration, thus Eq. (5) also holds for any field configuration, as long as they are in the same topology class, the same homotopy class, to be exact.

- - -

It is in general difficult to find the general solutions to the equation of motion, but we have two advantages, 
1. in stead of the second order equation of motion, we have the first order equation, namely the BPS equation.
2. We have various symmetry at hand which simplifies the solution.

Let us look at spherically symmetric solutions first, the solution is sometimes named the `BPS monopoles`. The solution centered at $x=0$ is 
$$
\phi^{a} = A^{a}_ {4} = - \hat{n}_ {a} vP(vr),\quad A_ {\mu}^{a} = \epsilon_ {a\mu \nu}n_ {\nu} \frac{1-A(\nu r)}{r},
$$
where $\hat{n}$ is the unit vector component, $\hat{n}\equiv \mathbf{r} / r$. $P,A$ are functions to be determined of $vr$, a dimensionless parameter. We have 
$$
\begin{align}
P(t) &= \coth t - \frac{1}{x} \to 1- \frac{1}{x}, \\
A(t) &= \frac{x}{\sinh x} \to xe^{ -x }.
\end{align}
$$

The field strength can be calculated straightforwardly, the explicit form of which will not be shown here. We only mention that the solution has a characteristic core size $\sim v^{-1}$ and in the core the solution is quite complicated, while far from the core the solutions simplifies a lot, 
$$
B_ {\mu}^{a}=E_ {\mu}^{a}\to\sim - n_ {\mu} n_ {a} / r^{2},
$$carrying the unit vectors in two spaces: the physics space and the group space. It enables us to calculate the action of a BPS monopole using the surface integral, 
$$
S_ {\text{BPS}} = \int  d^{2} S_ {\mu} \, B_ {\mu}A_ {4}\tag{5} = \frac{4\pi \nu}{g^{2}} = S_ {\overline{\text{BPS}}}.
$$

- - -

OK, we have found the simplest solutions for the BPS equation, but the problem is that this solution depends on the gauge fields, and gauge fields are gauge dependent, and the BPS solution is also gauge dependent. Since gauge is a local rotation in the group space, we can choose a gauge such that at the boundary, on each point the direction in the group space is the same.

If we defined the unbroken $U(1)$ gauge field to be the component that is parallel to $\phi$, then $S_ {\text{BPS}} = 4\pi \nu / g^{2} \left\lvert Q_ {m} \right\rvert$ where $Q_ {m}$ is the U(1) magnetic charge.

Outside of the core of the monopole (of size $\nu^{-1}$), the solution is largely determined by the U(1) component. There will be both electric and magnetic field dominating outside of the core. 


### Monopoles changes the perturbative picture

Since the monopole has size essentially around $\nu^{-3}$, the proliferation of it in $\mathbb{R}^{3}$ of size $V$ would be around
$$
\sim V\nu^{3} e^{ -S_ {0} }, \quad  S_ {0} := S_ {\text{BPS}} = \frac{4\pi \nu}{g^{2}}.
$$
To get an idea about the effect of this non-perturbative fluctuation, let us study the gauge-invariant two-point field-strength correlation function, say $\left\langle B^{3}(x)B^{3}(y) \right\rangle$. First note that, in the matrix form,
$$
F_ {MN}F^{MN} = 2(B^{2}+2E^{2}), \quad  B_ {.} = \frac{1}{2} \epsilon_ {\dots} F^{..},\quad E_ {\mu}=F_ {\mu_ 4},
$$
where I have used the dots for the indices, due to my laziness. Then the correlation function calculated perturbatively is 
$$
\left\langle B^{3}(x)B^{3}(y) \right\rangle = \int DA \, e^{ -S } B^{3}(x)B^{3}(y)
$$
where 
$$
S = \frac{1}{g^{2}} \int d^{3}x \,  (B^{2}+E^{2}).
$$
To find the correlation function of $B$, we can regard it as the degree of freedom and forget about $E$ in our calculation. Then the  propagator in momentum space is the inverse of the coefficients in $\text{field}^{2}$, for example if the Lagrangian has the form $\phi(\nabla^{2}+m^{2})\phi$ then the propagator in momentum space is inverse of $\nabla^{2}+m^{2}=-p^{2}+m^{2}$. In our case we just have the inverse of $1 / g^{2}$, namely $g^{2}$, thus
$$
\left\langle B^{3}(x)B^{3}(y) \right\rangle = \int \frac{d^{3}k}{(2\pi)^{3}}e^{ ik\cdot (x-y) } \,  = \frac{g^{2}}{2\pi (x-y)^{3}} \sim  \frac{g^{2}}{(x-y)^{3}}.
$$

That is the perturbative contribution. As per our discussion above, the monopole fluctuation can also appear and contribute to this two-point function, that is another reason why we choose to calculate the vev of the magnetic field, because it is easy to calculate the monopole contribution to it. Recall that an monopole at $\mathbf{r}$ far away from $\mathbf{x}$ contribute
$$
B^{3}_ {\text{1-mono}} \sim \frac{\mathbf{x-r}}{(\mathbf{x-r})^{3}}
$$
Thus the 1-instanton contribution to the two point function is given by 
$$
\left\langle B^{3}_ {\mu}(x)B^{3}_ {\mu}(y) \right\rangle = \nu^{3} e^{ -S_ {0} }\int d^{3}r \, \frac{\mathbf{x-r}}{(\mathbf{x-r})^{3}} \cdot \frac{\mathbf{y-r}}{(\mathbf{y-r})^{3}} 
$$
Substitute 
$$
\mathbf{\rho} \equiv \frac{\mathbf{r-x}}{\left\lvert \mathbf{y-x} \right\rvert }
$$
and define the unit vector $\hat{n}=(\mathbf{x-y}) / \left\lvert \mathbf{x-y} \right\rvert$. To simplify the notations, write $l = \left\lvert y-x \right\rvert$, we have $d^{3}\rho = d^{3}r / l^{3}$ and the integral becomes
$$
\int d^{3}r \, \frac{\mathbf{x-r}}{(\mathbf{x-r})^{3}} \cdot \frac{\mathbf{y-r}}{(\mathbf{y-r})^{3}} = \frac{1}{l} \int d^{3}\rho \,  \frac{\rho \cdot (\rho+\hat{n})}{\rho^{3}\left\lvert \rho+\hat{n} \right\rvert^{3} }.
$$
Switch to the spherical coordinates, let the $z$-axis coincide the inter-charge axis we have
$$
\frac{1}{l} \int d^{3}\rho \,  \frac{\rho \cdot (\rho+\hat{n})}{\rho^{3}\left\lvert \rho+\hat{n} \right\rvert^{3} } = \frac{1}{l} \int d\rho d\cos \theta d\phi \,  \rho^{2} \times  (\text{some function of }\rho \text{ and }\cos \theta).
$$

Next, substitute $u=\cos \theta$ and $-\sin \theta d\theta=du$, use Mathematica, we finally arrive at
$$
\int d^{3}r \, \frac{\mathbf{x-r}}{(\mathbf{x-r})^{3}} \cdot \frac{\mathbf{y-r}}{(\mathbf{y-r})^{3}} = \frac{1}{\mathbf{x-y}}
$$
which is the potential between the two charges! 

Finally, we conclude that the 1-monopole contribution is 
$$
\boxed{
\left\langle B^{3}_ {\mu}(x)B^{3}_ {\mu}(y) \right\rangle_ {\text{1-mono}} \sim 
g^{2}\left( \frac{1}{\left\lvert \mathbf{x-y} \right\rvert^{3} } + C \frac{v^{3}e^{ -S_ {0} }}{\left\lvert \mathbf{x-y} \right\rvert } \right).
}
$$