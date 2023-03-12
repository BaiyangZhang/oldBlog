---
layout:     post   				    # 使用的布局（不需要改）
title:     The Geometry of Surfaces			# 标题 
subtitle:   Theodore Frankel
date:       2023-3-12 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt1.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*


### Fundamental Forms, the First and Second

Let $M^{2}\subset \mathbb{R}^{3}$ be a 2D surface in 3D space, $M^{2} = F(U)$ where $U$ is a subset of $\mathbb{R}^{2}$ and $F_ {\ast}$ is a map of rank two. Denote the coordinates of $U$ as $u_{1}=u,u_{2}=v$.

A curve on $M^{2}$ is denoted by $x(t) = x(u(t))$, where $u(t)$ is a curve on $U\subset \mathbb{R}^{2}$. The basis vectors for the tangent space on $M^{2}$ at each point can be inherited from the basis vector of $U$, by defining
$$
X_ {\alpha} := \frac{ \partial x }{ \partial u^{\alpha} }.
$$
We can then introduce the metric tensor
$$
g_ {\alpha \beta}=\left\langle X_ {\alpha},X_ {\beta} \right\rangle
$$
and use it to calculate the inner product of any pair of vectors,
$$
ds^{2} = \left\langle dx,dx \right\rangle =g_ {\alpha \beta}du^{\alpha}du^{\beta}.
$$
This quadratic form associated to the metric tensor is called the `first fundamental form`. Note that here we are considering $u^{\alpha}$ and $u^{\beta}$ as functions on $U$ and $du^{\alpha,\beta}$ are 1-forms, not infinitesimals. Thus $ds^{2}$ is a tensor, 
$$
ds^{2} = g_ {\alpha \beta} \;du^{\alpha}\otimes du^{\beta}.
$$

Consider the sphere of radius $a$ which can be parametrized by colatitude $\theta$ and the longitude $\phi$. We then have 
$$
ds^{2}=a^{2}(d\theta^{2}+\sin ^{2}\theta d\phi^{2}).
$$

Once we know the metric, we can evaluate the total length of a curve, the angle between two vectors, etc.

For *element of area*, we state without proof that 
$$
ds = \sqrt{ g }du\wedge dv.
$$

- - -

We would like to make a remark on how to look at $d\mathbf{x}$, which is short for $dx^{i}$ with $i$ takes value in $1,2,3$. Here $\mathbf{x}$ is supposed to denote a vector, hence the bold font. Classically, $d\mathbf{x}$ is considered as an infinitesimal displacement, or infinitesimal vector. Let $\mathbf{x}$ be a *position vector* (so we are **not** talking about affine space) starting from the origin and end at some point on $M^{2}$, which is a surface in $\mathbb{R}^{3}$, then $\mathbf{x}+d\mathbf{x}$ gives us another vector, whose endpoint is $d\mathbf{x}$ away from $\mathbf{x}$, and $d\mathbf{x}$ is a infinitesimal vector which lies in the tangent plane at $\mathbf{x}$. 

However, in our language, $d\mathbf{x}$ is mixed tensor. Let $u^{I},I=\{1,2\}$ be the local coordinates. It means that, see the surface in $\mathbb{R}^{3}$ as the image of mapping $F(U)$ where $U$ is the subset of $\mathbb{R}^{2}$, then $u^{I}$ is the flat coordinates of $\mathbb{R}^{2}$. Then 
$$
d\mathbf{x} = \mathbf{x_ {i}} \otimes du^{i}, \quad   \mathbf{x}_ {i}=\frac{ \partial \mathbf{x} }{ \partial u^{i} } .
$$
The vector $\mathbf{x}_ {i}$ is the (components of) induced vector in $\mathbb{R}^{3}$ by $\partial / \partial u^{i}$ in $U$. Classically the tensor product sign is omitted. We shall think of the mixed tensor as a `vector valued 1-form`, that is, a 1-form whose value on any tangent vector $\mathbf{v}\in TU$ is a vector, rather than a scalar. For this particular vector valued 1-form, we have 
$$
d\mathbf{x}(v) = \mathbf{x_ {i}} \otimes du^{i}(v) = \mathbf{x_ {i}} v^{i} = {\mathbf{\widetilde{v}}}
$$
where $\widetilde{v}$ is the image of $\mathbf{v}\in TU$ which is a vector in $\mathbb{R}^{3}$.

