---
layout:     post   				        # 使用的布局（不需要改）
title:      Confinement in Toy Models  	# 标题 
subtitle:   Lecture 1      # 副标题
date:       2023-3-21			        # 时间
author:     Baiyang Zhang 				# 作者
header-img: img/background2.jpg 	        # 这篇文章标题背景图片
catalog: true 						    # 是否归档
tags:								    # 标签
    - math
    - quantum field theory
    - confinement
---

### Motivation


In QCD, we just don't know for sure why quarks and gluons, the fundamental fields of the theory, don't show up in the spectrum, as asymptotic particle states. It is widely agreed upon that there should exists formation of color flux tubes among quarks and antiquarks, eventually these flux tubes will fragmentate into mesons and baryons, but there no general agreement about how this is happening. It also means that we don't know enough about non-abelian gauge theories, SU(3) especially, at large distance. 

Historically, the word `confinement` originally referred to the fact that quarks and gluons appear to be trapped inside mesons and baryons, from which they cannot escape. But many meanings can be attached to the word, it is surprisingly subtle. Although the confinement problem is far from being solved, there is much known about the confining force, various models had been developed. 

#### Ising model

Confinement in non-abelian gauge theory involves the idea that the vacuum state is disordered at large scales. But first we need to explain what is meant by a disordered state. Disordered states appear in the Ising model of ferromagnetism. We know that certain materials can be magnetized at low temperature, but above a certain critical temperature, knowns as the `Curie temperature`, the magnetic moment disappears. The tendency to retain a non-zero magnetic moment at low temperature is due to the interaction between neighboring atoms in the crystal. Considering the 3D Ising model, the spin is quantized in $z$ direction, the interaction is 
$$
H = -J \sum s(x) s(x+\hat{\mu})
$$
where $s(x)=\pm1$ represents an atom at point $x$ with spin up(down), $J$ is a positive constant. 

The system admits two possible states, the 
- `ordered state`: most spins tend to point in the same direction. The average magnetization is non-zero. 
- `disordered state`: the spin is distributed more or less randomly, the average spin is zero, no residual magnetic field.

**The energy-entropy argument for phase transition**

The principles of statistical physics says that, the system wants to minimize its free energy
$$
\boxed{
F = U-TS
}
$$
where $U$ is the internal energy, $T$ the temperature and $S$ the entropy. We can already see that there are two competing terms, internal energy and entropy, their relative strength is controlled by temperature $T$. In order to minimize the free energy, we need to either decrease the energy or increase the entropy, both of them are preferred by the system, that is very intuitive. It is the competition between them that makes things interesting. In general these two things contradicts each other, if the energy is low, the there aren't as much states that can be reached, thus the entropy must be low. So which one is more important in minimizing the free energy? The answer to that question is **temperature**! Roughly speaking, at low temperature, the energy dominates, the system prefers to stay at the low energy state. At high temperature, the contribution from entropy dominates, the system prefers to stay at the high entropy states. 

In our 3D Ising model, 
- at low temperature, the system wants to stay at the low energy state, all the spins point at the same direction, we have ordered state;
- at high temperature, the system wants to stay at the high entropy state, the spins wants to be as different as possible, we have disordered state.

Thus there must exist a critical temperature $T^\ast$ such that, below which the system is in the ordered state, above which the system is in the disordered state. 

**The global spin-flip (time reversal) symmetry**

The Hamiltonian is invariant under the flip of all the spins, 
$$
-1: s(x) \to -s(x)
$$
Thus the system adopts global $\mathbb{Z}_ {2}$ symmetry. 

But the phase transition also seems impossible from the observations:
- The system is symmetric under time reversal transition.
   $$
Z = \sum_ {\text{all states}} e^{ -\beta H }
$$
is invariant under $s\to-s$. The expectation of spin average should be zero! You could also say that *the ordered state is forbidden by $\mathbb{Z}_ {2}$ symmetry*! What goes wrong? 

The answer is that, the expectation value of the spin is indeed zero, but only in the long run. If the system is not too small, the time for us to observe the zero expectation value is incredibly long! So we can effectively regard it as impossible. 

Or, you can say that the phase transition is possible in the `thermodynamical limit`, where the size of the system is taken to be infinity but the energy density is finite.

**The spontaneous symmetry braking**

A symmetry is said to be spontaneously broken if it is 
- a symmetry of the Hamiltonian (partition function, Lagrangian), but
- **not** a symmetry of the ground state. Of course the ground state is described by some observables.


#### Gauge invariance

The spin system which was just described is an example of a lattice field theory. The points of the lattice are known as `sites`, the lines joining neighboring sites are `links`, and, on a hypercubic lattice, the little squares joined by four connecting links are known as `plaquettes`.

A gauge transformation is a position-dependent transformation of the degrees of freedom, in which the transformation can be chosen independently at each site.

The trick is to associate the dynamical degrees of freedom with the links of the lattice, while the gauge transformation is specified at each site.

