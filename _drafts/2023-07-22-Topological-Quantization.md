---
layout:     post   				    # 使用的布局（不需要改）
title:     Line Bundle, Topological Quantization and Berry Phase 			# 标题 
subtitle:   
date:       2023-07-22 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background1.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Frankel
---

### A Generalization of Gauss-Bonnet

Let $E\to M$ be a complex line bundle, we suppose the structure group is $U(1)$, 
$$
\psi_ {V} = e^{ i\alpha }\psi_ {U}.
$$
Let $\omega$ be a $U(1)$ connection, which is a ${\frak g}$-valued 1-form on $M$. It is also pure imaginary.

If 
$$
\Psi = \mathbf{e}_ {U}\psi_ {U},\quad  \Phi = \mathbf{e}_ {U}\phi_ {U}
$$
be two sections. Then we can define a coordinate independent scalar product between these two sections,
$$
\overline{\psi}_ {V}\overline{\phi}_ {V} = \overline{\psi}_ {U}\overline{\phi}_ {U},
$$
where $\overline{\psi}$ means the complex conjugate of $\psi$.

We write 
$$
\left\langle \Psi,\Phi \right\rangle := \overline{\psi}\phi.
$$
We then say that $E$ is a `hermitian line bundle`. 

If we put 
$$
\nabla \psi = (d+\omega)\psi
$$
then 
$$
\left\langle \nabla \Psi,\Phi \right\rangle +\left\langle \Psi,\nabla \Phi \right\rangle =d(\psi \phi)
$$
where the term involving $\omega$ cancels out due to the fact the $\overline{\omega}=-\omega$. 

Let $\mathbf{e}_ {U}$ be a frame over $U$, that is a norm one complex line section. Then the coordinates of $\Psi$ takes value in $U(1)$ group, 
$$
\Psi = \mathbf{e}_ {U} \psi_ {U} = \mathbf{e}_ {U}e^{ i \alpha }.
$$

This is the most general section of $E$ over $U$. 

Let $V$ be an oriented closed surface (dimension 2) embedded in $M$. The points of $FM$ over $V$ defines a new frame bundle over $V$, again we call it $FV\to V$ or $E_ {V}$, which means $E$ restricted to $V$. 

We wish to consider a smooth section of $E$ over $V$, but it may not exist, for example consider the hairy ball theorem, a tangent vector on $\mathbb{S}^{2}$ must have at least one singularity. Then we can take a step back and be satisfied with a section with some singularities, which is always possible. To see it, first consider a section $s: V\to E$ of the complex line bundle, then putting $\Psi = s / \left\lVert s \right\rVert$ at those $p\in V$ where $s\neq 0$. Now consider the zero section $0$. The questions is, what could the intersection between $\Psi$ and $0$ be? Such intersections must be singularities because there is no smooth way for a norm one complex line to go to zero. Now, both $\Psi$ and $0$ are submanifolds of $E_ {V}$ which is dimension $4$. All sections have the same dimension as the base space so both $\Psi$ and $0$ are $2$ dimensional. Then the section in general is or dimension $4-2-2=0$. Thus the intersection comprises of a set of points. In other words, we expect to find a nonvanishing section of $E$, and a resulting *frame bundle* $FM$, over all $V$ except for perhaps some finite points $p_ {1},\dots,p_ {N}$. 

let then $\Psi$ be such a section. We construct the *connection form*
$$
\omega ^\ast = \pi ^\ast \omega+id\alpha.
$$

We define the `index` of $\Psi=\mathbf{e}\psi=\mathbf{e}e^{ i\alpha }$ at the zero $p_ {k}$ to be 
$$
j_ {\Psi}(p_ {k}) := \frac{1}{2\pi} \oint_ {\partial D}d\alpha
$$
where $D$ is some infinitesimal disk surrounding $p_ {k}$. 

Then, there a theorem telling us that 
$$
\frac{i}{2\pi}\iint_ {V} \theta = \sum_ {k} j_ {\psi}(p_ {k}) \in  \text{integer}.
$$

**Theorem.** Let $E$ be a hermitian line bundle with pure imaginary connections $\omega$ and curvature $\theta$, over a manifold $M$. Let $V$ be any oriented closed surface embedded in $M$. Then 
$$
\frac{i}{2\pi}\iint_ {V} \theta
$$
is an integer and represents the sum of the indices of any sections 
$$
s: V\to E.
$$
It is assumed that $S$ has finitely many zeros on $V$. $i\theta / 2\pi$ is called the `Chern form` of $E$.

**Intersection number**

The intersection number tells us in quality how a section $s$ intersects the $0$-section $0$, counted with multiplicity. By this we mean the following. Let $E$ be a rank-$n$ vector bundle over an $n$-dimensional manifold $M$. We assume that
- $M$ is oriented,
- The vector fiber $F$ is orientable in a continuous way. This is the case when the structure group of $F$ is a connected group.
Let $x^{} {1},\dots,x^{n}$ be positively-oriented coordinates of $M$ and let $u^{1},\dots,u^{n}$ be the coordinates of the fiber. Let the intersection point be $x=0,u=0$. The section $s$ can be described by the $n$ functions $n^{i}(x),i=1,\dots,n$. 

We say that the section $s$ intersects $0$ `transversely` if the Jacobian
$$
\left\lvert \frac{\partial u}{\partial x} \right\rvert \neq  0
$$
at $x=0$. It is also said that $s$ has a `nondegenerate` zero at $x= 0$. From
$$
\frac{du^{j}}{dt} = \frac{\partial u^{j}}{\partial x^{i}} \frac{dx^{i}}{dt}
$$
we see that `transversality` simply means that $s$ and $o$ don't have any nontrivial tangent vectors in common. So, when $s$ intersects with $0$ transversally at $x=0$, we define the `local intersection number` to be $+1$ (-1), provided the Jacobian is positive (negative). The total intersection number is the sum of all the local intersection numbers at all the intersections. 

Consider a complex line bundle $E\to\mathbb{S}^{2}$ over the Riemann sphere. We may use $z=x+iy$ as the local coordinates of the Riemann sphere near $z=0$. Use $\zeta=u+iv$ for fiber coordinates. A section $s$ is given by
$$
u=u(x,y),\quad v=v(x,y) \text{ or } \zeta=\zeta(z,\overline{z}).
$$
