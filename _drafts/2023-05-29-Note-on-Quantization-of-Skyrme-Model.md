---
layout:     post   				    # 使用的布局（不需要改）
title:     Note-on-Quantization-of-Skyrme-Model 			# 标题 
subtitle:   based on Adkins1983, Manko2007, etc.
date:       2023-06-19 				# 时间
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
Then we can obtain the variational equation from it, then we can further solve it numerically. The equation of motion reads
$$

$$


