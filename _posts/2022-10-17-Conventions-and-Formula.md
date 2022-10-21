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
- - -

We require the generators in the fundamental representations to satisfy normalization condition
$$
  \text{Tr }{T^a T^b} = \frac{1}{2} \delta^{ab}.
$$

Gauge field is a $\mathfrak{g}$-valued field,
$$
 A_\mu = A_\mu^a T^a, \, T^a \in \mathfrak{g}.
$$
The $\mathfrak{g}$-valued field strength is
$$
  F_{\mu\nu} = \partial_\mu A_\nu - \partial_\nu A_\mu -i[A_\mu, A_\nu],
$$
which in the language of differential forms is 
$$
\boxed{
F = dA-iA \wedge A
}.
$$
Our convention for covariant derivative acting on a field in the fundamental representation is
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

- - -

The gauge transformation for various fields are

- gauge field: $A_\mu \to \Omega (A_\mu + i \partial_\mu) \Omega^\dot{a}gger,\, \Omega=e^{i \omega^i T^i} \in SU(N)$
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

- - -

Some notations concerning SUSY.
$$\begin{align}
    \eta_{\mu\nu} &= \text{diag}{1,-1,-1,-1}, \\
    \sigma^\mu_{a \dot{a}} &= (\mathbb{1},\sigma^i)  \quad \text{numerically}, \\
    \overline{\sigma}^{\mu \dot{a} a} &= (\mathbb{1},-\sigma^i)\quad \text{numerically}, \\
    {\left(\sigma^{\mu\nu}\right)_{a}}^{b} &\equiv \frac{i}{4} {\left( \sigma^{[\mu}\overline{\sigma}^{\nu]}\right)_{a}}^{b}, \\
    {\left(\overline{\sigma}^{\mu\nu}\right)^{\dot{a}}}_{\dot{b}} &\equiv \frac{i}{4} {\left(\bar\sigma^{[\mu}\sigma^{\nu]}\right)^{\dot{a}}}_{\dot{b}}.
\end{align}
$$
Under Lorentz transformation,
$$
    \psi_a \mapsto {\exp\left( -\frac{i}{2}\omega_{\mu\nu}\sigma^{\mu\nu}\right)_{a}}^{b}\; \psi_b, \quad 
    \bar\psi^{\dot{a}} \mapsto {\exp\left( -\frac{i}{2}\omega_{\mu\nu}\bar\sigma^{\mu\nu}\right)^{\dot{a}}}_{\dot{b}} \bar{\psi}^{\dot{b}}.
$$

The contraction works in a peculiar way. The metric is
$$
  \epsilon_{ab} = \sigma^2(i\to 1) = 
  \begin{pmatrix}
  0 & -1 \\ 1 & 0
  \end{pmatrix}, \quad 
  \epsilon^{ab} = -\epsilon_{ab}, \quad \epsilon^{\dot{a}\dot{b}} = -\epsilon_{\dot{a}\dot{b}}. 
$$
The metric acts from left on a field, and acts from right to a derivative,
$$
  \epsilon_{ab} \psi^b = \psi_a, \quad \partial_a \epsilon^{ab} = \partial^b.
$$

The gamma matrices:
$$
\begin{align}
    \gamma^\mu &= \begin{pmatrix}
    0 & \sigma^\mu \\
    \bar\sigma^\mu & 0
    \end{pmatrix}, \\
    \gamma^5 &= i\gamma^0\gamma^1\gamma^2\gamma^3.
\end{align}
$$
$$
\begin{align}
    \chi^a \chi^b &= - \frac{1}{2} \epsilon^{ab} \chi^2, \quad 
    \chi_a \chi_b =   \frac{1}{2} \epsilon_{ab} \chi^2, \\
    \bar\chi^{\dot{a}} \bar\chi^{\dot{b}} &=  \frac{1}{2} \epsilon^{\dot{a} \dot{b}} \bar\chi^2, \quad 
    \bar\chi_{\dot{a}} \bar\chi_{\dot{b}} = -\frac{1}{2} \epsilon_{\dot{a} \dot{b}} \bar\chi^2.
\end{align}
$$
$$
(\theta \sigma^\mu \bar\theta)(\theta \sigma^\nu \bar\theta) = \frac{1}{2} \eta^{\mu\nu} \theta^2 \bar\theta^2.
$$ 
$$
\begin{align}
  A^\mu &= \frac{1}{2} A_{a\dot{b}} \sigma^{\mu\dot{b} a}, \\
  A_{a\dot{b}} &= A^\mu \sigma_{\mu a\dot{b}}, \\
  F_{a}^{b} &= F_{\mu\nu} {(\sigma^{\mu\nu})_{a}}^{b}
\end{align}
$$

Note that the complex conjugate reverses the order of Grassman operators, and 
$$\boxed{(\partial_a)^\ast = -\bar\partial_{\dot{a}}}.$$

**The chiral field:**
$$
\begin{align}
    x_L &\equiv x^\mu - i\theta \sigma^\mu \bar\theta, \quad 
    x_R \equiv x^\mu + i\theta \sigma^\mu \bar\theta, \\
    D_a &= \partial_a -i (\sigma^\mu \bar\theta)_a \partial_\mu, \quad 
    \bar{D}_{\dot{a}} = (D_a)^\ast = -\bar\partial_{\dot{a}} + i (\theta \sigma^\mu )_{\dot{a}} \partial_\mu.
\end{align}
$$
The supergauge transformation:
$$
\begin{align}
    \Phi &\rightarrow e^{i q\Lambda(y,\theta)} \Phi, \\
    V(x,\theta,\bar\theta) &\rightarrow  V(x,\theta,\bar\theta) - i (\Lambda - \bar\Lambda),
\end{align}
$$
where the charge $q$ is usually absorbed in the definition of the gauge field $A$. The gauge invariant combination is 
$$ 
  \bar\Phi e^{V} \Phi.
$$ 
The Wess-Zumino supergauge greatly reduces the number of component fields of a real superfield:
$$
  V(x,\theta,\bar\theta) = -2 \theta \sigma^\mu \bar\theta A_\mu -2i\bar\theta^2 (\theta\lambda) + 2i \theta^2 \bar\theta\bar\lambda + \theta^2 \bar\theta^2 D.
$$ 
The super-generalization of field strength is a left-chiral superfield, 
$$
  W_a \equiv \frac{1}{8} \bar{D}^2 D_a V,
$$ to derive it, go to $\{y^\mu, \theta, \theta\}$ coordinates and note that $\bar{D}_{\dot{a}} \to - \bar\partial_{\dot{a}}$ and $\bar\partial^2 \bar\theta^2 = -4$.
