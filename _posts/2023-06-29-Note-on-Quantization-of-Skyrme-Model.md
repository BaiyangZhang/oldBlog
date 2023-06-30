---
layout:     post   				    # 使用的布局（不需要改）
title:     Note on the Skyrme Model, Classical and Quantum 			# 标题 
subtitle:   based on Adkins1983, Manko2007, David Tong, etc.
date:       2023-06-29 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background1.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 
---

# Static Properties of Nucleons in the Skyrme Model

## Introduction

In his 1973 paper "A planar diagram theory for strong interactions", 't Hooft treated the parameter $N$ in the gauge group $SU(N)$ or $U(N)$ as a free parameter, and explained that in the $N\to \infty$ limit, the Feynman diagrams arrange into sets with different topological structure according to its contribution in powers of $1 / N$. For the sake of simplicity he didn't require the trace of the ${\frak g}$-valued gauge field $A$ to be traceless, thus instead of $SU(N)$ the gauge group is actually $U(N)$. As a result there will be an extra photon corresponding to the $U(1)$ component of $U(1)$, which will be discarded at the last step. 't Hooft introduced the double-line notation and each closed group index circle will generate a factor of $\delta^{i}_ {i}=N$, making it convenient to count the factor of $N$ of a given Feynman diagram. Based on this, 't Hooft made use of the Euler theorem saying that $\chi=2-2g$ where $\chi$ is the Euler characteristic and $g$ the genus of a manifold, and reached the conclusion that, if $g^{2}N$ is kept fixed at large $N$, then *the planar diagrams with genus zero and one  dominate*. That is, to treat the double-line Feynman diagrams as the boundary of a manifold, then we can talk about the genus of it. *Regarding non-planar diagrams, each "handle" pay a price $1 / N^{2}$*.

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
where $\sigma^{a}$ are the Pauli matrices, and $f_ {\pi}\sim 92 \text{ Mev}$ is the pion decay constant. In 4D the scalar field has dimension 
$$
[\pi] = \frac{d-2}{2} = 1
$$
therefore $f_ {\pi}$ should also has the dimension of mass, such that the argument of the exponential function is dimensionless.

This is an example of so-called `chiral Lagrangian`, which combines the three pions into a single matrix with the help of Pauli matrices. 

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
But why? Some people might tell you not to worry about it, it doesn't matter for the calculation, but did you decide to do physics because you want to understand or because you love calculation? So here I'll try to explain it briefly. Feel free to skip the next chapter entirely if you are not interested.

### Chiral transformation

