---
layout:     post   				    # 使用的布局（不需要改）
title:     Notes on Aspects of Symmetry			# 标题 
subtitle:   
date:       2022-11-24 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/lib2.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Duality
    - QFT
    - Notes
---

## An introduction to unitary symmetry

The story begins with the observation that, there exists eight baryons, namely eight positive-parity particles with isospin one and nucleon number 1, they are the nucleons, the $\Lambda$, the $\Sigma$s, the $\Xi$s. The masses of these particles are close together, all lying within 20% of their common mean mass. There are essentially two method to explain it,
- only some of these eight particles are fundamental. In the original Sakata model, the nucleons and the $\Lambda$ are taken to be fundamental, other particles are composite baryon-meson states, mesons are light in comparison with baryons thus explains the closeness of the masses of the eight baryons. Not very successful. 
- Maybe there is some larger approximate symmetry, of which the eight baryons are eight states in the same representation. The mass degeneracy is not accurate because the symmetry is not accurate. Very much like isospin model. This is gonna be the main role of this chapter.

What we want for this larger approximate symmetry: 
1. It commutes with the Poincare symmetry,
2. we want the conservation of probability, thus we want this group to be represented by a unitary operator when acting on the Hilbert space of the universe.
3. The many particle states transforms as a tensor made of one-particle states.
4. The group commutes with the scatter matrix (S matrix). 

A group which satisfies these conditions are usually called an *internal symmetry group*. Internal since it commutes with the Poincare symmetry, so if you perform, say, a Lorentz transformation, the eigenvalue stays the same, like the spin. 

The following are several properties force on the group by the nature of the problem,
1. it has an eight-dimensional representation,
2. which is irreducible.
3. The condition of continuity of the S matrix requires that the eight-dimensional representation to be closed, in the sense that any limit of a sequence of representation matrices is itself a representation matrix. 
4. The representation should be faithful. If a group action changes the universe in any way, it should also change the eight baryons, so different group elements should be represented by distinct representations.
5. It should contain SU(2) as a subgroup.

Two candidates are at hand: $G_{0}$ and $SU(3)$, the former turns out to be wrong. $G_{0}$ is the direct product of three $SU(2)$s,
$$
G_{0} = SU(2)\otimes SU(2)\otimes SU(2)
$$

## Soft Pions

### LSZ reduction formula

The LSZ reduction formula connects the time-order correlation function, such as $\left\langle T \left\{ \phi_{1}\phi_{2}\phi_{3}\phi_{4} \right\} \right\rangle$, to the S (Scatter?) matrix. It is at the heart of the scattering theory. It is not so important when dealing with the non-scattering properties of the field theory, such as non-perturbative properties. 

In scattering process, the initial and final particles, together known as the external legs in Feynman diagrams, are eigenstates of the full, interacting Hamiltonian. The formula giving us the scattering amplitudes must reflect that fact. 

S-matrix elements, extrapolated off the mass shell, with every external line multiplied by a propagator, are simply the Fourier transform of the vacuum expectation value of the time-ordered correlation functions.

## Dilatation

Coleman started with the Ward identity. Ward identity tells us that the classically conserved Noether current is not really conserved in the quantum theory, that is, when put in the path integral. There will be contact terms. There are Dirac delta function in it, we can integrate with respect to the whatever coordinate appears in the current, if omit the surface term, then we obtain the zero-energy theorem.

Then let's talk about dilatation, or scale transformation. 