- - -
**The second fundamental form**

Whenever we discuss the normal to a surface we shall assume that one of the two possible local normal fields has been chosen.

Let 
$$
\mathbf{N} = \frac{\mathbf{x}_ {u} \times \mathbf{x}_ {v}}{\left\lvert \mathbf{x}_ {u} \times \mathbf{x}_ {v} \right\rvert }
$$
be the unit normal to $M^{2}$ at a point $(u^{1},u^{2})$. Given any tangent vector $\mathbf{X}$ at the same point, let $u^{\alpha}(t)$ be a curve on $M^{2}$ having $\mathbf{X}$ as tangent at $u(0)$; $du(t) / dt = \mathbf{X}$. Then, since $\mathbf{N}$ is a unit vector, the derivative of it is tangent to $T_ {(u^{1},u^{2})}(M^{2})$. Then
$$
\frac{d}{dt} \mathbf{N} = \frac{ \partial \mathbf{N} }{ \partial u^{i} } \frac{du^{i}}{dt} =: \mathbf{N}_ {i} \frac{du^{i}}{dt} = \mathbf{N}_ {i} \mathbf{X}^{i}.
$$
The assignment (The minus sign being conventional)
$$
\mathbf{X} \mapsto - \mathbf{N}_ {i} \mathbf{X}^{i} =: b(\mathbf{X})
$$
defines a linear transformation
$$
b: TM^{2} \to TM^{2}.
$$

Its matrix form $b^{\alpha}\, _{\beta}$  in the basis $\mathbf{x}_ {\alpha}$ works as 
$$
b(\mathbf{x}_ {\beta}) = \mathbf{x}_ {\alpha} b^{\alpha} _ {\beta} = -\mathbf{N}_ {\beta}.
$$
These are called the `Weingarten equations`.

The bilinear form $B$ associated to $b$ is given by
$$
B(X,Y) = \left\langle X,b(Y) \right\rangle,
$$
as a tensor, $B$ is given by the `second fundamental form`
$$
-\left\langle d\mathbf{x},d\mathbf{N} \right\rangle =-\left\langle \mathbf{x}_ {\alpha},\mathbf{N}_ {\beta} \right\rangle du^{\alpha}\otimes du^{\beta} .
$$

After some derivation we find that, along a curve $u(t)$, the change of the normal vector is given by the second fundamental form 
$$
\frac{d\mathbf{N}}{dt} = -\mathbf{x}_ {\alpha} b^{\alpha}_ {\beta} \left( \frac{du^{\beta}}{dt} \right).
$$
For example, if $b=0$ then $d\mathbf{N} / dt=0$, the space is flat.

We may write for the second fundamental form 
$$
B = b_ {\alpha \beta}du^{\alpha}du^{\beta}
$$
where 
$$
b_ {\alpha \beta}=g_ {\alpha \gamma}b^{\gamma}_ {\beta}.
$$
We shall exhibit a more useful form to calculate $b_ {\alpha \beta}$. Put
$$
\mathbf{x}_ {\alpha \beta} := \frac{ \partial ^2\mathbf{x} }{ \partial u^{\alpha}\partial u^{\beta} }.
$$
Since $\mathbf{N}$ is normal thus $\mathbf{x}_ {\alpha} \cdot \mathbf{N}=0$, and 
$$
0= \frac{ \partial  }{ \partial u^{\beta} } \left\langle \mathbf{x}_ {\alpha},\mathbf{N} \right\rangle = \left\langle \mathbf{x}_ {\alpha \beta},\mathbf{N} \right\rangle+\left\langle \mathbf{x}_ {\alpha},\mathbf{N}_ {\beta} \right\rangle   =\left\langle \mathbf{x}_ {\alpha \beta},\mathbf{N} \right\rangle -b_ {\alpha \beta},
$$
that is, 
$$
\boxed{
\left\langle \mathbf{x}_ {\alpha \beta},\mathbf{N} \right\rangle = b_ {\alpha \beta}
}
$$
which is the formular to calculate $b_ {\alpha \beta}$. We can also see that $b_ {\alpha \beta}$ is symmetric w.r.t. $\alpha$ and $\beta$, which means $B$ as a bilinear form is self-adjoint, of which we will say more next.


