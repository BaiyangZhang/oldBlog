---
layout:     post   				    # 使用的布局（不需要改）
title:      Note on Meson-Kink Scattering		# 标题 
subtitle:   
date:       2022-10-26 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background8.jpg 	#这篇文章标题背景图片
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
Note that above expressions are different from the ones we are using by somewhere a different factor. 
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
It is not in the form of a shape-preserving wave packet, which should be $f(x-vt)$ for some function $f$, does it mean that during the propagation the shape changes?  The complex conjugate of $\psi^+$ will be $\psi^-$, the wave packet that moves to the $-x$ direction.

- - -

Kiriushcheva and Kuzmin studied the propagation of the wave packet numerically for $\nu=1$ sech square potential. [^2] They found that the wave packet narrows and accelerates. Their wave packet was taken to be the Gaussian shape at the initial time,  
$$
\Phi_{0}(x,t=0) = \exp \left\{ ik_{0}(x-x_{0})-\frac{(x-x_{0})^2}{2b^2} \right\} 
\tag{1}
$$
where $x_{0}$ is the center position of the wave packet and $b$ the width. The reason for the imaginary part in the exponential is such that the wave packet has momentum centered at $k_{0}$, as we shall see below. To be specific, the momentum is $k_{0} \pm b$ where $\pm b$ denotes the error. The same wavefunction in the momentum space looks like
$$
\tilde{\Phi}_{0}(p) = \int dx \, \Phi_{0}(x) e^{ -ipx },
$$
for the convention refer to note [[2022-7-17-Conventions-and-Formula]]. We have 
$$
\tilde{\Phi}_{0}(p) = \sqrt{ 2\pi }b \exp \left\{ -\frac{b^2}{2}(p-k_{0})^{2}-ipx_{0} \right\} .
\tag{2}
$$
We can now evolve the state with the Hamiltonian, for a given wavefunction $\psi(x,t)$, in terms of momentum eigenstates we have 
$$
\psi(x,t) = \int \frac{dp}{2\pi} \, \phi(p) e^{ -iH(p)t+ipx }  
$$
where $H(p)$ is the Hamiltonian. Apply it to $\Phi(x,t=0)$ we have
$$
\Phi(x,t) = \frac{b}{\sqrt{ b^{2}+\frac{it}{m} }}\exp \left\{ -\frac{1}{2} \frac{(x-x_{0}-vt)^{2}}{b^{2}+\frac{it}{m}} + ip\left( x-x_{0}-\frac{1}{2}vt \right) \right\} .
$$

Now, to see how the wave packet moves through time, we need to know how the density evolves, which is 
$$
\left\lvert \Phi(x,t) \right\rvert ^2 = \frac{b}{\sqrt{ b^{2}+\frac{t^{2}}{b^{2}m^{2}} }}\exp \left\{ - \frac{(x-x_{0}-vt)^{2}}{b^{2}+\frac{t^{2}}{b^{2}m^{2}}} \right\} ,
$$
we can see clearly that the peak of the Gaussian wave packet moves with velocity $v= p / m$, since the time-dependent position of the peak is $x_{0}+vt$. Taking into consideration the error, the center of position will be $x_{0}+vt \pm \sqrt{ b^{2}+t^{2} / b^{2}m^{2} }$. 

The initial position is $x_{0} \pm b$, the momentum is $k_{0}\pm \frac{1}{b}$, which can be read off from Eq. (2).

We notice two things,
1. Heisenberg uncertainty principle is saturated in this case, $\Delta x \Delta p = b \times\frac{1}{b} =1$ (note we have set $\hbar=1$),
2. the variance in the initial position and velocity are independent, thus can be compounded by squares, the variance in position at time $t$ will be 
$$
\Delta x(t)^{2}=(\Delta x_{0})^{2}+(t\Delta v)^{2}=b^{2}+\left( \frac{t}{mb} \right)^{2}.
$$



[^2]: N. Kiriushcheva and S. Kuzmin, “Scattering of a Gaussian wave packet by a reflectionless potential,” Am. J. Phys. 66, 867–872 (1998)

- - -

### 1+1 dimensional QFT with kinks

Consider a $1+1$ dimensional model with scalar fields $\phi$ only, in the Schrodinger picture. Schrodinger picture means that operator are constants in time while the wave function evolves. Since the scalar field is a operator in quantum field theory, $\phi(x)$ is constant in time so $\partial_{t}\phi$ makes no sense, hence we need the canonical momentum $\pi(x)$. The Hamiltonian is 
$$
H=\int d x: \mathcal{H}(x):_a, \quad \mathcal{H}(x)=\frac{\pi^2(x)}{2}+\frac{\left(\partial_x \phi(x)\right)^2}{2}+\frac{V(\sqrt{\lambda} \phi(x))}{\lambda}.
$$
The notation $:\bullet:_{a}$ denotes the normal ordering with respect to ladder operators $A,A^{\dagger}$, we will have more to say about it later. The parameter of potential is written as $\sqrt{ \lambda }\phi(x)$ not because we like to make our lives complicated, but for semi-classical expansion reasons. By semi-classical expansion we mean the to take the limit $\hbar\to 0$. Putting $\hbar$ back to the action we have roughly 
$$
Z = \int \mathcal{D}\phi \mathcal{D}\pi \, e^{ iS/\hbar }, \quad S = \int dx^2 \,\mathcal{L} .
$$
We can stick to the natural units and consider $\hbar$ not the Plank constant with non-trivial dimension, but just a parameter which is dimensionless. Now we ask, if we want the action kept unchanged as we vary the value $\hbar$, how would various parameters in the Lagrangian vary? The field operator $\phi$ multiplies $\hbar$ as $\frac{\phi^2}{\hbar}$, thus when we change $\hbar$,
$$
\text{const action} \implies \frac{\phi^2}{\hbar} \text{ is const} \implies \phi \sim \sqrt{ \hbar },
$$
where tilde means the $\phi$ scales as $\sqrt{ \hbar }$. Similarly we have $\lambda \sim \hbar^{-1 / 2}$. We find that the combination
$$
\sqrt{ \lambda }\phi = \text{const} \text{ under the variatio of } \hbar,
$$
which means $\sqrt{ \lambda }\phi$ is const in the semi-classical limit, and that's why we define the potential in that specific combination. 