The story begins with what happens when some *global, continuous symmetry* is *spontaneously broken*. Let $J_ {\mu}$ be the Noether current associated to the symmetry. Assume that the conservation law $\partial_ {\mu} J^{\mu}$ holds in both classical and quantum situation, that is to say this symmetry is not anomalous. In the quantum theory, the conserved charge
$$
Q := \int d^{3}x \,  J_ {0},\quad  J_ {0} = \sum \frac{\partial \mathcal{L}}{\partial \dot{\phi}}\Delta \phi
$$
where $\Delta \phi$ is the variation of $\phi$ under the symmetry at question, the summation is over all kinds of fields. The important thing is that now $Q$ is an **operator**, because $\phi$'s are operators. Recalling the procedure of canonical quantization, first we define the canonical momentum
$$
\pi := \frac{\partial \mathcal{L}}{\partial \dot{\phi}}
$$
with the canonical commutation relation
$$
[\phi(x),\pi(y)] = i\delta^{(3)}(x-y)
$$
where I have omitted some possible indices. We then find that 
$$
[Q,\phi_ {n}(y)] = -i \frac{\delta \phi(y)}{\delta \alpha}
$$
where the RHS is the variation of the field under the symmetry in question, therefore $Q$ *generates the symmetry transformation.* 
Now, by definition, spontaneous symmetry breaking happens if the symmetric vacuum (or staple point, whatever name you like) with 
$$
Q\left\lvert{\Omega}\right\rangle=0
$$
is unstable, but the true, stable vacuum has non-zero charge
$$
Q\left\lvert{0}\right\rangle\neq 0.
$$
Here it is best to think of $Q\left\lvert{0}\right\rangle$ not as calculating the charge of $\left\lvert{0}\right\rangle$, but the infinitesimal form of transforming of $\left\lvert{0}\right\rangle$. If you have doubt, just think of the Mexico hat potential and rotational symmetry, once chosen a vacuum $\left\lvert{0}\right\rangle$, one can rotate it by an infinitesimal angle 
$$
e^{ i\epsilon Q }\left\lvert{0}\right\rangle = \left\lvert{0}\right\rangle +1\epsilon Q \left\lvert{0}\right\rangle =\left\lvert{0'}\right\rangle
$$
which is a new vacuum. Then Obviously $Q\left\lvert{0}\right\rangle\neq 0$. 

It can be shown that each spontaneously broken symmetry (SSB) gives rise to a massless mode, namely a massless particle. One way to do it is to start with the defining relation 
$$
\left\langle{0}\right\rvert [Q,\phi] \left\lvert{0}\right\rangle  \neq 0,
$$
introduce the eigenstates of momentum $\left\lvert{\pi(\mathbf{p})}\right\rangle$ and the corresponding identity operator 
$$
\mathbb{1} = \int_{-\infty}^{\infty} \frac{d^{3}p}{(2\pi)^{3}} \,  \left\lvert{\pi(\mathbf{p})}\right\rangle \left\langle{\pi(\mathbf{p})}\right\rvert ,
$$
substitute them into the vev of $[Q,\phi]$, write everything in the form of integral, make use of the fact that both the vacuum and the momentum eigenstates have very good property under the translation operator, we arrive at an formula which looks like 
$$
\left\langle{0}\right\rvert [Q,\phi] \left\lvert{0}\right\rangle = 
\int \frac{d^{3}p}{(2\pi)^{3}} \,  e^{ iE(\mathbf{p}=0)t } \times (t\text{-independent})
$$
but we know that the LHS is time independent, since $Q$ is a conserved charge! Thus the energy of zero momentum state must be 
$$
E(\mathbf{p}=0) = 0
$$
which means that this state is gapless, physically it means it is the state of a massless particle. 

Another way to see it is to notice that we can construct the pion state of 3-momentum $\mathbf{p}$ from the vacuum via
$$
\left\lvert{\pi(\mathbf{p})}\right\rangle := -\frac{2i}{F} \int d^{3}x \,  e^{ i\mathbf{p} \cdot \mathbf{x}} J_ {0}(x)\left\lvert{0}\right\rangle ,
$$
where $\pi$ in $\pi(\mathbf{p})$ is *not* the canonical momentum, but the pion field, so $\pi(\mathbf{p})$ is the pion field with momentum $\mathbf{p}$. This will be more obvious if you write things explicitly in ladder operators. Anyway, the energy of this state is 
$$
E = E(\mathbf{p}) + 0,
$$
where $0$ is the vacuum energy. Since $\left\lvert{\pi(0)}\right\rangle$ has energy $0$, energy must goes to zero as the momentum goes to zero, leaving us a massless particle.

We present here the famous `Goldstone's Theorem`,

**Goldstone's Theorem.** Spontaneous breaking of *continuous global symmetries* implies the existence of massless particles, called Goldstone bosons.

But, what does it has to do with chiral transformation? As we will see, massive pions can be approximately seen as the Goldstone bosons, the spontaneously broken symmetry being the chiral symmetry, as we will see later.

Usually the first connection between pion and SSB is made via the linear sigma model, which is of a complex scalar field with global $U(1)$ symmetry, with a Mexican hat potential, for more details refer to M. D. Schwartz's *Quantum field theory and the standard model*, section `28.2.1`. There, the massless scalar field is identified as the pion. But there is no quarks in the model, you can't introduce chiral symmetry without fermions. So we turn to a more realistic model, concerning the two lightest quarks.

- - -

Consider the QCD Lagrangian with up and down quarks only, both set to be massless,
$$
\mathcal{L} = -\frac{1}{2} tr F^{2} + \overline{u}i\gamma^{\mu} D_ {\mu} u + \overline{d}i\gamma^{\mu} D_ {\mu} d
$$
where $u,d$ are the Dirac fermions for up and down quarks respectively. Two things are important for our concern,
1. *isospin rotation is a symmetry of the Lagrangian*. Recall that isospin treats $(u,d)$ as a doublet under global $SU(2)$ transformation.
2. The *separation of left-handed and right-handed components of fermions*. Recall that the left-handedness and right-handedness, or chirality, is defined by the different Lorentz transformation behavior. In the massless case, there is no explicit coupling between the left- and right-handed components of the Dirac fermion, therefore we can treat them as independent particles.

In summary, we can now perform the isospin rotation separately,
$$
\begin{pmatrix}
u^{L} \\
d^{L} 
\end{pmatrix}
\to
L 
\begin{pmatrix}
u^{L} \\
d^{L} 
\end{pmatrix},\quad 
\begin{pmatrix}
u^{R} \\
d^{R} 
\end{pmatrix}
\to
R 
\begin{pmatrix}
u^{R} \\
d^{R} 
\end{pmatrix}
$$
where $L,R$ are different $SU(2)$ matrices. This is the so-called $SU(2)_ {L}\times SU(2)_ {R}$  `chiral symmetry` of QCD. Actually the Lagrangian is invariant under not $SU(2)_ {L}\times SU(2)_ {R}$ but $U(2)_ {L}\times U(2)_ {R}$, however we usually extract the two $U(1)$ components of $U(2)$ to form two global transformation, namely the *vector* and *axial vector* transformation, the vector transformation rotates both the up and down quark by the same angle, while the axial vector transformation rotates them by opposite angle. All together we can write
$$
U(2)\times U(2) = SU(2)_ {L} \times  SU(2)_ {R}\times U(1)_ {V}\times U(1)_ {A}
$$
where $V$ stands for vector and $A$ axial vector.

There is a rich story about $U(1)_ {V,A}$ symmetries, involving the quantum corrections that breaks the conservation law, etc. But that's another topic for another day. Right now we focus on the chiral symmetry. 

You can't get this from QCD theory itself, but the ground states in nature clearly has a non-zero vev of $\overline{u}u$ or $\overline{d}d$ operator,
$$
\left\langle \overline{u}u \right\rangle = \left\langle \overline{d}d \right\rangle =: V^{3}\neq 0.
$$
This is justified by the fact that it implies a spectrum of hadrons. The equivalence between $\left\langle \overline{u}u \right\rangle$ and $\left\langle \overline{d}d \right\rangle$ is also an empirical result. This phenomenological fact is referred to as the `quark condensate. 

- - -

Quark condensate, also known as the `chiral condensate` is one of the two dominate phenomena, namely *confinement* and `quark condensate`, at low energy. Actually when we wrote $\left\langle \overline{u}u \right\rangle$ we missed some information about the chirality, it should be $\left\langle \overline{u}_ {L} u_ {R} \right\rangle$. But how does this condensate form? I don't have any precise answer to that question though. Instead, I'll just list some heuristic reasons.

The existence of quark condensate, or equivalent the non-zero $\overline{q}_ {l}q_ {R}$ ($q$ stands for generic quarks) tells us that the vacuum is full of antiquark-quark pairs, for that is what the operators $\overline{q}q$ measure. This is analogous to what happens in a super conductor, where pairs of electrons condensate. In vacuum ,the quark-antiquark pairs must be produced in fluctuation, and is responsible for the confinement since it can break the flux tube. Of course another effect of quark condensate is that they break the chiral symmetry. To see this, recall that under chiral transformation the left-handed and right-handed quarks transform differently, in components we have
$$
\psi_ {Li}\to \psi'_ {Li} = L_ {ij} \psi_ {Lj},\quad  \psi_ {Ri} \to\psi'_ {Ri}=R_ {ij} \psi_ {Rj}
$$
where $i,j$ labels the flavor. Then the condensate operator $\overline{\psi}_ {Li}\psi_ {Rj}$ transforms as 
$$
\overline{\psi}_ {Li}\psi_ {Rj} \to \overline{\psi'}_ {Li}\psi'_ {Rj} = L^{\dagger}_ {mi}\overline{\psi}_ {Lm} R_ {jn} \psi_ {Rn} ,
$$
where we better think of $\overline{\psi}$ as $\psi ^\ast$. The quark condensate tells us that 
$$
\left\langle \overline{\psi}_ {Li}\psi_ {Rj} \right\rangle = V^{3}\delta_ {ij}
$$
Hence
$$
V^{3}=\left\langle \overline{\psi}_ {Li}\psi_ {Rj} \right\rangle \to \left\langle \overline{\psi}_ {Lm}\psi_ {Rn} \right\rangle L^{\dagger}_ {mi}R_ {jn}= V^{3}(RL^{\dagger})_ {ji},
$$
we see that the vev is only the same if $L=R$, otherwise the chiral transformation gives it a "phase". But if $L=R$ then the left-handed and right-handed fermions are transformed the same way, $SU(2)_ {L}\times SU(2)_ {R}$ degenerates to $SU(2)_ {L+R}$, which is just $SU(2)$. 

### Back to the Lagrangian

The pattern that the vacuum breaks the chiral symmetry shows us what the vacuum manifold is like, since
$$
\left\langle \overline{\psi}_ {Li}\psi_ {R_ {j}} \right\rangle = V^{3}(RL^{\dagger})_ {ji}
$$
and $RL^{\dagger}\sim SU(2)$, we have
$$
\left\langle \overline{\psi}_ {Li}\psi_ {R_ {j}} \right\rangle = V^{3}U_ {ij}, \quad  U \in  SU(2).
$$

This also answers our previous question about why $U(x)$ transforms as 
$$
U(x) \to L^{\dagger}U(x)R
$$
under the chiral transform. Note that we have been a little careless when identifying $L$ and $R$, in fact we can *define* $L^{\dagger}$ and $R$ according to the above formula. 

Next, Goldstone's theorem tells us that there exists a massless boson for each broken symmetry. So how many symmetries are broken? The SSB is 
$$
SU(2)\times SU(2) \to SU(2)
$$
and the number of generator is broken down from $2\times 3=6$ to $3$, so three symmetries (generators of symmetries, to be specific) are broken. Therefore, Goldstone's theorem tells us that there exists three massless Goldstone bosons. 

What is the physical nature of these massless bosons? They can only be bound states of quarks. They arise from the fact that the vacuum is "charged" under the quark condensate operator, which simply says that the vacuum gives non-zero expectation value of quark condensate operators. Hence it is better to think of the massless boson as a result of the slow-varying of $U(x)$ in $\left\langle \overline{\psi}\psi \right\rangle=V^{3} U$, where we have neglected as many indices as possible.

Then, as mentioned before, we parametrized $U(x)$ by pion fields,
$$
U(x) = \exp \left( \frac{i}{F_ {\pi}}\pi^{a}\sigma^{a} \right).
$$
This will be our basic degree of freedom, or building block, of the low-energy effective theory for pions. This seems like a leap of faith to me. It also shows how powerful is the tool of SSB, it enables us to say a lot about pion with very little knowledge about the actual structure of them.

- - -

Now let's proceed to construct a effective theory of Goldstone modes $U(x)$.  This effective model should respect all the low-energy symmetries that survived the SSB, in our case the chiral symmetry.

The simplest dynamic, renormalizable Lagrangian in terms of $U$ satisfying the chiral symmetry reads
$$
\mathcal{L} = \frac{f_ {\pi}^{2}}{4} \mathrm{Tr}\,(\partial_ {\mu}U \partial^{\mu}U).
$$
This is the so-called `chiral Lagrangian`. 

The normalization coefficient chosen such that, if you expand $U$ in terms of sin and cos functions, the pion fields adopt the correct dynamic term,
$$
\mathcal{L} = \frac{1}{2}\partial_ {\mu}\phi \partial^{\mu}\phi + \dots.
$$
Keep in mind that we are interested in a low energy effective theory, and in low energy the higher derivative terms are always suppressed since the momenta can't be too high, otherwise we wouldn't be talking about low energy. However, *we can use this fact to expand our Lagrangian terms in terms of momenta*, or so-called derivative expansion. At leading order of derivative expansion, except for the kinetic term, we also have
$$
\mathrm{Tr}\,(U^{\dagger}\partial_ {\mu}U)^{2},\quad (\mathrm{Tr}\,U^{\dagger}\partial_ {\mu}U)^{2}.
$$
However $\mathrm{Tr}\, U^{\dagger}\partial_ {\mu}U$ vanishes because $U^{\dagger}\partial_ {\mu}U$ takes value in the Lie algebra ${\frak su}(N)$, which has zero trace. Or you can just write $U$ in terms of generators then it become apparent. Furthermore, we can use the property
$$
U^{\dagger}U=\mathbb{1}
$$
to write $\mathrm{Tr}\,(U^{\dagger}\partial_ {\mu}U)^{2}$ in terms of $\mathrm{Tr}\,(\partial_ {\mu}U^{\dagger} \partial^{\mu}U)$, so at the leading order of the derivative expansion, we just need the kinetic term.

The interesting about the chiral Lagrangian
$$
\mathcal{L} = \frac{f_ {\pi}^{2}}{4} \mathrm{Tr}\,(\partial_ {\mu}U \partial^{\mu}U).
$$
is that, albeit the resemblance, it is **not a free theory**. This is because the target space, namely the space where the fields take value in, is not free, it is under some constraint. For example, you can never set $U=0$ since then it wouldn't be in $SU(2)$. Algebraically speaking, the theory is not free because $U$ are fixed to be special, unitary matrices. Geometrically speaking, the theory is not free because the target space of $U$ is $\mathbb{S}^{3}$, since $SU(2)\cong\mathbb{S}^{3}$. 

- - -

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

**Remarks.**
1. There is no first principal reason for including the Skyrme term. It seems quite *ad hoc*.
2. It is a little counter-intuitive, but the Skyrme term in fact contains only *second order time derivative*. This can be seen by expanding the bracket, and making use of the properties of $SU(2)$. This is important for second order time derivative is what we want in deriving the equation of motion. And the Skyrme term is unique in this sense.
3. The coupling $e^{2}$ is dimensionless.

- - -

Recall that $U$ is a SU(2) matrix, under the chiral transformation 
$$
U \to LUR^{-1}, \quad  L, R \in SU(2).
$$
$F_ {\pi}=186 \text{ MeV}$ is the pion decay constant, $e^{2}$ is a dimensionless parameter. The last term, the trace of a commutator, was first introduced by Skyrme to stabilize the soliton solution.

To simplify the notation, we denote the Noether current associated to the $SU(N_ {f})_ {L}$ by
$$
L_ {\mu} = U^{\dagger}\partial_ {\mu}U.
$$
The Noether current associated to the right-handed $SU(2)$ is left as a homework, you'll see it is related to $L_ {\mu}$ by a hermitian conjugation. 

With some manipulation, you can see that the *static* energy can be written entirely in terms of $L_ {\mu}$,
$$
E = \frac{F^{2}_ {\pi}}{4} \int d^{3}x \,  \left( L_ {i}L^{\dagger}_ {i}  - \frac{1}{4e^{2}F^{2}_ {\pi}}(\epsilon_ {ijk}L_ {j}L_ {k}) (\epsilon_ {imn}L^{\dagger}_ {m}L^{\dagger}_ {n}) \right).
$$

We now use Bogomolnyi trick, namely to complete the square,
$$
E = \frac{F^{2}_ {\pi}}{4} \int d^{3}x \,  \mathrm{Tr}\,\left\lvert L_ {i}\mp \frac{1}{2eF_ {\pi}}\epsilon_ {ijk}L_ {j}L_ {k} \right\rvert ^{2}
\pm \frac{F_ {\pi}}{4e}\int d^{3}x \,  \epsilon_ {ijk}L_ {i}L_ {j}L_ {k}.
$$
Then, follow the standard procedure, we need to show that the second term is actually a *topological constant* (or topological charge), which will justify the statement that the solution to the EOM is given by the field configuration that sets the square term in $E$ zero. 

- - -

A field configuration is a map
$$
U(x): \mathbb{R}^{3}\to SU(2)
$$
where $\mathbb{R}^{3}$ is the physical space. If we insist that the field goes to the same vacuum at the spatial boundary, then we can compactify $\mathbb{R}^{3}$ to $\mathbb{S}^{3}$. This is a reflection of the idea that the kinds of function you define on a space will in tern decide the topological structure of the supporting space itself. So now the field configuration is a map
$$
U(x): \mathbb{S}^{3}\to SU(2)\cong \mathbb{S}^{3},
$$
which is classified by the homotopy group $\pi_ {3}(\mathbb{S}^{3})\cong\mathbb{Z}$. With some mathematics we can show that, the winding number $B$ is given by
$$
B = \frac{1}{24\pi^{2}} = \int d^{3}x \,  \epsilon_ {ijk}\mathrm{Tr}\, 
(U^{\dagger}\partial_ {i} U U^{\dagger}\partial_ {j} UU^{\dagger}\partial_ {k} U)
$$
where the derivative acts on the next matrix only. 

We can go further and write down a local current associated to $B=\int  \,J^0$,
$$
J^{\mu} = \frac{1}{24\pi^{2}}\epsilon^{\mu \nu \rho \sigma} \mathrm{Tr}\,(U^{\dagger}_ {\nu}UU^{\dagger}_ {\rho}UU^{\dagger}_ {\sigma}U)
$$
which obeys $\partial_ {\mu}J^{\mu}=0$ due to the antisymmetric properties.

What is the physical interpretation of $J^{\mu}$? The only candidate seems to be the vector transformation $U(1)$. *If we identify $J^{\mu}$ with $J_ {V}$, then we are identifying the solitons with baryons, for $J_ {V}$ is the baryon number current*. This is probably why we regard soliton in Skyrme model as candidates for baryons.

- - -

Now having the expression for $B$, we can write the static energy in terms of it,
$$
E \geq  \frac{6\pi^{2}F_ {\pi}}{e}B.
$$
When the equality is taken, we say the solution saturates the Bogomolnyi condition, and corresponding solitons (with nontrivial topology, namely $B\neq 0$) are called `Skyrmions`.

- - -

To find the Skyrmion solution, one would naively try to solve the first-order differential equation. 
$$
0=L_ {i}\mp \frac{1}{2eF_ {\pi}}\epsilon_ {ijk}L_ {j}L_ {k}.
$$
There is nothing wrong with this approach, actually it is the standard approach in solving solitons in general, however in our particular case this doesn't seem to help. *One can show that there is no solution to the firsts order differential equation.* Instead we must turn to the full equation of motion, which is of second order,
$$
\boxed {
\partial_ {\mu}L^{\mu} = \frac{1}{4F^{2}_ {\pi}e^{2}}\partial_ {\mu}[L_ {\nu},[L^{\mu},L^{\nu}]]. \tag{EoM for Skyrmion}
} 
$$

We adopt the spherical symmetric ansatz (`hedgehog ansatz`)
$$
\boxed {
U_ {0}(x) = \exp[iF(r) \tau \cdot \hat{x}], \quad  F(r){\Large\mid}_ {r=0} =\pi,\,F(r){\Large\mid}_ {r=\infty} =0. \tag{hedgehog}
} 
$$

Take it to the Lagrangian, Legendre transform the Lagrangian to energy functional, we have the expression of the energy of the soliton in terms of the profile function $F(r)$:
$$
M = 4\pi \int_{0}^{\infty} dr \, r^{2}\left\{ \frac{1}{8}F_ {\pi}^{2}\left[ (\partial _ {r}F)^{2}+2\frac{\sin ^{2}F}{r^{2}} \right] + \frac{1}{2e^{2}} \frac{\sin ^{2}F}{r^{2}}
\left[ \frac{\sin ^{2}F}{r^{2}}+2(\partial _ {r}F)^{2} \right]\right\} , 
\tag{2}
$$

Then we can obtain the variational equation from it, then we can further solve it numerically. Introduce the dimensionless parameter $\widetilde{r}:= eF_ {\pi}r$, the equation of motion reads
$$
\left( \frac{1}{4}\widetilde{r}^{2}+2\sin ^{2}F \right)F'' + \frac{1}{2} \widetilde{r} F' + \sin (2F) F'^{2}- \frac{1}{4}\sin(2F) - \frac{\sin ^{2}F \sin 2F}{\widetilde{r}^{2}}=0.
$$
Then we can use numerical methods to solve it. It is a monotonically increasing function, and *the energy of this solution turns out to be about 25% higher than the bound*. So the Bogomolnyi bound can not be saturated for Skyrmions.

- - -

However, there is another level of symmetry breaking here, where the original $SU(2)_ {L}\times SU(2)_ {R}$ symmetry is broken by the Skyrmion solution. If we insist that 
$$
U(x) {\Large\mid}_ {x\to \infty }= \mathbb{1} 
$$
then the symmetry is broken down to 
$$
SU(2)_ {L}\times SU(2)_ {R} \to SU(2)_ {V},
$$
for if left-handed and right-handed rotations are different, then $\mathbb{1}$ will be changed. 

### How to parametrized the rotation

Recall that in the presence of a Skyrmion, the symmetry is broken to $SU(2)_ {V}$, to preserve $U(X)=\mathbb{1}$ at spatial infinity. We can include the spatial rotational symmetry, we have the symmetry group
$$
SU(2)_ {\text{rot}} \times  SU(2)_ {V}. \tag{Skyrmion symmetry group}
$$
The single Skyrmion is not invariant under either of these $SU(2)$ groups separately. However, *it is invariant under the diagonal $SU(2)$ which acts simultaneously as a spatial and flavor rotation*. To be specific, a spatial rotation will change the Skyrmion configuration (think of it as a hedgehog), but we can use isospin rotation to rotate it back, for both the spatial and isospin rotations will rotate the hedgehog.

The subgroup of the Skyrmion symmetry group which acts non-trivially on the Skyrmion solution can be used to generate new solutions. These are trivially related to the original, and just change its embedding in the target space. Nonetheless, they have important consequences, as we will see below.

Now we can make use of the *global* $SU(2)_ {\text{rot}}$ symmetry of the Lagrangian, namely if $U_ {0}$ is a soliton solution, then
$$
U = A U_ {0} A^{-1}
$$
is also a soliton solution. Thus we have a space of solutions parametrized by $A$, by parametrization we mean that there is a map
$$
A \to \text{rotation space of soliton solutions}.
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