### Gaussian and Mean Curvature

**Symmetry and Self-Adjointness**

In general, let $\hat{a}$ be an operator, then the `adjoint` of $\hat{a}$, denoted $\hat{a}^\ast$, is another operator defined by 
$$
\left\langle X,\hat{a}Y \right\rangle =\left\langle \hat{a}^\ast X,Y \right\rangle .
$$
If $\hat{a}=\hat{a}^\ast$ then $\hat{a}$ is said to be `self-adjoint`. In terms of bilinear form $A$ associated with $\hat{a}$, $A$ is self-adjoint provided
$$
A(X,Y) = \left\langle X,\hat{a}Y \right\rangle  = \left\langle \hat{a}X,Y \right\rangle = \left\langle Y,\hat{a}X \right\rangle  = A(Y,X).
$$
That is, **the linear transformation (operator) $\hat{a}$ is self-adjoint iff the associated bilinear form $A$ is symmetric.** 

Note that when we say $A$ is symmetric, in terms of coordinates we are saying $A_ {\alpha \beta}=A_ {\beta \alpha}$, note the position of the indices! They must all be downstairs, or up-stairs, it doesn't matter, as long as they are at the same position! It doesn't make sense to say that two indices at different positions are symmetric or not. The reason is that, *only when the two indices are both up-stairs or down-stairs, then their symmetry is independent of the choice of basis*.

We see that the second fundamental form $B$ is symmetric thus the linear transformation
$$
b: M^{2} \to M^{2}
$$
is self-adjoint! The special eigenvalue behavior of a self-adjoint transformation will have remarkable geometric consequences in the case of the linear transformation $b$.

**Principal Normal Curvatures**

Let $x=x(s)$ define a curve $C$ parametrized by the arc length (so that the velocity vector is always of unit length), on the surface $M^{2}$ in $\mathbb{R}^{3}$. The unit tangent at $x(0)$ is then $\mathbf{T} = d\mathbf{x} / ds = \mathbf{x}_ {\alpha} du^{\alpha} / ds$. The `curvature vector` for $C$, as a space curve, at $x(0)$ is 
$$
\kappa = \kappa \mathbf{n} = \frac{d\mathbf{T}}{ds}
$$
where $\mathbf{n}$ is the principal normal to $C$. The component of $\mathbf{T}$ in the direction normal to the plane is 
$$
\left\langle \kappa \mathbf{n}, \mathbf{N} \right\rangle = B(\mathbf{T},\mathbf{T}).  
$$
Geometrically, $\kappa^{-1}$ is the radius of the tangent circle at $x(0)$. 

We define the **principal (normal) curvature** of $M$ at $p=x(0)$ by 
$$
\kappa_ {1}(p) = \text{max } B(\mathbf{T},\mathbf{T})
$$
and 
$$
\kappa_ {2}(p) = \text{min }B(\mathbf{T},\mathbf{T})
$$
for unit $\mathbf{T}\in M^{2}_ {p}$. The two directions $\mathbf{T}_ {\alpha},\alpha=1,2$ yielding these extrema are called the` principal directions` for $M$ at $p$. But $b$ is self-adjoint (i.e., $B$ is symmetric), and linear algebra tells us the following:

**Theorem.** $\kappa_ {1}$ and $\kappa_ {2}$ are the eigenvalues of $b$ and the corresponding principal directions $\mathbf{T}_ {a}$ are the eigenvectors,
$$
b(\mathbf{T}_ {a}) = \kappa_ {a}\mathbf{T}_ {a}.
$$
If $\kappa_{1}\neq \kappa_ {2}$ then these two eigenvectors are automatically orthogonal. 

Of course if $\kappa_ {1}=\kappa_ {2}$ then all the normal curvatures at $p$ coincide; $p$ is then called an `umbilic` point. The usual round 2-sphere consists entirely of umbilic points.


**Gauss and Mean Curvatures: The Gauss Normal Map**

