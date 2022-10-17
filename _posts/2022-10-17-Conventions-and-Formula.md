---
layout:     post   				        # 使用的布局（不需要改）
title:      Conventions and Formula 	    # 标题 
subtitle:                               #副标题
date:       2022-10-17 				    # 时间
author:     Baiyang Zhang 				# 作者
header-img: img/mathArt2.jpg 	        #这篇文章标题背景图片
catalog: true 						    # 是否归档
tags:								    #标签
    - math
    - quantum field theory
---

The master formulae in QFT:
$$
  \int \mathcal{D}\phi^*\mathcal{D}\phi\exp\left\{ i \int d^4x (\phi^* M \phi + JM) \right\} = \frac{\mathcal{N}}{\det{M}} \exp(iJM^{-1}J)
$$
where $\mathcal{N}$ is some normalization factor.

For fermions,
$$
  \int \mathcal{D}\psi\mathcal{D}\overline{\psi}\exp\left\{ i \int d^4x (\overline{\psi} M \psi) \right\} = \mathcal{N}\det{M}.
$$
Some conventions
$$
\begin{align}
  g_{\mu\nu}&=\text{diag}\{1,-1,-1,-1\},\\
  \epsilon_{0123} &= 1,\\
  f(x) &= \int \frac{d^nk}{(2\pi)^n}e^{-ip\cdot x}\widetilde{f}(p),\\
  \widetilde{f}(p)&=\int dx e^{ip\cdot x}f(x),\\
  \delta^{(n)}(k) &= \frac{1}{(2\pi)^n}\int d^nxe^{i k x}.
\end{align}
$$
The gauge Lie group $G$ has an underlying Lie algebra $\mathfrak{g}$, whose generator satisfies
$$
  [T^a,T^b] = i f^{abc} T^c
$$

We require the generators in the fundamental representations to satisfy normalization condition
$$
  \text{Tr }{T^a T^b} = \frac{1}{2} \delta^{ab}.
$$

Gauge field is a $\mathfrak{g}$-valued field,
$$
 A_\mu = A_\mu^a T^a, \, T^a \in \mathfrak{g}.
$$
4
The $\mathfrak{g}$-valued field strength is
$$
  4F_{\mu\nu} = \partial_\mu A_\nu - \partial_\nu A_\mu -i[A_\mu, A_\nu],
$$
our convention for covariant derivative acting on a field in the fundamental representation is
$$
  D_{\mu}{\psi} \equiv \partial_\mu \psi -i A_\mu \psi,
$$
while acting on a field in the adjoint representation is
$$
  D_{\mu}{\phi} \equiv \partial_\mu \phi -i [A_\mu,\phi],
$$
and
$$
\begin{align}
  [\mathcal{D}_\mu,\mathcal{D}_\nu]\psi &= -i F_{\mu\nu}\psi,\\
  [\mathcal{D}_\mu, \mathcal{D}_\nu]\phi &= -i [F_{\mu\nu},\phi],
\end{align}
$$
where again $\psi,\phi$ are fields in the fundamental and adjoint representation respectively.

The gauge transformation for various fields are

- gauge field: $A_\mu \to \Omega (A_\mu + i \partial_\mu) \Omega^\dagger,\, \Omega=e^{i \omega^i T^i} \in SU(N)$
- fundamental scalar field:  $\phi \to \Omega \phi$
- fundamental spinor field:  $\psi \to \Omega \psi$
- adjoint scalar field:      $\phi \to \Omega \phi \Omega^\dagger$


The non-abelian, gauge dependent magnetic field (chromo-magnetic field) is
$$
  B_i \equiv -\frac{1}{2} \epsilon_{ijk}F_{jk}
$$
and the non-abelian electric field
$$
  E_i \equiv F_{0i}
$$

The Weyl (chiral) basis of gamma matrices is
$$
\gamma^\mu =
 \begin{pmatrix}
   0 & \sigma^\mu \\
   \bar\sigma^\mu & 0
 \end{pmatrix},\quad \bar\sigma^\mu \equiv (\mathbb{1},\sigma^i).
$$

Going to the Euclidean spacetime: 
$$
    t\to -i\tau
$$