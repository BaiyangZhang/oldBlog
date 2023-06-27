---
layout:     post   				    # 使用的布局（不需要改）
title:     Note-on-Quantization-of-Skyrme-Model 			# 标题 
subtitle:   based on Adkins1983, Manko2007, etc.
date:       2023-06-27 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background1.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 
---

# Static Properties of Nucleons in the Skyrme Model

## Introduction

In his 1973 paper "A planar diagram theory for strong interactions", 't Hooft treated the parameter $N$ in the gauge group $SU(N)$ or $U(N)$ as a free parameter, and explained that in the $N\to \infty$ limit, the Feynman diagrams arrange into sets with different topological structure according to its contribution in powers of $1 / N$. For the sake of simplicity he didn't require the trace of the ${\frak g}$-valued gauge field $A$ to be traceless, thus instead of $SU(N)$ the gauge group is actually $U(N)$. As a result there will be an extra photon corresponding to the $U(1)$ component of $U(1)$, which will be discarded at the last step. 't Hooft introduced the double-line notation and each closed group index circle will generate a factor of $\delta^{i}_ {i}=N$, making it convenient to count the factor of $N$ of a given Feynman diagram. Based on this, 't Hooft made use of the Euler theorem saying that $\chi=2-2g$ where $\chi$ is the Euler characteristic and $g$ the genus of a manifold, and reached the conclusion that, if $g^{2}N$ is kept fixed at large $N$, then *the planar diagrams with genus zero and one  dominate*. That is, to treat the double-line Feynman diagrams as the boundary of a manifold, then we cal talk about the genus of it. *Regarding non-planar diagrams, each "handle" pay a price $1 / N^{2}$*.

Large $N$ really plays an important rule in SU($N$) gauge theory. Large $N$ limit turns out to be pretty helpful in understanding the nonperturbative and phenomenological aspect of field models. In large N limit, the coupling is made $N$-dependent in such a way that the large $N$ limit exists and is nontrivial, duh. 

Speaking of QCD specifically, we have 
$$
\beta(g) = - \frac{1}{16\pi^{2}}\left( \frac{11}{3}N - \frac{2}{3}N_ {f} \right)g^{3}
$$
and the 't Hooft coupling, which is required to be fixed at large $N$, is 
$$
\lambda = g^{2}N.
$$
Usually the 't Hooft expansion is defined to be the limit $N\to \infty$ with $\lambda$ kept fixed.

It is said that *counting rules suggest that baryons may emerge as solitons in large QCD theory.* The large $N$ theory of mesons, at low energy, reduces to non-linear sigma model, but how? And what does the Wess-Zumino coupling has to do with it?

## The Non-linear Sigma Model

The non-linear sigma model, sometimes written as NL$\sigma$M or NLSM, is a scalar field theory where the target space (where the field takes value) is a non-linear manifold. It's called $\sigma$ model because originally Gell-Mann and Levy used $\Sigma$ to denote the scalar field. NLSM is a precursor of modern day QCD, even now it still serves as a good low-energy approximation, namely low energy effective theory of QCD, where quarks are negligible. NLSM is an effective of spin-zero scalar, in real world pions. 

There are three types of pions,
$$
\begin{cases}
\pi^{+}: &  u\overline{d} \\
\pi^{0}: & \frac{1}{\sqrt{ 2 }}(u\overline{u}+d\overline{d}) \\
\pi^{-}: & \overline{u}d
\end{cases}
$$
which will be the degree of freedoms in the NLSM. 

There is a clever way to combine the three scalars together to form a compact model. Let $U(x)$ be a $SU(2)$ matrix, we can "stuff" the pion fields into $U(x)$ by writing 
$$
U(x) = \exp(i\pi^{a}\sigma^{a} / f_ {\pi})
$$
where $\sigma^{a}$ are the Pauli matrices, and $f_ {\pi}$ is the pion decay constant. In 4D the scalar field has dimension 
$$
[\pi] = \frac{d-2}{2} = 1
$$
therefore $f_ {\pi}$ should also has the dimension of mass, such that the argument of the exponential function is dimensionless.

