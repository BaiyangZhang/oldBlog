---
layout:     post   				    # 使用的布局（不需要改）
title:      Note on Kink-anitkink Scattering		# 标题 
subtitle:   Part 2
date:       2023-05-15 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background9.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - QuantumFieldTheory
    - Kink
    - Meson
---

### The Model

We will introduce the scalar field in (1+1) dimension. We regard the mass terms as a special type of self-interaction and put it in the interaction $U(\phi(x))$. The Lagrangian is 
$$
\mathcal{L} = \frac{1}{2} (\partial \phi)^{2} - U(\phi), \quad  (\partial \phi)^{2} \equiv\partial _ {\mu}\phi \partial ^{\mu}\phi.
$$
The Euler-Lagrange equation, or the equation of motion, is 
$$
\frac{\partial \mathcal{L}}{\partial \phi}= \partial_ {\mu} \frac{\partial \mathcal{L}}{\partial (\partial _ {\mu}\phi)}
$$
which in terms of $U(\phi)$ becomes 
$$
\partial _ {\mu}\partial ^{\mu}\phi + \frac{d U(\phi)}{d\phi} =0.
$$
For a static solution this simplifies to 
$$
\frac{d^{2}\phi}{dx^{2}} = \frac{dU(\phi)}{d\phi}.
$$
At a certain moment, the instantaneous energy is obtained by the Legendre transformation of the Lagrangian. Then the translational symmetry makes sure that the energy is a conserved quantity in time. Classically, given the field configuration, we just substitute it to the energy functional, then you have the total energy of the field configuration. After quantization, though, there will be infinite zero point energy. But for our concern we will just pretend it is not there and carry on to calculate the difference of energy. This is a common property to quantum field theory models, it is usually possible to calculate the **difference of something** rather than the things themselves, which will be divergent, as it often turn out to be. 

The vacuum manifold is the manifold given by the minimum of $U(\phi)$. If there exists non-trivial maps 
$$
\text{boundary of space} \to \text{vacuum manifold}
$$
then we can construct soliton solutions. If there exists non-trivial maps from
$$
\text{boundary of space-time} \to \text{vacuum manifold}
$$
then we can construct instanton solutions. 

The energy functional can be further simplified if we introduce the so-called `superpotential` whose derivative gives the potential 
$$
U(\phi) = \frac{1}{2} \left( \frac{dW(\phi)}{d\phi} \right)^{2}.
$$
Then the energy is given by 
$$
E[\phi] = \frac{1}{2} \int dx \, \left\{ \left( \partial _ {x}\phi \mp \frac{dW}{d\phi} \right) ^{2} \pm \boxed {  2(\partial _ {x}\phi)\left( \frac{dW}{d\phi} \right) }\right\},
$$
the boxed term can be easily shown to be a total derivative! The integral over 
$$
\left( \frac{\partial\phi}{\partial x} \right)  \frac{dW}{d\phi}= \frac{\partial W}{\partial x}
$$
is a surface term, whose value only depends on the boundary condition of $\phi$. We have
$$
E[\phi(x)] = \frac{1}{2} \int dx \, \left( \partial _ {x}\phi \mp \frac{dW}{d\phi} \right) ^{2} \pm W{\Large\mid}^{\phi(x=+\infty)}_ {\phi(x=-\infty)} 
$$
which is of the form $E = (\dots)^{2}+\mathrm{eq}$, the minimum of which is given by $\text{eq}=0$. 

Recall that for the (anti-)kink solution, the boundary condition is taken such that the potential $U(x)$ takes different vacua at different space boundaries, then $W(x=\pm\infty)$ is fixed. The kink equation will just be 
$$
\boxed { 
\partial _ {x}\phi \mp \frac{dW}{d\phi} = 0, \quad  U(\phi)=\frac{1}{2} \left( \frac{dW}{d\phi} \right)^{2}.
} 
$$
where the minus sign is chosen for kinks and plus for anti-kinks. This first-order PDF is called the BPS equation, named after Bogomolny, Prasad, and Sommerfield, the corresponding minimum of energy is called the BPS energy
$$
E_ {\text{BPS}} = W{\Large\mid}^{\phi(x=+\infty)}_ {\phi(x=-\infty)}.
$$
Any field configuration with energy equal to BPS energy is said to **saturate the BPS bound**.

In terms of the potential $U(x)$, the BPS equation becomes
$$
\partial _ {x}\phi = \frac{dW}{d\phi} = \sqrt{ 2U(\phi) },
$$
since the solution to it is a local minimum, the Euler-Lagrange equation is therefore automatically satisfied by solutions of the BPS equation, even though the latter is only a first order differential equation.

