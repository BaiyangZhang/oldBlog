---
layout:     post   				    # 使用的布局（不需要改）
title:    Note on Clasical Lumps and Their Quantum Descendants		# 标题 
subtitle:   Lecture 1
date:       2023-3-17 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background10.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Duality
    - QFT
    - Notes
---

## An introduction to unitary symmetry

The waves in real world usually dissipates in the course of time. As the energy propagates to infinite far in the form of waves, the energy density goes to zero uniformly in spacetime. The same is true for the solutions of wave equations, except for some singular solutions at least. We give a more rigorous definition for dissipation here, a solution of the classical equations of motion is dissipative if 
$$
\lim_{ t \to \infty } \text{max } \mathcal{E}(\mathbf{x},t)=0,
$$
where $\mathcal{E}(\mathbf{x},t)$ is the energy density. 

The interesting thing is that there exists wave functions that allows for non-singular, non-dissipative solutions. In the most striking and simplest case, the solution is time-independent. Somehow, lumps of energy hold themselves together by their own self-interaction. 

- - - 

### Some time-independent example in one space dimension

First some conventions. The metric is taken to be $g = \text{diag}(1,-1)$, $i,j, \dots$ denote space dimensions, $a,b, \dots$ denotes internal symmetry. 

Let us consider the simplest relativistic example: theories of a single scalar field in one space and one time dimension, with non-derivative interactions. The dynamics of such a theory are describe by the Lagrangian density
$$
\mathcal{L} = \frac{1}{2} \partial _ {\mu}\phi \partial ^{\mu}\phi - U(\phi).
$$
The energy is given by a Legendre transformation $H = L - p\dot{q}$, we get 
$$
H = \int d x \,  \left[  \frac{1}{2}(\partial _ {0}\phi)^{2}+\frac{1}{2} (\partial _ {1}\phi)^{2}+U(\phi) \right].
\tag{1}
$$
We sometimes write the total energy as the sum of kinetic and potential energy,
$$
E = T+V
$$
where $T$ is the term quadratic in time derivatives, namely the first term in Eq.(1), and $V$ is the term involving no time derivatives. 

- - -

There are two models we will consider here. First let's take a look at the phi-fourth theory. There are two degenerate vacua, corresponding to the two directions of the boundary of the space. The potential energy is 
$$
U = \frac{\lambda}{2} (\phi^{2}-a^{2})^{2}.
$$
The vacuum configuration is clearly given by $\phi = \pm a$ a constant in spacetime. In a different form $a$ is written as $a = \mu^{2} / \lambda$. 

Next let's consider the sine-Gordon potential, 
$$
U = \frac{\alpha}{\beta^{2}} (1-\cos \beta \phi).
$$
The ground states have infinite degeneracy. 

We want to find the time-independent solutions of the equations of motion. We need to find the stationary point of the energy function, which is very similar to finding the stationary point of the action, with one difference: the sign of the potential term. Mathematically, looking for the time-independent solution is the same as looking for the motion of a particle of unit mass in a potential equal to **minus** $U(x)$. 

To emphasize, **we can turn a static problem of finding the time-independent solution that minimizes the Hamiltonian, to a dynamical problem of finding the motion of a particle (of unit mass) in a reversed potential.** The latter allows us to make use of our intuition and imagination, and helps to visualize the solution.

Every motion of the particle in the potential corresponds to a time-independent solution of the field equations, but not all of them are of finite energy. For the energy integral to converge, the energy density must go to zero at space infinity. In terms of the particle problem, this boundary conditions fixes the possible initial and final positions. 

In the example of the phi-fourth theory, the potential takes the form of double-well. The minus version of the potential is of the form double hill. It would be helpful to draw some picture here but I am too lazy, interested readers should just read Coleman's book. The lump solution corresponds to the motion that the particle starts off from one of the hills and rolls over the valley and reaches the other hill and stays there.

By convention, the solution for which $\phi$ is monotone increasing `lumps` and those for which it is monotone decreasing `antilumps`.

To find the exact expression of the solution, let's adopt the dynamic picture of a moving particle. The potential is now $-U(x)$ where $x$ is identified with $\phi$ in the static problem. The total energy is conserved to zero during the whole motion, thus 
$$
\frac{1}{2} \left( \frac{dx}{dt} \right)^{2} - U(x) = 0.
$$
We can translate this back into field language by substitution $x\to \phi$ and the solution can be read off instantly in the integral form,
$$
\phi(x) = \pm\int d x \,[2U(\phi(x))]^{1/2}
$$
or 
$$
x = \pm\int_ {\phi_ {0}}^{\phi} d\phi \,  [2U(\phi')]^{- 1/2}.
$$

Note that the solutions enjoys the translation symmetry, meaning the center of the lump can be translated to anywhere. 

These equation also enables us to simplify the expression for the energy of a lump, thanks to the fact that a lump satisfies the equation of motion. 

For phi-fourth theory, we find for the form of the lump
$$
\phi = a \tanh(\mu x).
$$
The energy of the lump is given by 
$$
E = \frac{4\mu^{3}}{3\lambda}.
$$
The lumps of $\phi^{4}$ theory is frequently called `kinks` in the literature.

For the sine-Gordon theory, we find 
$$
\phi = \frac{4}{\beta} \tan^{-1} \exp(\alpha^{1/2}x)
$$
where which branch of the inverse tangent we choose determines which two zeros we move between. The energy of the lump is 
$$
E = \frac{8\alpha^{1/2}}{\beta^{2}}.
$$
The lumps of sine-Gordon theory are frequently called `solitons` in the literature. In both cases the antilumps are obtained simply by multiplying by minus one.