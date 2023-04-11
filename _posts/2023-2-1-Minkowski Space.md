---
layout:     post   				    # 使用的布局（不需要改）
title:     Minkowski Space			# 标题 
subtitle:   
date:       2023-2-1 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt8.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

### Curvature and Special Relativity


Given a curve $C:= \mathbf{x}=\mathbf{x}(t)$ in $\mathbb{R}^{3}$, its tangent vector is a column vector, denoted by $\dot{\mathbf{x}}(t)=(\dot{x},\dot{y},\dot{z})^{T}$. $t$ can be considered as time in physics problems and $\dot{\mathbf{x}}(t)$ would be the velocity. Introduce the arc length $s$ by means of 
$$
\left( \frac{ds}{dt} \right)^{2} = \left\lvert \dot{\mathbf{x}} \right\rvert^{2} = v^{2}, \quad s(t) = \int_{0}^{t} du \, \left\lvert \dot{\mathbf{x}}(t) \right\rvert.
$$

We then have the `unit tangent vector` $T:= d\mathbf{x} / ds=\dot{\mathbf{x}}dt / ds = \mathbf{v} / v$, that is $\mathbf{v}= v\mathbf{T}$. Then the acceleration is given by 
$$
\mathbf{a} = {\dot{v}}\mathbf{T} + v\mathbf{\dot{T}} = \dot{v}\mathbf{T} + v^{2} \frac{d\mathbf{T}}{ds}.
$$
Since $\mathbf{T}$ has constant length, ${d \mathbf{T}} / {ds}$ must be orthogonal to $\mathbf{T}$. The direction of ${d \mathbf{T}} / {ds}$ defines a unique unit vector normal to  the curve called the `principal normal` $\mathbf{n}$,
$$
\frac{d\mathbf{T}}{ds} = \kappa(s) \mathbf{n}(s)
$$
where $\kappa(s)$ is the `curvature` of curve $C$ at $s$. Then the acceleration is 
$$
\mathbf{a} = \dot{v}\mathbf{T} + v^{2}\kappa(s)\mathbf{n}.
$$
The plane spanned by $\mathbf{T}$ and $\mathbf{n}$ is called the `osculating plane`. There is an easy way to compute $\kappa$ in terms of the original parameter $t$ rather than $s$, note that 
$$
\mathbf{v}\times \mathbf{a} = v^{3}\kappa \mathbf{T}\times \mathbf{n},
$$
so 
$$
\kappa = \frac{\left\lvert \mathbf{v}\times \mathbf{a} \right\rvert }{v^{3}}.
$$

We define the `curvature vector` by
$$
\boxed{
\kappa=\frac{d\mathbf{T}}{ds}=\kappa \mathbf{n},
}
$$
note that it is $d\mathbf{T} / ds$ rather than $d\mathbf{T} / dt$.

The curvature $\kappa$ has an intuitive geometric interpretation. Consider three nearby points $\mathbf{x}(s-\epsilon),\mathbf{x}(s),\mathbf{x}(s+\epsilon)$ on a curve $C$. There three points are generically not colinear, and determine a circle. Intuitively speaking, the larger the curvature, the smaller the determined circle. Under mild conditions, it is shown that at $\epsilon\to {0}$ limit, the determined circle lies on the osculating plane and the radius of the circle $\rho(x)=1 / \kappa(s)$ is called the `radius of the curvature` of $C$ at $s$. The accelerator is 
$$
\mathbf{a} = \dot{v}\mathbf{T} + \left( \frac{v^{2}}{\rho} \right)\mathbf{n}.
$$

### Completion and Promotion

The laws of physics are Lorentz invariant, it means that physics quantities should transform "nicely" under Lorentz group. Given a 3-dimensional spatial infinitesimal displacement $d\mathbf{x}$, it needs to be `unified` with a fourth component $dt$ to form a Lorentz 4-vector $dx^{\mu}$. We say that $d\mathbf{x}$ is not relativistically `complete`. In Minkowski's words, 
>space by itself and time by itself have now faded away into mere shadows.

The problem is that, all the quantities we are familiar with from Newtonian physics are not Lorentz invariant. For example, take a look at the definition of velocity,
$$
\mathbf{v}= \frac{d\mathbf{x}}{dt} 
$$
 where both $\mathbf{x}$ and $t$ changes under Lorentz transform, they are actually different components of a single Lorentz 4-vector, by no reason should $\mathbf{v}$ behave nicely under Lorentz transform. However, if we change $dt$ to $d\tau$, since $\tau$ is a Lorentz scalar and $\mathbf{x}$ is a 3-vector, the new definition will have better Lorentz transform property, it at least transforms as a 3-vector. Thus we define 
$$
v_{r} = \frac{d\mathbf{x}}{d\tau} 
$$ where the subscript $r$ is for relativistic. Now $v_{r}$ is the 3-dimensional, spatial component of some 4-vector velocity. Obviously this 4-vector velocity is 
$$
u^{\mu}= \frac{dx^{\mu}}{d\tau}.
$$
This is what we should study in relativistic theory. 

We can further write everything in terms of non-relativistic quantities, escaping the use of $\tau$, as some authors like to do. For example, we can write 
$$
\frac{dt}{d\tau}=\frac{1}{\sqrt{ 1-\left( \frac{d\mathbf{v}}{dt} \right)^{2} }}=:\gamma
$$
and the four velocity would become
$$
u^{\mu}= \gamma(1,\mathbf{v}).
$$



### Electromagnetism in Minkowski Space