The $\mathbb{Z}_ {2}$ gauge symmetry of the lattice Ising model is rather peculiar. The spin is associated to the links $s_ {\mu}(x)$, where $x$ is the site and $\mu$ specifies the direction to which the link goes. The gauge transformation is given by 
$$
s_ {\mu}(x) \to s'_ {\mu}(x) = z(x)s_ {\mu}(x) z^{-1} (x+\mu)
$$
where $z \in \mathbb{Z}_ {2}$.

**Elitzur’s Theorem.** A local gauge symmetry cannot break spontaneously. The expectation value of any gauge non-invariant local observable must vanish.

We must look, instead, to gauge-invariant observables, which are unaffected by gauge transformations. These can be constructed by taking the product of spins on links around a closed loop C, known as a ‘‘Wilson loop’’.

#### Possible phases of a gauge theory

Elitzur’s theorem tells us that gauge symmetries do not break spontaneously, in the sense that any *local*, gauge non-invariant observable that could serve as an order parameter must have a vanishing expectation value. There is, nonetheless, a qualitative distinction between different phases of a gauge theory, based on the behavior of large Wilson loops. Let us again consider a large rectangular $R\times T$ loop, with $T\gg R$, we know that 
$$
W(C) \sim  e^{ -V(R)T }.
$$

There are three possibilities:

- **massive phase**. The potential is of the Yukawa type
  $$
V(R) = -g^{2} \frac{e^{ -mR }}{R} +2V_{0},
$$
where $V_{0}$ is a self-energy term. The Wilson loop falls off at $R> \frac{1}{m}$ as $\exp(-2V_{0}T)$, and 
$$
W(C) = e^{ -V_{0} P(C) }
$$
where $P(C)$ is the perimeter of loop $C$.

- **massless phase, or Coulomb phase**. The potential looks like 
  $$
V(R) = - \frac{g^{2}(R)}{R} +2V_{0}
$$
and the Wilson loop still adopts perimeter law. 

- **Confining phase.** The potential is asymptotically linear
  $$
V(R) = \sigma R+2V_{0}
$$
Then the Wilson loop falls off asymptotically as
$$
W(c) \sim \exp[-\sigma A(C)-V_{0}P(C)]
$$
and there is an area-law type of falloff.

It is sometimes also called ‘‘magnetic disorder’’ is a terminology inspired by electromagnetism.

### From flat $\mathbb{R}^{4}$ to a cylinder

We will talk about the physics on four dimensional SU(2) gauge theory with a number $n_ {f}$ of Weyl fermions in the adjoint representation of the gauge group. The spacetime manifold is not flat $\mathbb{R}^{4}$ but instead $\mathbb{R}^{3}\times \mathbb{S}^{1}$. When formulated on $\mathbb{R}^{4}$, the vacuum structure of the theory can not be studied analytically, due to the strong-coupling in infrared energy scale. The $\mathbb{S}^{1}$ dimension has size (circumference) $L$, as we will see for small enough $L$ the theory can be studied using semi-classical methods.

This approach is mostly first studied by Mithat Unsal. He found that when $L \Lambda \ll 1$ the theory stays weakly couple even at IR scale. 

The space of SU(2) gauge theories with adjoint fermions are defined by the parameters:
- $\Lambda$, the confining scale;
- $n_ {f}$, the number of the flavor of the quarks;
- $m$, the mass of the adjoint fermion;
- $L$, the circumference of the $\mathbb{S}^{1}$ space. 

Such theories can be split into three parts, each with distinct calculable dynamics at $L \Lambda \ll 1$. We will enumerate some of them. In the process we will also introduce the jargon. The models include 

- `dYM`, deformed Yang-Mills theory. It is roughly speaking Yang-Mills theory with **two or more massive adjoint fermions**, whose mass are set to be very large, of order $m \sim \frac{1}{L}$. Due to the large mass, the fermions decouple from the theory at energy scale $\sim 1 / L$. But the existence leaves some trace, namely the breaking down of the gauge symmetry to U(1), called abelianization, and the center symmetry preservation. Note that dYM is in the  universality class of pure Yang-Mills theory, it is also believed to be continuously, i.e. without phase transition connected to the 4 dimensional Yang-Mills theory. 
- `QCD(adj)`, or adjoint QCD. It has $2\leq n_ {f} \leq 5$ massless adjoint Weyl fermions. It has the advantage that when the circle is small, $L \Lambda \ll 1$, the long distance effective theory is calculable, helps us to understand confinement and chiral symmetry analytically. The study of this theory highlights the importance of novel topological excitations in the dynamics of confinement and chiral symmetry breaking, the so-called “magnetic bions.” 
- SYM, the supersymmetric Yang-Mills theory. It is the same as the adjoint QCD theory except for $n_ {f}=1$. At zero fermion mass, the theory enjoys $\mathcal{N}=1$ super symmetry. Thus, near the SUSY point we can use powerful theoretical tools such the holomorphy to study it, plus it becomes semi-classical at small $L$, just like QCD(adj). In the semi-classical limit one also finds a novel type of composite topological structure, called the neutral bions. 

In the following notes we shall look into the non-perturbative physics at small circle size in detail. 