We can Taylor expand the exponential function, and by making use of the properties of Pauli matrices such as 
$$
\sigma^{a} \sigma^{b} = \delta^{ab} + i \epsilon^{abc} \sigma^{c}
$$
we get
$$
\exp\{ i\pi \cdot \sigma / f_ {\pi} \} = \cos(\pi / f_ {\pi})\mathbb{1} + i \sin(\pi / f_ {\pi}) \hat{\pi}\cdot \sigma,\quad  \pi := \left\lvert \mathbf{\pi} \right\rvert .
$$
This form makes the symmetry of the Lagrangian manifest. 

We also want the NLSM to adopt the chiral symmetry, that is the $SU(2)_ {L} \times SU(2)_ {R}$ global symmetry. Let $L,R\in SU(2)$ then the chiral symmetry acting on $U$ is 
$$
U \to L U R^{\dagger}.
$$

The simplest dynamic, renormalizable Lagrangian in terms of $U$ satisfying the chiral symmetry reads
$$
\mathcal{L} = \frac{f_ {\pi}^{2}}{4} \mathrm{Tr}\,(\partial_ {\mu}U \partial^{\mu}U).
$$
The normalization coefficient is such that, if you expand $U$ in terms of sin and cos functions, the pion fields adopt the correct dynamic term,
$$
\mathcal{L} = \frac{1}{2}\partial_ {\mu}\phi \partial^{\mu}\phi + \dots.
$$

- - -

The chiral symmetry is a symmetry of the Lagrangian, thanks to the trace, but is it the symmetry of the vacuum? Setting the vacuum to be $\left\langle \pi \right\rangle=0$, which means 
$$
\left\langle U \right\rangle=\mathbb{1},
$$
under the chiral transformation we have 
$$
\left\langle U \right\rangle=\mathbb{1} \to \left\langle L U R^{\dagger} \right\rangle = L \mathbb{1} R^{\dagger} = L R^{\dagger},
$$
which equals to $\mathbb{1}$ iff $LR^{\dagger}=\mathbb{1}\implies L = R$, then the chiral transformation breaks to 
$$
SU(2)_ {L}\times SU(2)_ {R} \to SU(2)_ {V}
$$
where $V$ is for vector. In other words, *the chiral symmetry is spontaneously broken to $SU(2)$.*






## Classical Skyrme Model

Let $N_ {f}=2$. Consider the simplest Skyrme model
$$
L = \frac{1}{16}F_ {\pi}^{2} \,\mathrm{Tr}\,(\partial _ {\mu}U\partial ^{\mu}U^{\dagger})+\frac{1}{32e^{2}}\mathrm{Tr}\,[\partial _ {\mu}U U^{\dagger},\partial _ {\nu}U U^{\dagger}]^{2}
\tag{1}
$$
where we have adopted the convention that the derivative acts on the first term followed by it only. 

The second term is to stabilize the Skyrmion solution. Now, why we need to stabilize it in the first place? It is because, Derrick's scaling argument, or Derrick's theorem says that, if the Lagrangian of a scalar field can be written as 
$$
\mathcal{L} = \frac{1}{2} \partial_ {\mu}\phi \partial^{\mu}\phi - V(\phi)
$$
which is very general, then given a localized wave-pack like classical solution to the equation of motion, call it $\phi_ {0}(x)$, for dimension $\geq 2$, we can always shrink the solution to
$$
\phi_ {\lambda} (x) = \phi_ {0}(\lambda x), \quad  \lambda>1,
$$
and reduce the energy, thus $\phi_ {0}$ can not be stable. In the case of Skyrme model we don't have a scalar field but this conclusion still holds, as can be shown by writing down a solution and the energy functional, and study what happens if the soliton is shrunk. Therefore, to stabilize the soliton solution, we need extra terms in the Lagrangian involving the derivatives. 

- - -

Recall that $U$ is a SU(2) matrix, under the chiral transformation 
$$
U \to LUR^{-1}, \quad  L, R \in SU(2).
$$
$F_ {\pi}=186 \text{ MeV}$ is the pion decay constant, $e^{2}$ is a dimensionless parameter. The last term, the trace of a commutator, was first introduced by Skyrme to stabilize the soliton solution.