We now define two measures of curvatures of a surface $M^{2}$ at $p$, they corresponds to two operations we can do to a matrix: taking trace and taking the determinant. They are both invariant under a change of basis hence of invariant meaning.

- `Gauss Curvature`:
 $$K:= \det b = \frac{\det(b_ {\alpha \beta})}{\det(g_ {\alpha \beta})}=\kappa_ {1}\kappa_ {2}.$$
- `Mean curvature:`
$$
H:= \text{tr }b = b^{\alpha}_ {\alpha} = \kappa_{1} + \kappa_ {2}.
$$
Note that since $b$ is sent into $-b$ under a change of normal, $H$ will be sent into its negative but $K$ is invariant under choice of normal!

**Warning:** In some texts the mean curvature is defined to be the true curvature $(\kappa_{1}+\kappa_ {2}) / 2$.

The next fact might come in handy when it comes to calculations. Let 
$$
A: \mathbb{R}^{n} \to \mathbb{R}^{n}
$$
be a linear transformation on the vector space, the pull-back by $A$ of n-form $\omega$ satisfy
$$
A^{\ast }\omega = \det (A) \;\omega,
$$
it can be proved by writing down the expression and make use of the antisymmetric property of n-forms. 

If $M^{2}\subset\mathbb{R}^{3}$ is a surface with given normal field, we define the `Gauss (normal) map`
$$
n: M^{2} \to \text{unit sphere }\mathbb{S}^{1}
$$
by 
$$
n(p) = \mathbf{N}(p), \text{ the unit normal to } M \text{ at } p.
$$

Define the positive orientation of $\mathbb{S}^{2}$ by using the outward pointing normal. This Gauss map, or normal map, maps a neighborhood of point $p\in M^{2}$ to an area on the unit sphere. Without proof we state that
$$
\lim_{ U \to p } \frac{\text{signed area of }n(U)}{\text{signed area of }U} = K(p),
$$
as the neighborhood shrinks to $p$. This was Gauss's original definition of $K$.

### The Brouwer Degree of a Map: A Problem Set

The situation of mapping a compact oriented manifold into another of the same dimension plays an important and recurring role in mathematics and its applications. We shall discuss the topological implications of this situation, first studied in detail by the Dutch mathematician L. E. J. Brouwer around the turn of the twentieth century.

Let 
$$
\phi: M^{n} \to V^{n}
$$
be a *smooth* map from one closed oriented manifold to another of the same dimension. 

We introduce a n-form on $V$, denoted $\omega^{n}$, subject to the single condition that it be normalized,
$$
\int_ {V} \omega  =1.
$$
The `Brouwer degree` of $\phi$ is defined by 
$$
\boxed{
\text{deg }(\phi) =  \int _ {M} \, \phi ^\ast \omega .
}
$$

Note that we may also write the degree as 
$$
\text{deg}(\phi) = \int _ {\phi (M)} \, \omega.
$$

The Brower degree tells us *how many times, algebraically, the image of $M$ wraps around $V$*. 

It can be shown that $\text{deg}(\phi)$ is well defined, independent of the choice of the form $\omega$. 

The geometric significance of Brouwer degree is given by the following:

**Theorem.** Let $y\in V$ be a regular value of $\phi: M \to V$, that is, $\phi_ {\ast}$ at $\phi^{-1}(y)$ is onto. Recall that Sard's theorem says that the regular values of $\phi$ are dense in $V$. For each $x\in \phi^{-1}(y)$, the map between tangent vector spaces $\phi_ {\ast}: M_ {x}  \to V_ {y}$ is also one-to-one; that is, $\phi_ {\ast}$ is an isomorphism. Put
$$
\text{sign } \phi(x) = := \pm 1
$$
where the plus sign is used iff $\phi_ {\ast}$ preserves the orientation. Then 
$$
\text{deg}(\phi) = \sum_ {x\in \phi^{-1}(y)} \text{sign }\phi(x).
$$

As a corollary, the degree is always an integer. 

As a simple example, consider $V=\mathbb{S}^{1}$ and $M$ is a simple closed loop. Then the degree is called the `winding number` of the curve $M$. 

- - -

**Complex Analytic (Holomorphic) Maps**

