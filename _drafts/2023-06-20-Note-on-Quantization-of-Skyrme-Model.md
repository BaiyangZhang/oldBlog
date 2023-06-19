---
layout:     post   				    # 使用的布局（不需要改）
title:     Note-on-Quantization-of-Skyrme-Model 			# 标题 
subtitle:   based on Adkins1983, Manko2007, etc.
date:       2023-06-20 				# 时间
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

Let $N_ {f}=2$. Consider the simplest Skyrme model
$$
L = \frac{1}{16}F_ {\pi}^{2} \,\mathrm{Tr}\,(\partial _ {\mu}U\partial ^{\mu}U^{\dagger})+\frac{1}{32e^{2}}\mathrm{Tr}\,[\partial _ {\mu}U U^{\dagger},\partial _ {\nu}U U^{\dagger}]^{2}
\tag{1}
$$
where we have adopted the convention that the derivative acts on the first term followed by it only. As usual, $U$ is a SU(2 matrix), under the chiral transformation 
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

Since the collective coordinates parameterize the solution space, a.k.a. moduli space, we now have a means to describe the motion of a soliton. Every point in the moduli space corresponds to a specific soliton solution, then a trajectory of a soliton would ideally be denoted by a curve in the moduli space. The converse would also hold in the ideal case, namely a curve in the moduli space would give us uniquely a soliton trajectory. It would be nice if there exists a one-to-one correspondence between the curves and the soliton trajectory. It should indeed be the case if no discrete symmetry jumps out and ruins everything. To be more specific, one way to ruin this bijection between curves in the moduli space and actual soliton trajectory is that if some discrete symmetry is modded out in constructing the moduli space, then there may exist special points where the discrete symmetry can make the soliton trajectory not uniquely defined, these are called `stacky points`, put it short, there exists more than one way for a curve to cross a stacky point. Could there be stacky points in the moduli space of Skyrmions?

To be able to describe the time-dependent motion of Skyrmions, let's make $A$ time dependent, $A\to A(t)$. Then a time-dependent soliton solution is given by
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
H = \pi_ {i}a_ {i}-L = M + \frac{1}{8\pi}\pi_ {i}\pi_ {i}.
$$
Recall that in quantum mechanics, during canonical quantization we re-wrote the canonical momentum as a difference operator with respect to $x$, $p := -i \partial_ {x}$, we can do the same to the $a_ {i}$ and $\pi_ {i}$, writing 
$$
\boxed {
\pi_ {i} \to -i \partial /\partial a_ {i}. 
} 
$$
