---
layout:     post   				    # 使用的布局（不需要改）
title:     An extremely short summary			# 标题 
subtitle:   
date:       2022-11-24 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt2.jpg 	#这篇文章标题背景图片
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