Consider a map
$$
f: \mathbb{C} \to\mathbb{C}
$$
where $f$ is given by an analytical function $Z=f(z)$ in the complex plane. We will consider the complex plane as a complex one-dimensional manifold, $\text{dim}_ {\mathbb{C}}=1$. If we write, as usual, $z=x+iy$ and $f(z) = u+iv$, then $u,v$ must satisfy the Cauchy-Riemann condition. The differential $f_ {\ast}$ of the map $f$ is given by 
$$
\frac{df}{dt} = \frac{df(z)}{dt} = \frac{df(z)}{dz} \frac{dz}{dt} = f'(z) \frac{dz}{dt}.
$$
Thus $f_ {\ast} = f'$. 

Consider a **Polynomial map** $P: \mathbb{C} \to \mathbb{C}$, given by 
$$
P(z) = z^{n} + a_ {n-1} z^{n-1} +\dots+a_{0}.
$$
$\mathbb{C}$ is not compact so we can't talk about Brouwer degree of this map. But $\left\lvert z \right\rvert^{n}\to \infty$ as $\left\lvert z \right\rvert\to \infty$ and since $P$ behaves like $z^{n}$ for $\left\lvert z \right\rvert$ large, we can see that $P$ extends to a continuous map (again called $P$) of the Riemann sphere into itself by putting $P(\infty)=\infty$. Note that this is true for polynomial maps, not true for exponential maps $e^{ z }$.

We need to discuss the smoothness at $\left\lvert z \right\rvert=\infty$. Near $\left\lvert z \right\rvert=\infty$ we introduce the coordinate $w=1 / z$ and the map mentioned before can be expressed in the form 
$$
w \to W(w).
$$
To be specific, we have 
$$
w = \frac{1}{z} \to \frac{1}{z^{n}+\dots+a_{0}} = \frac{w^{n}}{a_{0}w^{n}+\dots+a_ {n-1}w+1} =W(w)
$$
which is smooth at $w=0$. 

We may now discuss the Brouwer degree of this polynomial map of the Riemann sphere into itself. Deform the polynomial map by considering, for $0<\epsilon<1$, 
$$
z\to z^{n} +\epsilon(a_ {n-1}z^{n-1}+\dots+a_{0}).
$$
We can rewrite it in terms of $w=1 / z$, then we would get a smooth function in $\epsilon$ and $w$ near $w=0$. We have defined a smooth deformation of the original polynomial map of the Riemann sphere. 

The Brouwer degree of the nth-degree polynomial map of the Riemann sphere is the same as that of the map $z\to z^{n}$ , $w\to w^{n}$. Then the value $z=1$ shows that this degree is $n$.

**The Gauss-Bonnet Theorem**

Recall the Gauss normal map $n$ that maps the normal vector to a 1-shere of unit radius, and the Gauss curvature $K=\kappa_{1} \kappa_ {2}$. Recall we have 
$$
n^{\ast } \text{ Vol}^{2}_ {S} = K \text{ Vol}^{2}_ {M}.
$$
It implies that 
$$
\frac{1}{4\pi} \int _ {M} \, KdA = \text{deg} (n: M^{2}\to S^{2})
$$
where $dA$ is the area form. It is the degree of the Gauss map, which is an integer. *If we smoothly deform M, this integer must vary smoothly and thus it remains constant, even though K itself will change*. The left hand side of the above equation is called the `total curvature` of $M$. It can be read off by just looking at the picture of $M^{2}$, namely, 
$$
\int _ {M} \, KdA = 4\pi (1-g)
$$
where $g$ is the genus of a surface, that is, the surface of a multi-doughnut with $g$ holes.

This `Gauss-Bonnet theorem` is remarkable; a deformation of the surface might change the Gauss curvature everywhere but the total curvature remains unchanged! The **total curvature is a measure of the genus of the surface**.

- - -

**The Kronecker Index of a Vector Field.**

Let $M^{n}$ be a **closed** submanifold of $\mathbb{R}^{n+1}$. It is a fact that $M$ is the boundary of a compact region $U$, $M = \partial U$. Then the orientation of $\mathbb{R}^{n+1}$ and the normal vector of $M^{n}$ defined the orientation of $M$. Let $\mathbf{v}$ be a unit vector field on $M$, namely a map 
$$
v: M^{n} \to \mathbb{S}^{n}, \quad x\in M^{n}\mapsto \mathbf{z}(x)\in \mathbb{S}^{n}.
$$
$\mathbf{v}$ need not be tangent to $M$. If it is normal to $M$ then it is Gauss normal map.