To find the solution of the soliton, we adopt the spherical symmetric ansatz
$$
U_ {0}(x) = \exp[iF(r) \tau \cdot \hat{x}], \quad  F(r){\Large\mid}_ {r=0} =\pi,\,F(r){\Large\mid}_ {r=\infty} =0.
$$
Take it to the Lagrangian, Legendre transform the Lagrangian to energy functional, we have the expression of the energy of the soliton in terms of the profile funciton $F(r)$:
$$
M = 4\pi \int_{0}^{\infty} dr \, r^{2}\left\{ \frac{1}{8}F_ {\pi}^{2}\left[ (\partial _ {r}F)^{2}+2\frac{\sin ^{2}F}{r^{2}} \right] + \frac{1}{2e^{2}} \frac{\sin ^{2}F}{r^{2}}
\left[ \frac{\sin ^{2}F}{r^{2}}+2(\partial _ {r}F)^{2} \right]\right\} , 
\tag{2}
$$
Then we can obtain the variational equation from it, then we can further solve it numerically. Introduce the dimensionless parameter $\widetilde{r}:= eF_ {\pi}r$, the equation of motion reads
$$
\left( \frac{1}{4}\widetilde{r}^{2}+2\sin ^{2}F \right)F'' + \frac{1}{2} \widetilde{r} F' + \sin (2F) F'^{2}- \frac{1}{4}\sin(2F) - \frac{\sin ^{2}F \sin 2F}{\widetilde{r}^{2}}=0.
$$

Now we can make use of the *global* $SU(2)$ symmetry of the Lagrangian, namely if $U_ {0}$ is a soliton solution, then
$$
U = A U_ {0} A^{-1}
$$
is also a soliton solution. Thus we have a space of solutions parametrized by $A$, by parametrization we mean that there is a map
$$
A \to \text{space of soliton solutions}.
$$

### Quantization

To study the spin and isospin of a soliton, we need to quantize the soliton solution, by thinking of $A$ as a quantum mechanical variable, which is the collective coordinates. 

Since the collective coordinates parameterize the solution space, a.k.a. moduli space, we now have a means to describe the motion of a soliton. Every point in the moduli space corresponds to a specific soliton solution, then a trajectory of a soliton would ideally be denoted by a curve in the moduli space. The converse would also hold in the ideal case, namely a curve in the moduli space would give us uniquely a soliton trajectory. It would be nice if there exists a one-to-one correspondence between the curves and the soliton trajectory. It should indeed be the case if no discrete symmetry jumps out and ruins everything. To be more specific, one way to ruin this bijection between curves in the moduli space and actual soliton trajectory is that if some discrete symmetry is modded out in constructing the moduli space, then there may exist special points where the discrete symmetry can make the soliton trajectory not uniquely defined, these are called `stacky points`, put it short, there exists more than one way for a curve to cross a stacky point. *Could there be stacky points in the moduli space of Skyrmions?* Maybe a related question is, what if the gauge group is $SU(N) / Z_ {N}$ instead of $SU(N)$? Changing the gauge group to $SU(N) / Z_ {N}$ has many consequences, one of them is we have introduced an extra *discrete symmetry*, $Z_ {N}$ symmetry of the gauge group, therefor to the moduli space, and this could make the moduli space not fine anymore, assuming the moduli space of Skyrmion is fine in the first place. Recall that

**Fine moduli space.** A `fine moduli space` is a space $M$, such that
1. the points in $M$ are in 1-2-1 correspondence with *isomorphism classes* of the objects we are studying;
2. (`technical condition`) For every family $\mathcal{F}$ over a topological (parameter) space $T$, denoted by $\mathcal{F} / T$, the associated moduli map $T\to M$, which maps the point $t \in T$ to the isomorphism class of the family member $\mathcal{F}_ {t}$, is *continuous*;
3. Every *continuous map* from $T$ to $M$ is the moduli map of some family parametrized by $T$;
4. if the two families have the same moduli map, they are isomorphic families. 

- - -

To be able to describe the time-dependent rotation (not motion) of Skyrmions, let's make $A$ time dependent, $A\to A(t)$. Then a time-dependent soliton solution is given by
$$
U(t) = A(t) U_ {0} A(t)^{-1}.
$$

Given $U(t)$ in terms of $A(t)$, in theory we can substitute it in the Lagrangian, obtaining a Lagrangian (Hamiltonian, whatever) in terms of $A(t)$. We can then try to diagonalize the Hamiltonian, find the eigenstates. We can then study the spin and isospin of these eigenstates by acting the corresponding operators on it. The eigenstates with proper spin and isospin will correspond to the nucleon and delta.

To be honest, beside having the same quantum numbers, I don't see any reasons why the soliton solutions should be regarded as nucleons, or for that matter any particle we observe in real life. This whole soliton-nucleon identification is supposed to be taken with a grain of salt, I guess.