- - -
### Kink solution
Next we turn to a specific potential, the well-known phi-fourth model. The self-interaction is defined to be 
$$
U(\phi) = \frac{1}{4} (\phi^{2}-1 )^{2} ,
$$
here we write the potential in a dimensionless and mathematically convenient form. The minimum of $U(\phi)$ is given by $\phi = \pm 1$. If you draw the potential, you'll see that the potential has two symmetric minima and one maximal given by $\phi=0$. 

The topological non-trivial solution that connects one vacuum to another smoothly is the classical kink solution. Solve the BPS equation we find
$$
\phi_ {K} = \tanh \frac{x-a}{l_ {k}},\quad  l_ {k} =\sqrt{ 2 }.
$$
The position of the kink is $a$ and $l_ {k}$ the characteristic size of it. To get a moving kink we just Lorentz boost it by velocity $v$,

Besides the kink solution, there is another static solution given by the elliptic sine function. But first, a digression to elliptic functions.

**Jacobi elliptic functions**

The circular functions arise from ratios of lengths in a circle. In a similar manner, the elliptic functions can be defined by means of ratios of lengths in an ellipse. Many of the key properties of the elliptic functions follow from simple geometric properties of the ellipse.

![Elliptic](/img/jacobiEllipse.jpg)

The most general form of Jacobi elliptic functions take two input, the first input is like the variable and the second as a parameter that controls the behavior of the function. The first input, the variable, is usually written in two ways, $u$ and $\phi$, related by 
$$
u=\int_{0}^{\phi} d\theta \, \frac{1}{\sqrt{ 1-m \sin ^{2}\theta} }.
$$
The angle $\phi$ is called the amplitude, a rather confusing name to call an angle. 

To say more about the topic, we need to start with the elliptic integrals. The most general form of elliptic integral reads
$$
f(x)= \int dx \,  \frac{A+B}{C+D\sqrt{ S }},\quad  A,B,C,D,S\in \mathbb{R}[x], \,\text{deg}(S)=3\text{ or }4.
$$
*They can be considered as the generalization of the inverse of trigonometric functions.* 

Define something called `modulus` $k$ satisfy $0<k^{2}<1$. This is sometimes written in terms of $m:=k^{2}$ or the `modulus angle` $k=\sin \alpha$. The **incomplete** `elliptic integral` *of the first kind* reads 
$$
F(\phi,k)=\int_{0}^{\sin \phi} dt \,  \frac{1}{\sqrt{ (1-t^{2})(1-k^{2}t^{2}) }},\quad  1\leq k^{2}\leq 1.
$$
If we let $t=\sin \theta$ then
$$
F(\phi,k)=\int_{0}^{\phi} d\theta \,  \frac{1}{\sqrt{ 1-k^{2}\sin ^{2} \theta }}, \quad  0\leq \phi\leq \frac{\pi}{2}
$$
This is the *incomplete* `Legendre elliptic integral.` The complete Legendre elliptic integral is obtained by setting $\phi$ to its maximal value, i.e., $\phi=\pi / 2$ or $\sin \phi=1$. 

The incomplete elliptic integral of the *second kind* reads
$$
E(\phi,k)=\int_{0}^{\phi} d\theta \,  \sqrt{ 1-k^{2}\sin ^{2} \theta }.
$$

Similarly, the complete elliptic integral of the first kink can be obtained by setting $\phi=\pi / 2$.

As an example of the Jacobian elliptic function $sn$ we can write
$$
u(x=\sin \phi,k)=F(\phi,k)=\int_{0}^{x} dt \,  \frac{1}{\sqrt{ (1-t^{2})(1-t^{2}k^{2}) }}
$$
then the inverse of $u(x)$ is defined to be 
$$
x = sn (u,k)
$$
or 
$$
u(x,k)=\int_{0}^{x} dt \, \frac{1}{\sqrt{ (1-t^{2})(1-t^{2}k^{2}) }} .
$$

While there are 12 different types of Jacobian elliptic functions based on the number of poles and the upper limit on the elliptic integral, the three most popular are the co-polar trio of sine amplitude, $sn(u, k)$, cosine amplitude, $cn(u, k)$ and the delta amplitude elliptic function, $dn(u, k)$ satisfy
$$
sn^{2}+cn^{2}=1,\quad  k^{2}sn^{2}+dn^{2}=1.
$$