We define the `Kronecker index` of $\mathbf{v}$ on $M$ by
$$
\text{index of }\mathbf{z} := \text{Brouwer degree of } \mathbf{v}: M\to S.
$$
If $\mathbf{v}$ is any vector field (non-zero) on $M$, then the Kronecker index is given by the index of the normalized version, $\mathbf{v} / \left\lvert v \right\rvert$.

Again, *the Kronecker index is an integer and invariant under the continuous deformation*.

**The Brouwer fixed point theorem.** Every smooth map $\phi$ of the closed $(n+1)$-ball 
$$
B^{n+1} = \left\{ x\in \mathbb{R}^{n+1} \,\middle\vert\, \left\lvert x \right\rvert \leq 1 \right\}
$$
into itself has a fixed point. 

- - -

**The Gauss Looping Integral.**

Let $C_ {1,2}: \mathbb{S}^{1}\to\mathbb{R}^{3}$ be a pair of non-intersecting smooth closed curves in space. Let $r_ {1,2}$ be their coordinates respectively, parametrized by $r_ {1}(\theta)$ and $r_ {2}(\phi)$. Gauss wrote down an integral describing how the curves "link".

Consider the abstract torus $T^{2}$ with coordinates $\theta,\phi$. Consider the map
$$
L: T^{2} \to\mathbb{S}^{2}, \quad L(\theta,\phi)= \frac{\mathbf{r}_ {2}(\phi)-\mathbf{r}_ {1}(\theta)}{\left\lvert \mathbf{r}_ {2}(\phi)-\mathbf{r}_ {1}(\theta) \right\rvert }:= \frac{\mathbf{r}_ {12}(\theta,\phi)}{\left\lvert \mathbf{r}_ {12}(\theta,\phi) \right\rvert }.
$$
The Gauss `looping` or `linking` number of $C_ {1}$ and $C_ {2}$ is defined to be the integer
$$
\boxed{
\text{Lk}(C_ {1},C_ {2}) := \text{deg}(L).
}
$$

To see the geometrical interpretation of the linking number, consider the closed, orientable surface $W$ whose boundary is  $C_ {1}$. The orientation of $\mathbb{R}^{3}$ picks out a preferred unit normal $\mathbf{N}$ to $W$. 

It is a fact that $C_2$ can always be moved slightly if necessary to ensure that it meets $W$ transversally. We may then consider the intersection number $W\;\circ\;C_ {2}$, defined to be the **signed** number of intersections of $C_ {2}$ with $W$, an intersection carrying a plus sign only if $C_ {2}$ is traversing $W$ in the same direction of $\mathbf{N}$. Then the linking number has the following interpretation.
$$
boxed{
\text{Lk}(C_ {1},C_ {2}) = W \;\circ\;C_ {2}.
}
$$

See Feynman's lectures [F, S, L, vol. II, pp. 14-10].

The linking number is a measure of how the curves link.

*It should be remarked that two wires can have linking number $0$ and yet be physically inseparable, as is indicated in our last illustration.*

Another way to look at the linking number is that, when we move $C_ {1}$ away while keep its shape, until it is moved far far away from $C_ {2}$, the linking number is how many times $C_ {1}$ cuts $C_ {2}$ in the process.

### Area, Mean Curvature, and Soap Bubbles

To study how does the area of a surface change as we move it in space, we begin with a class of surfaces $M(t)$ in $\mathbb{R}^{3}$, a **variation** of the initial surface $M(0)$.

We assume that $M(0)$ is a compact manifold, perhaps with boundary. We wish to calculate how the area of $M(t)$ varies with $t$. To make sure that all the surfaces are disjoint, we introduce the extra variable $t$. 

Now we have time variable $t$ and we can make it into dynamical a problem! We can write down the Lagrangian and try to solve the equation of motion, as usual. For example, it can be used to study the bubble growth. The study shows that, snice a soap bubble in equilibrium has spatially constant pressure inside (otherwise air would be in motion), it describes a surface of constant mean curvature. 