So, substituting $U = A(t)U_ {0}A^{-1}(t)$ in Eq. (1), by the end of the day we get
$$
L = -M + \lambda \mathrm{Tr}\,(\partial _ {0}A \partial _ {0}A^{-1}), 
\tag{3}
$$
where $M$ is the soliton mass defined in Eq. (2) and 
$$
\lambda = \frac{4}{6} \pi \left( \frac{1}{e^{3}F_ {\pi}} \right)\Lambda,\quad 
\Lambda = \int d\widetilde{r} \, \widetilde{r}^{2} \sin ^{2} F \left[ 1+4\left( F'^{2} + \frac{\sin ^{2}F}{\widetilde{r}^{2}} \right) \right] .
$$
Numerically, Adkins et al. found that $\Lambda = 50.9$. 

Recall the canonical quantization of quantum mechanics is to endow the generalized coordinate $q$, its canonical momentum $p = \partial L / \partial \dot{q}$ a canonical commutation relations, $[p,q]=\text{something}$. How we do it to $A$, a $SU(2)$ matrix? 

We can write 
$$
A = a_ {0} + i \mathbf{a}\cdot \mathbf{\tau},\quad a_ {\mu}a_ {\mu}=1,\quad  \mu=0,1,2,3.
$$
where the summation convention has been adopted. The above equation is a general property for all $SU(2)$ matrices. In terms of $a$'s the Lagrangian becomes 
$$
L = -M + 2\lambda \dot{a}_ {\mu}\dot{a}_ {\mu}\tag{4}.
$$
Now we can introduce the canonical momentum in the standard way, 
$$
\boxed {
\pi := \frac{\partial L}{\partial \dot{a}} \implies \pi_ {i} = 4\lambda \dot{a}_ {i}
} 
$$
and the Hamiltonian becomes
$$
H = \pi_ {i}a_ {i}-L = M + \frac{1}{8\lambda}\pi_ {i}\pi_ {i}.
$$
Recall that in quantum mechanics, during canonical quantization we re-wrote the canonical momentum as a difference operator with respect to $x$, $p := -i \partial_ {x}$, we can do the same to the $a_ {i}$ and $\pi_ {i}$, writing 
$$
\boxed {
\pi_ {i} \to -i \partial /\partial a_ {i}. 
} 
$$
then we can write down $H$ in the "moduli-space representation"
$$
\boxed { 
H = M + \frac{1}{8\lambda} \sum_ {i=0}^{3}\left( -\frac{\partial^{2}}{\partial a_ {i}^{2}} \right),\quad a_ {i}a_ {i}=1.
}
$$

The constraint suggests that $\sum_ {i}\partial^{2} / \partial a_ {i}^{2}$ should be interpreted as the Laplacian $\nabla^{2}$ on $\mathbb{S}^{3}$. By analogy with usual spherical harmonies (where you go to the polar coordinates system and solve the eigenfunction equation, blahblahblah), the eigenfunctions to the Hamiltonian are *traceless symmetric polynomials* in the $a_ {i}$. (I don't know how to prove this) For example, one eigenfunction to the Laplacian is $(a_ {0}+ia_ {1})^{l}$, with
$$
-\nabla^{2}(a_ {0}+ia_ {1})^{l} = l (l+2) (a_ {0}+ia_ {1})^{l}.
$$
Such a wave function has spin and isospin equal to $l / 2$. To see this, consider the spin operator
$$
I_ {k} = \frac{1}{2} i \left( a_ {0} \frac{\partial}{\partial a_ {k}}-a_ {k} \frac{\partial}{\partial a_ {0}}  -\epsilon_ {klm}a_ {l} \frac{\partial}{a_ {m}} \right)
$$
which generalized the 3D angular momentum operator 
$$
\mathbf{l} = \mathbf{x} \times \mathbf{p}, \quad  l_ {k} = -i \epsilon_ {klm}x_ {l} \frac{\partial}{\partial a_ {m}}.
$$
The isospin operator is defined as 
$$
J_ {k} = \frac{1}{2} i \left( -a_ {0} \frac{\partial}{\partial a_ {k}} + a_ {k} \frac{\partial}{\partial a_ {0}}  -\epsilon_ {klm}a_ {l} \frac{\partial}{a_ {m}} \right)
$$
where the terms involving zero component gets an extra minus sign in comparison to the spin operator. 