Electromagnetic field is best described in the language of differential forms. However, electric field and magnetic field are given by forms of different ranks. When it comes to counting the rank of forms, there are usually two ways to do it,
1. differential forms are what we integrate on a manifold, the dimension of the form must be the same as the dimension of the manifold on which it is integrated. For example, a form which we integrate on $\mathbb{R}^{3}$ is a 3-form.
2. Forms also are maps that turns vectors into numbers. We can count the rank of a form by counting how may vectors does it acts on. For example, if a form maps $V\otimes V$ to real numbers, then it must be a 2-form.

In our case, it is easiest to adopt the first method. Given a test charge of charge $q$, if it moves along a curve $C$ in electric field $E$, the work done to the charge is given by 
$$
W = q \int_{C} E,
$$
thus $E$ must be a 1-form. Similarly, the magnetic flux is given by the integral of magnetic field on some surface $S$
$$
\Phi=\int_{S} \, B
$$
thus $B$ must be a 2-form. 

However, that is what we have in 3-D space. In 3D space the basis of forms are $dx,dy$ and $dz$, turning to relativistic  4-D spacetime, we have an extra basis, namely $dt$. The expressions for electromagnetic field also needs some modification.

Let's start with the Lorentz force law. In non-relativistic case, the 3-dimensional Lorentz force is given by 
$$
\mathbf{f}=q(\mathbf{E}+\mathbf{v}\times \mathbf{B})
$$
where the speed of light is set to $1$. We need to `complete` this spatial force vector to Minkowski 4-vector force. Lucky for us there is a trick to do that. The 3-force can be written as 
$$
\mathbf{f} = \frac{d\mathbf{p}}{dt} = \frac{d m_{0}\mathbf{u}}{dt}
$$
where $\mathbf{u}$ is the three component of the four velocity $u$, $\mathbf{p}$ is the three momentum. As discussed before, a natural completion of the three momentum is the four momentum so in order to complete $\mathbf{f}$ we should replace $\mathbf{p}$ by the four momentum $P$, and we need to substitute $t$ for the Lorentz scalar $\tau$. Thus the four-force become
$$
f^{\mu} = \frac{d}{d\tau}(m,\mathbf{p})=\left( \frac{dm}{dt},\gamma  \frac{d\mathbf{p}}{dt} \right) = (f^{0},\gamma \mathbf{f}).
$$
To obtain $f^{0}$, notice that the inner product of $P$ and itself is a constant, 
$$
P^{2} = \left\langle P,P \right\rangle =\text{const}
$$
and as a consequence, the four momentum $P$ is perpendicular to $dP / d\tau$. Since $P=m_{0} u$ and $m_{0}$ is a Lorentz scalar, we have 
$$
\left\langle f,u \right\rangle =0= -\gamma f^{0} +\gamma^{2} \mathbf{f}\cdot \mathbf{v},
$$
from where we can work out $f^{0}$,
$$
f^{0} = \gamma \mathbf{f} \cdot \mathbf{v}.
$$

Putting everything together, we have complete  the three-force to the Lorentz contravariant four-force,
$$
\boxed{
f = \gamma (\mathbf{f}\cdot \mathbf{v}, \mathbf{f}).
}
$$
Substitute the expression for $\mathbf{f}$ as the Lorentz force, in terms of  classical vector form of electro-magnetic field, we have 
$$
f = \gamma q (\mathbf{E}\cdot \mathbf{v}, \mathbf{E}+\mathbf{v}\times \mathbf{B}).
$$
On the other hand, the force itself is a 1-form since we can integrate it along some path $C$ to evaluate the work done,
$$
W = \int_{C} \, f. 
$$


Coming back to the case of Lorentz force, to simplify the notations we write $E = E_{i}dx^{i}$ and $B= B_{i<j}\,dx^{i}dx^{j}$.  The 1-form expression of the Lorentz force
$$
f = -\gamma q\, i_{\mathbf{v}}E dt + \gamma q \, (E_{i}dx^{i}-i_{\mathbf{v}}B)
$$
where $i_{\mathbf{v}}$ is the inner product with vector $\mathbf{v}$. 

The Lorentz 1-form $f$ can be written as 
$$
f = -q i_{\mathbf{v}} F
$$
where
$$
F=E \wedge dt+B
$$
is the electromagnetic field strength 2-form. It was first introduced by Minkowski in 1907. 

### Maxwell's Equations

In Minkowski space we have 
$$
d = \mathbf{d}+dt\wedge \partial _{t}
$$
then half of the Maxwell equations are given by 
$$
dF = 0
$$
Following the Poincare's lemma, if the spacetime manifold is simply connected, 
$$
F = dA
$$
for some 1-form $A$. Then we can further express $E,B$ in terms of $A$, we would recover the familiar expressions.

To account for the other half of the Maxwell equation, we need to introduce the charged flux. Consider a charged fluid with local velocity $\mathbf{v}$, the current vector then is $\mathbf{j}=\rho \mathbf{v}$, $\rho$ is the density **measured in the inertial system $x$**. Let $\rho_{0}$ be the `rest charge density`, that is, the density measured by someone moving instantaneously with the fluid, then 
$$
\rho=\rho_{0} \gamma,
$$
this is due to the contraction of the space. Thus
$$
\mathbf{j} = \rho_{0}\gamma \mathbf{v}.
$$

Since $\rho_{0}$ is independent of the observer by definition, we can construct the so-called `current 4-vector`
$$
J:= \rho_{0} u = (\rho,\rho \mathbf{v}) := (\rho,\mathbf{J}).
$$
We may then construct the associated `current 3-form`
$$
\mathcal{J}=i_{\mathbf{J}}\text{vol}^{4}
$$
where $\text{vol}^{r}$ is the 4-volume form. Then the other half of the Maxwell's equations can be written as
$$
d\star F = 4\pi \mathcal{J}.
$$