### Gauss's Theorema Egregium

**The Equations of Gauss and Codazzi**

Let $M^{2}$ be a surface in $\mathbb{R}^{3}$ with local coordinates $u^{1,2}$, then the vectors $\mathbf{x}_ {\alpha} = \partial\mathbf{x} / \partial u^{\alpha}$ can serve as the basis of the tangent plane. $\mathbf{x}_ {\alpha \beta}$ need not be tangent, in fact its normal components tells us how curve the surface is. Decompose into tangential and normal parts, called the `Gauss's surface equation`,
$$
\mathbf{x}_ {\alpha \beta}= \partial _ {\beta}\partial _ {\alpha}\mathbf{x} = \mathbf{x}_ {\gamma}\Gamma^{\gamma}_ {\beta \alpha} + b_ {\alpha \beta}\mathbf{N}
$$
where the coefficients $\Gamma^{\gamma}_ {\alpha \beta}=\Gamma^{\gamma}_ {\beta \alpha}$ are still to be determined. Now define
$$
\Gamma_ {\beta \alpha \mu}:=g_ {\gamma \mu}\Gamma^{\gamma}_ {\beta \alpha},
$$
then we have 
$$
\partial _ {\beta}g_ {\alpha \mu} = \Gamma_ {\beta \alpha \mu} + \Gamma_ {\beta \mu \alpha} 
$$
and we can solve for $\Gamma$ in terms of $g$, see Frankel's textbook. $\Gamma$ are the `Christoffel symbols`. 

Thus all the coefficients in Gauss's surface equations have been evaluated in terms of the first and second fundamental forms $g$ and $b$. Gauss now took a further step by calculating the consequences of the identity
$$
\mathbf{x}_ {\alpha \beta \gamma} = \partial _ {\gamma}\partial _ {\beta}\partial _ {\alpha}\mathbf{x} = \mathbf{x}_ {\alpha \gamma \beta},
$$
we get 
$$
\mathbf{x}_ {\alpha \beta \gamma}-\mathbf{x}_ {\alpha \gamma \beta}= \mathbf{x}_ {\tau}(R^{\tau}_ {\alpha \gamma \beta}-U^{\tau}_ {\alpha \beta \gamma})+V_ {\alpha \beta \gamma}\mathbf{N}
$$
where $R$ is the `Riemann` or `Riemann-Christoffel curvature tensor`. $U,V$ are given by combinations of various tensors and derivatives.

The expression of $R$ in terms of the second fundamental form $b$ is called the `Gauss's` equations. 

The Gauss's equations integrability conditions, that is, conditions that must be satisfied in order for these two matrices to be the first and second fundamental forms. In fact, Bonnet showed that these conditions are also sufficient to ensure the local existence of a surface having a prescribed $g_ {\alpha \beta}$ and $b_ {\alpha \beta}$.

**The Theorema Egregium**

Gauss's calculation of the Gauss's equation led him to one of the most important and surprising discoveries in all of mathematics. First , however, we need some background.

We are all familiar with geographical maps
$$
\phi: \mathbb{S}_ {a}^{2} \to \text{a portion of the plane }\mathbb{R}^{2}
$$
where $\mathbb{S}_ {a}^{2}$ is a portion of $\mathbb{S}^{2}$ of radius $a$. 

We say that a local mapping $\phi: M\to V$ of Riemannian manifolds is a `local isometry` if $\phi_ {\ast}$ preserves the length. If $\phi$ is a local isometry, then all lengths of curves, areas of regions, and angles between curves are preserved; in other words the map is` distortion-free`. A familiar example is when a flat sheet of paper is rolled up into a cylinder or a cone. Though the paper is "bent" there is basically no "stretching". The metric is also the same. Then the Christoffel symbols and the Riemann tensor, are also identical at corresponding points since they are constructed from the metric tensor alone!

Coming back to surfaces in 3D space, we have 
**Gauss's Theorema Egregium.** The Gauss curvature
$$
K = \kappa_ {1} \kappa_ {2} = R^{12}\\_ {12}
$$
is an `isometry invariant`.
