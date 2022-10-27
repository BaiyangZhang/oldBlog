---
layout:     post   				    # 使用的布局（不需要改）
title:      Note on Meson-Kink Scattering		# 标题 
subtitle:   
date:       2022-10-26 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt13.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - QuantumFieldTheory
    - Kink
    - Meson
---

### Sech$^2$ as an example of reflectionless potential 

The one-dimensional potential 
$$
V(x) = - \frac{\hbar^2}{2m a^{2}} \frac{\nu(\nu+1)}{\cosh ^{2}\left( \frac{x}{a} \right)}
$$
if reflectionless, at any energy, if $\nu$ is a positive integer number. Since there is no reflection of any eigen function, the wave packet formed by superposition of the energy eigen functions are also reflectionless. A numerical study shows that a Gaussian wave packet will be narrower by passage of the reflectionless $\text{sech}^{2}$ potential, and they can travel faster than a free space packet.[^1]

[^1]: N. Kiriushcheva and S. Kuzmin, “Scattering of a Gaussian wave packet by a reflectionless potential,” Am. J. Phys. 66, 867–872 (1998).

- - -

For positive energy energies we write $E = \frac{\hbar^{2}k^{2}}{2m}$, where $k$ is the momentum. The Schrodinger equation becomes
$$
\frac{d^{2}}{dx^{2}}\Psi +\left[ k^{2}+\frac{\nu(\nu+1)}{a^{2}\cosh ^{2}\left( \frac{x}{a} \right)} \right]\Psi = 0.
$$
Since the equation is parity invariant, name the equation is invariant under the interchange $x\to-x$, the solutions will also be eigen functions of the parity operator, they either stay unchanged, or obtain a minus sign, under $x\to-x$. In other words, there exists even or odd parity solution. The solution is found to be
$$
\begin{align}
\psi^e_{\nu} &= \left( \cosh \frac{x}{a} \right)^{\nu+1}F\left( \alpha,\beta, \frac{1}{2},-\sinh ^{2}\left( \frac{x}{a} \right)  \right), \\
\psi^o_{\nu} &= \left( \cosh \frac{x}{a} \right)^{\nu+1} \sinh\left( \frac{x}{a} \right) F\left( \alpha+ \frac{1}{2},\beta+\frac{1}{2}, \frac{3}{2},-\sinh ^{2}\left( \frac{x}{a} \right)  \right)
\end{align}
$$
where 
$$
\alpha = \frac{1}{2}(\nu+1+ika),\quad \beta=\frac{1}{2}(\nu+1-ika)
$$
are complex conjugate to each other the $F$ is the hypergeometric function which can be represented by the Gauss hypergeometric series
$$
F(\alpha,\beta,\gamma,\zeta) = \frac{\Gamma(\gamma)}{\Gamma(\alpha)\Gamma(\beta)}\sum_{0}^\infty 
\frac{\Gamma(\alpha+n)\Gamma(\beta+n)}{\Gamma(\gamma+n)}
\frac{\zeta^n}{n!}
$$
within the unit circle $\zeta=1$. Recall that $F(\alpha,\beta,\gamma,\zeta)$ is symmetric under the interchange of $\alpha$ and $\beta$.

When $\nu=0$ there is no potential, so the solution $\psi_{0}^{\text{even,odd}}$ are plane waves, the trivial solution. To be exact, 
$$
\begin{align}
\psi^e_{0} &= \cos kx,  \\
\psi^e_{0} &=\frac{\sin kx}{ka}.
\end{align}
$$
The integer $\nu$ solutions rapidly become more and more complicated, but remain elementary functions, expressible in terms of $\cos, \sin$ and tanh functions. For example,
$$
\begin{align}
\psi^e_{1}  & = \cos kx - \tanh \left( \frac{x}{a} \right) \frac{\sin kx}{ka},\\ 
\psi^o_{1}  & = \frac{1}{1+(ka)^{2}}\left[ ka\sin kx + \tanh\left( \frac{x}{a} \right) \cos kx \right] \\ 
\psi^e_{2}  & = \frac{1}{1+(ka)^{2}} \left\{ \left[ 1+(ka)^{2}-3\tanh ^{2}\left( \frac{x}{a} \right) \right] \cos kx 
-3ka \tanh\left( \frac{x}{a} \right)\sin kx\right\},  \\ 
\psi^o_{2}  & = \frac{1}{ka(4+(ka)^{2})^{2}}\left\{ \left[ 1+(ka)^{2}-3\tanh ^{2}\left( \frac{x}{a} \right) \right] \sin kx + 3ka\tanh\left( \frac{x}{a} \right)\cos kx\right\} .
\end{align}
$$

- - -

The eigenstates we listed above can be used to construct propagating waves. For example, the waves moving to the $+x$ direction can be defined by 
$$
\psi_{0}^+ = \psi_{0}^e + ika\psi_{0}^o = e^{ ikx },
$$
which is the plane wave moving to the plus $x$ direction if you put back the $e^{ -i\omega t }$ factor, and 
$$
\psi_{1}^+ = \psi_{1}^e + i \frac{1+(ka)^{2}}{ka}\psi_{i}^o = 
\left[ 1+\frac{i}{ka}\tanh\left( \frac{x}{a} \right) \right]e^{ ikx },
$$
Here I am a little confused, in what sense is the state $\psi^+_{\nu}$ a right-moving eigen state? It is not in the form of a shape-preserving wave packet, which should be $f(x-vt)$ for some function $f$, does it mean that during the propagation the shape changes?  Also I guess the complex conjugate of $\psi^+$ will be $\psi^-$, that wave packet that moves to the $-x$ direction?

- - -

Kiriushcheva and Kuzmin studied the propagation of the wave packet numerically, 