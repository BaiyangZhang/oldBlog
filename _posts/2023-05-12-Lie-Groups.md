---
layout:     post   				    # 使用的布局（不需要改）
title:     Lie Groups, Invariant Vector Fields, and Forms		# 标题 
subtitle:   
date:       2023-05-12 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background1.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

Let $M(n,\mathbb{R})$ be the set of all $n\times n$ real matrices, it has $n\times n$ elements thus is topologically isomorphic to a $n\times n$ dimensional real space $\mathbb{R}^{n\times n}$. The *real general linear group* $\text{GL}(n,\mathbb{R})$ is the group of all *invertible* (with non-zero determinant) $n\times n$ real matrices. We can regard such matrices as a point $x$ in some space, with the coordinates given by all its elements $x_ {ij}$, then $\text{GL}(n,\mathbb{R})$ is a sub-space in $\mathbb{R}^{n\times n}$. The question is, what exactly is this subspace? Is it a codimension one open set or something? To answer this question, notice that the determinant is a map from $M(n,\mathbb{R})$ to $\mathbb{R}$ which is **continuous**. The image of $GL(n,\mathbb{R})$ under the map is $\mathbb{R} - 0$ and is open in regular topology, thus the preimage of determinant function is also open, namely $GL(n,\mathbb{R})$ is a open subspace of $M(n,\mathbb{R})$. The product and inverse are also continuous functions defined on $GL(n,\mathbb{R})$, thus when we consider $GL(n,\mathbb{R})$ as a manifold and the matrix points, product and inverse are smooth functions on this manifold. This brings as to the definition of a `Lie group`:

**Definition.** A `Lie group`$G$ is a manifold endowed with a product, that is, a map 
$$
G\times G \to G,\quad  (g,h)\mapsto gh
$$
making $G$ into a group. We demand that this map, as well as the "inversion map" be **differentiable**. 

For example, $\mathbb{R}$ is a Lie group under addition. This group is commutative, or `abelian`. The positive real numbers $\mathbb{R}^{+}$ also form a abelian group under multiplication. The real and complex general linear matrices $GL(n,\mathbb{R})$ and $GL(n,\mathbb{C})$ are also Lie groups under the usual matrix multiplication. The `special linear` group, $SL(n,\mathbb{R})$ is the subset of $GL(n,\mathbb{R})$ that have determinant one. For any matrix group, the adjective **special** means that the determinant is equal to one. Other examples include $\mathbb{T}^{n}$ the $n$-torus group, which is the abelian group of diagonal matrices of the form 
$$
z = \text{diag }\left\{ \exp i \theta_ {1},\dots,\exp i \theta _ {n} \right\} .\tag{1}
$$
The $\mathbb{T}^{n}$ group is topologically homeomorphic to $\mathbb{S}^{1}\times\dots \times \mathbb{S}^{1}$, $n$ copies of them. Since the circles are connected, it follows that $\mathbb{T}^{n}$ is also connected.

As a manifold, a Lie group is very special for the following reason. A Lie group always has two families of diffeomorphisms, the left and right translations. For $g\in G$, these translations are defined by
$$
L_ {g}: G \to G, \quad  h \mapsto gh, \text{multiply from the left}
$$
and similarly 
$$
R_ {g}: G \to G, \quad  h \mapsto hg, \text{multiply from the right.}
$$

**Theorem.** $U(N)$ is connected.

To see it, just notice that any unitary matrix can be diagonalized to a $\mathbb{T}^{n}$ under some similar transformation, we casually write it as $\mathbb{T}^{n} = g U(N) g^{-1}$ for some $g\in U(N)$. Then $U(N)=g^{-1}\mathbb{T}^{n}g$ is connected to $\mathbb{1}$ smoothly by varying $\mathbb{T}^{n}$ smoothly from $\mathbb{1}$. 

The subgroup $\mathbb{T}^{n}$ of $U (n)$ given by (1) is called a maximal torus of $U(n)$. Any conjugate $h \mathbb{T}^{n} h^{-1}$ of this maximal torus is also called a maximal torus. By the same type of reasoning we may deal with the rotation group.

**Theorem.** $O(n)$ consists of two connected components, and $SO(n)$ is the part connected with the identity. 

As our last example, consider the set of linear transformation of points in 1-dimension affine space. The points in 1-dimensional affine space are denoted by $(t,1)^{T}$ where $t$ is the coordinate and $1$ denotes that it is a point. A vector in affine space would be denoted by $(v,0)^{T}$, thus the difference of two points yields a vector. The linear transformations, $G=\mathbb{A}^{1}$, the affine group of lines. They consist of real $2\times 2$ matrices of form
$$
\begin{pmatrix}
x  & y \\
0 & 1 
\end{pmatrix}.
$$
with $x>0$. 

A matrix group is a subgroup of $Gl(n)$ that is also a submanifold of $Gl(n)$. 


### Invariant Vector Fields and Forms


Lie groups are special as manifolds in the sense that, given a tangent vector $X_ {e}$ at the unity $e$, we may use the group elements to translate $X_ {e}$ to each point of $G$, by left or right group action. The left-translated tangent vector $X_ {g}$ is given by 
$$
X_ {g} := L_ {g\ast}\, X_ {e}
$$
and the right-translated vector (denoted by the same notation)
$$
X_ {g}:= R_ {g\ast }\, X_ {e}.
$$
In this way we have two non-vanishing vector fields all over $G$. 

In fact, given a set of basis $X_ {i}$ of the tangent space $T_ {e}G$ at $e$, we can translate them to any point $g\in G$ thus yielding a basis $L_ {g\ast}\, X_ {i}$ of $T_ {g}G$. The importance of this claim has to do with the orientation of $G$ as a manifold. Recall that the orientation is defined by the order of basis, if we can translate the basis $X_ {i}$ to any point of the group then the group is orientable! We conclude that *every Lie group is a orientable manifold*.

Consider for instance, a closed orientable surface $M^{2}$ of genus $g$. We shall see that of these surfaces only the torus (genus $1$) can support even a single nonvanishing tangent vector field. To be specific, $\mathbb{T}^{2}$ supports two sets of vector fields $\partial_ {\theta}$ and $\partial_ {\phi}$ where $\theta$ and $\phi$ parametrize the circles in $\mathbb{T}\cong \mathbb{S}^{1}\times\mathbb{S}^{1}$. The Torus can be regarded as the abelian Lie group $\mathbb{S}^{1}\times\mathbb{S}^{1}$ with multiplication
$$
(\theta,\phi)\times (\theta',\phi'):=(\theta+\theta',\phi+\phi').
$$
Topologically, the **only** compact Lie group of dimension 2 is the torus.

A vector field $X$ on $G$ is said to be `left-invariant` or `right-invariant` if it is invariant under left or right translation, 
$$
L_ {h\ast }\,X_ {g} = X_ {hg}, \quad  \text{left invariant}
$$
and similarly for right invariant. 

We can define similar concept for differential forms. A differential form field $\omega$ on $G$ is said to be `left invariant` if 
$$
L_ {g}^{\ast }\, \omega_ {gh} = \omega_ {h}.
$$
Note the direction of the pull-back.

Consider the example of Lie group $G:=Gl(n)$ of invertible matrices. Let $t\to h(t)$ be a curve in $G$, namely a G-valued curve parametrized by one parameter $t$. Let $h(0)=h$ and $h'(0)=X_ {h}$, where $h'$ is the $t$-derivative of $h$. This curve is simply a matrix whose entries $h_ {mn}$ are functions of $t$, $h(t)$ describes a curve in $n^{2}$ dimensional space. Then $X_ {h}$ is simple the matrix whose entries are $t$-derivatives of $h$ at $t=0$, $h'_ {mn}(t=0)$. Of course just because $h(0)$ is in $G$ does not mean $h'(0)$ is also in $G$. Then for the constant matrix $g$, the curve $gh(t)$ given by matrix multiplication is the left translated curve of $h(t)$ by $L_ {g}$. The tangent vector of $gh(t)$ at $t=0$ is given by $gX_ {h}$, 
$$
L_ {g\ast }X_ {h} = gX_ {h}
$$
which is again the simple matrix multiplication. 

Note that in any Lie group, if $X_ {i}$ is a basis for the left invariant vector fields and if $\sigma^{i}$ is the dual basis of 1-forms, then this dual basis is automatically left invariant. This can be shown using the relation $f^{\ast}\alpha(X)=\alpha(f_ {\ast}X)$. Also, note that if $\alpha$ and $\beta$ are invariant differential forms on $G$ then so are $d\alpha$ and $\alpha \wedge\beta$. A left invariant area form is also called a left `Haar measure`, which can be seen as a convenient way to use the left action $L_ {g\ast}$ to translate some well-defined infinitesimal areas about the entire group space to measure quantities defined on it. 

### One-Parameter Subgroups

Recall that a group homomorphism is a map between groups 
$$
f: G\to H
$$
that preserves the group multiplication. If it is further one-to-one (injective) and on-to (surjective) then it is an isomorphism. The exponential function is an example of group homomorphism, since $e^{ a }e^{ b }=e^{ a+b }$ for $a,b\in\mathbb{R}$ we have
$$
\exp: (\mathbb{R},\times )\to (\mathbb{R}^{+},+).
$$

A `1-parameter subgroup` of $G$ is by definition a differentiable homomorphism (a path) 
$$
g: \mathbb{R}\to G,\quad  t\to g(t)\in G
$$
of the additive group of the reals into the group $G$. Thus
$$
g(s+t) = g(s)g(t) = g(t)g(s),\quad \text{(abelian)}.
$$

Next let's look at the most important example, the one parameter subgroup of matrix group $G$. As matrices  
$$
g(t+s)=g(t)g(s),\quad  \text{matrix multiplication.} 
$$
To find $g$ that satisfy the condition, let's take derivatives on both sides w.r.t. $s$ then put $s$ to zero,
$$
g'(t) = g(t)g'(0),\quad  g'(0)=\text{const matrix.} \tag{2}
$$
The solution is of exponential form,
$$
g(t) =g(0) \exp \left\{ t g'(0) \right\} .
$$
Since $g(0)=e$ for any homomorphism, since homomorphism has to map identity to identity, we conclude that 
$$
g(t) = \exp \left\{ tg'(0) \right\} ,\quad  g'(0)\in T_ {e}(G).
$$
This is also the most general one-parameter subgroup of matrix group.

The group multiplication property Eq. (2) tells us the how to proceed for arbitrary group. Regard $g'(0)$ as a tangent vector at $g(0)$ and regard the left multiplication by $g(t)$ as a map, Eq. (2) can be generalized to 
$$
g'(t) = L_ {g(t)\ast }\, g'(0), \quad L_ {g(t)\ast } \text{ is the induced map of }L_ {g(t)}.
$$
It says that, the tangent vector $X$ of the one-parameter subgroup (a curve, if you like) is *left translated* along the subgroup (curve). Thus, given a tangent vector $X_ {\mathbb{1}}$ at the identity $\mathbb{1}$ in $G$, 

*the 1-parameter subgroup of $G$ whose tangent at $\mathbb{1}$ is $X_ {\mathbb{1}}$ is the integral curve through $\mathbb{1}$ of the vector field $X$ on $G$ resulting from left translation of $X_ {\mathbb{1}}$ over all of $G$.*

The vector $X_ {\mathbb{1}}$ is called the `infinitesimal generator` of the 1-parameter subgroup.

For any Lie group $G$ we shall denote the 1-parameter subgroup whose generator at $\mathbb{1}$ is $X$ by
$$
g(t):= e^{ tX } \equiv \exp(tX).
$$

*Example.* The matrix 
$$
X=
\begin{bmatrix}
0 & -1 \\
1 & 0
\end{bmatrix}
$$
can be considered a tangent vector at $\mathbb{1}$ of group $G=GL(2,\mathbb{R})$. The 1-parameter subgroup of $G$ is 
$$
\exp(tX) = \begin{bmatrix}
\cos t & -\sin t \\
\sin t & \cos t
\end{bmatrix}.
$$

Note that $X$ is a vector and $\exp X$ is a group element, different things fundamentally.

### The Lie Algebra of a Lie Group

Let $G$ be a Lie group regarded as a manifold (with group structure), the tangent vector space at the identity $\mathbb{1}$ of $G$ plays an important role and is denoted by Gothic letter ${\frak g}$. Sometimes it is denoted by script letters, which we will not do here. 

**Definition.** The Lie group ${\frak g}$ of group $G$ is 
$$
{\frak g}:= T_ {\mathbb{1}}\,G.
$$

The fancy notation might appears to be pretentious and uncomfortable at first, but once you get used to it, you'll find them clear and precise. You'll never mistake a point in the group space with a vector at the origin.

Let $X_ {i}$ be a basis for ${\frak g}$, we will also use $X_ {i}$ to denote the left translation of this vector to all of $G$. Since any left invariant vector field is determined by its value at $\mathbb{1}$, the most general left invariant vector field is then of the form
$$
X = \sum_ {i} v^{i}X_ {i},\quad  v^{i} \text{ are constants.}
$$

Let $\sigma^{i}$ be the dual basis of left invariant 1-forms on $G$. They are determined by their values on vectors from the Lie algebra. The most general left invariant r-form on $G$ is of the form 
$$
\alpha^{r} = \sum_ {I_ {<}}\alpha_ {I} \, \sigma^{I}, \quad  \sigma^{I} = \sigma^{I_ {1}}\wedge \sigma^{I_ {2}}\wedge \dots
$$
It is again determined by its value on a $r$-tuple of vectors from ${\frak g}$. The components $\alpha_ {I}$ are again constants.

It shouldn't come as a surprise that, 

**Theorem.** The Lie bracket $[X,Y]$ of two left invariant vector fields is again left invariant.

To prove it, notice that $X$ is left invariant iff $\left\langle X,\sigma \right\rangle=\text{const}$ for some left invariant 1-form $\sigma$. For such a $\sigma$, since $X,Y$ are left invariant we have $\left\langle X,\sigma \right\rangle=\text{const}$ and $\left\langle Y,\sigma \right\rangle=\text{const}$. So the question is, is $\left\langle [X,Y],\sigma \right\rangle=\text{const}$? Then since for general $\omega \in\Omega^{1}$ 
$$
d\omega(X,Y)=-\omega([X,Y])+X(\omega(Y))-Y(\omega(X))
$$we have
$$
\left\langle [X,Y],\sigma \right\rangle =\sigma([X,Y]) =- d\sigma(X,Y)
$$
where, if $\sigma$ is left invariant then so is $d\sigma$ since $L_ {g}^{\ast}d\sigma \Large\mid_ {g}  =dL_ {g^{\ast}}\sigma \Large\mid_ {g} =d \sigma \Large\mid_ {\mathbb{1}}$. Thus 
$$
\sigma([X,Y])=\text{const}.
$$
Q.E.D.

We may then write
$$
[X_ {i},X_ {j}]=if_ {ij}^{k}X_ {k},\quad f_ {ij}^{k}=-f_ {ji}^{k}.
$$
$f_ {ij}^{k}$ is called the `structure constants`.

The structure constant also can be applied to the left invariant 1-forms $\sigma$. 

**Theorem.** The `Maurer-Cartan` equations
$$
d\sigma^{i} = -\sum_ {j<k}if^{i}_ {jk}\,\sigma^{j}\wedge \sigma^{k}
=-\frac{1}{2}\sum_ {j,k}if^{i}_ {jk}\,\sigma^{j}\wedge \sigma^{k}
$$
hold, and $d^{2}\sigma^{i}=0$ yields the `Jacobi identity`
$$
f^{m}_ {na}f^{n}_ {bc}+f^{m}_ {nb}f^{n}_ {ca}+f^{m}_ {nc}f^{n}_ {ab}=0.
$$

This Jacobi identity for left invariant I -forms is also a consequence of a general Jacobi identity for vector fields on any manifold $M^{n}$, which reads
$$
[X,[Y,Z]]+[Y,[Z,X]]+[Z,[X,Y]]=0.
$$

We now make the vector space $T_ {\mathbb{1}}G={\frak g}$ into a `Lie algebra` by defining a product
$$
{\frak g}\times {\frak g}\to {\frak g}
$$
as follows.

Let $X,Y\in{\frak g}$, extend them to be vector fields $X',Y'$ on all of $G$. Define the product of $X$ and $Y$ to be the Lie bracket
$$
[X,Y]:= [X',Y']_ {\mathbb{1}}.
$$

Note that *the Lie algebra product is not associative*! Take $SO(3)$ for example, there exists three basis vectors $X,Y,Z$ satisfying $[X,Y]=Z$, $[Y,Z]=X$ and $[X,Z]=-Y$, then $[X,[X,Y]]=-Y\neq[[X,X],Y]=0$.

**We shall consistently identify the Lie algebra ${\frak g}$ with the $N(= \text{dim} G)$ dimensional vector space of left invariant fields on $G$.**

Classically the Lie algebra was known as the "infinitesimal group" of $G$, for classically a vector was thought of roughly as going from a point to an "infinitesimally nearby" point. Then the Lie algebra consisted of group elements infinitesimally near the identity! We shall **not** use this picture.

### The Exponential Map

**Theorem.** For *any* matrix $A$,
$$
\det \exp A = \exp \mathrm{Tr}\,A,\quad  \text{or equivalently, } \det e^{ A }=e^{ \mathrm{Tr}\,A }.
$$

**Theorem.** The map 
$$
\exp: {\frak g}\to G,\quad  A \mapsto e^{ A }
$$
is a diffeomorphism of some neighborhood of $0\in{\frak g}$ onto a neighborhood of $\mathbb{1}\in G$.

In a general Lie group, the 1-parameter subgroup $\text{exp}(t X)$ is the integral curve of a vector field on $G$, and thus it would seem that this need only be defined for $t$ small. In this case of a left invariant vector field on a group, it can be shown that the curve exists for all $t$, just as it does in the matrix case.

### Examples of Lie Algebras

Consider our old friend, the matrix group $GL(n)$. Let $M(n\times n)$ be the vector space of *all* *real* $n\times n$ matrices, the dimension is clearly $n^{2}$. For $A\in M(n\times n)$, we have 
$$
\det e^{ A }=e^{ \mathrm{Tr}\,A }\geq 0.
$$
Therefore the matrix $e^{ A }$ is invertible, the exponential map maps any $n\times n$ matrix to an invertible matrix,
$$
\exp: M(n\times n)\to GL(n).
$$
We usually use the same name of the group but all in lowercase Gothic font to denote the corresponding Lie algebra, for example the Lie algebra of $GL(n)$ group is denoted ${\frak gl}(n)$. Then 
$$
{\frak gl}(n)= M(n\times n).
$$
If $G$ is a matrix group, that is, a *subgroup* of $GL(n)$, including $SO(N)$, $SU(N)$, etc., then its Lie algebra ${\frak g}$ is the largest subspace of $M(n\times n)$ such that $\exp {\frak g}\to G$. 

For special orthogonal matrices $SO(n)$, we simply state that its Lie algebra ${\frak so}(n)$ consists of anti-symmetric matrices. 

The group of unitary matrices $U(n)$, on the other hand, has Lie algebra ${\frak u}(n)$ consists of anti-hermitian matrices, $A^{\dagger}=-A$. As a special case, the special unitary groups $SU(n)$ has Lie algebra ${\frak su}(n)$ made of anti-hermitian matrices with zero trace, since $\exp \mathrm{Tr}\,=\det$.

### Do the 1-Parameter Subgroups Cover $G$?

The question is, can every $g\in G$ be generated by an $A\in {\frak g}$? In other words, 
$$
\text{is the map } \exp: {\frak g}\to G \text{ onto?}
$$
It can be shown that, $\exp$ is indeed onto if the group as a manifold is *connected* and *compact*. It is clear that a 1-parameter subgroup must lie in the connected piece of $G$ that contains the identity. The matrix group $SL(2,\mathbb{R})$ is not compact since the only constrain for an element 
$$
g=\begin{bmatrix}
x & y \\
z & w
\end{bmatrix}
$$
is that 
$$
\det g = xw-yz=1
$$
still $x$ can be arbitrary large even with this condition.

However, it can be shown that $SL(2,\mathbb{R})$ is *connected*. To see it, it is helpful to adopt a geometric viewpoint. $SL(2,\mathbb{R})$ can be pictured as a pair of column vectors $(x z)^{T}$ and $(y w)^{T}$ in $\mathbb{R}^{2}$ spanning a parallelogram of area $1$. Deform he lengths of both so that the first becomes a unit vector, keeping the area $1$. This deforms $SL(2,\mathbb{R})$ into itself. Next, "Gram-Schmidt" the second so that the columns are orthonormal. This can be done continuously. The resulting matrix is then in the subgroup $SO(2,\mathbb{R})$ That is, it represents a rotation of the plane. The $SO(2)$ group is nothing but the rotation in two-plane, parametrized by a single angle $\theta$, topologically a circle, which is connected. 

In fact, Let $V^{r}$ be s submanifold of $M^{d}$, furthermore suppose $V$ is a `deformation retract` of $M$. A deformation retract means that there exists a 1-parameter, continuous map $r_ {t}: M\to M$ such that 
1. $r_ {0}$ is the identity map on $M$,
2. $r_ {1}$ maps all of $M$ to $V$,
3. $r_ {t}$ for all $t$ is the identity map on $V$.

Then, consider homology group of any coefficient group. The deformation retract will change continuous by definition, meaning during the deformation from $r_ {t}$ to $r_ {t+\Delta t}$ it sweeps over a area on $M$ whose boundary is $r_ {t+\Delta t}-r_ {t}$. Then the deformation process will not change the homology group, thus

**Theorem.** If $V \subset M$ is a *deformation retract*, then $V$ and $M$ have isomorphic homology groups, regardless of the coefficient group $G$,
$$
H_ {p}(M;G)\cong H_ {p}(V; G).
$$

As an application of the above theorem, consider $SO(2)$ and $GL(2)$. Since $SO(2)$ is topologically a circle, we have 
$$
H_ {1}(SL(2,\mathbb{R})) \cong H_ {1}(\mathbb{S}^{1}) \cong \mathbb{Z}.
$$

Since we are talking about $2\times 2$ matrices, there exists an interesting result for $A\in 2\times 2$ matrices called the `Cayley-Hamilton` theorem, stating that 
$$
A^{2}-(\mathrm{Tr}\,A)A+\det A \,\mathbb{1}=0.
$$

### Subgroups and Subalgebras

Since the group $G$ is generated by its Lie algebra ${\frak g}$, at least for the connected component, there should be a way to find the subgroup of $G$ by looking at ${\frak g}$. 

We will not distinguish between Lie algebra elements, namely the vectors at the identity of the group $X_ {\mathbb{1}}$, and the left-invariant vector field $X_ {g}$, since they are isomorphic to each other. 

The exp map $\exp X$ gives the integral curve of $X$. Since $X$ is left invariant, the integral curve starting at $g$ is connected to the integral curve starting at $\mathbb{1}$, to be specific $g(t) = L_ {g}g(0)$. To be specif, notice with an infinitesimal parameter $dt$, the tangent vector $X$ will "move" the point $\mathbb{1}$ to $\mathbb{1}+dt X = \mathbb{1}(1+dt X)$, since $X$ is left-invariantly translated to $g$, the vector $X_ {g}$ will move the point $g$ to $g(1+dX)$. On the other hand, the $X$ vector field, like any vector field, generates a flow $\phi_ {t}(g)$ where $g$ is the starting point. 

Convince yourself that the flow generated by the left invariant field $X$ is the 1-parameter group of right translations
$$
\phi_ {t}(g) = g \exp(tX).
$$

#### Commutator of matrices

Recall that the Lie algebra ${\frak g}$ as a vector space, is simply the tangent space to $G$ at $\mathbb{1}$, but as an algebra it is identified with the left invariant vector fields on $G$. (Of course this is merely a convention; we could have used right invariant fields just as well.) If $X,Y\in{\frak g}$, then their Lie bracket is given by the Lie derivative since 
$$
[X,Y]=\mathcal{L}_ {X}Y.
$$
If $G$ is a matrix group, then the elements of ${\frak g}$ are matrices as well, not in $G$ but the derivative of $G$ at origin, and $[X,Y]$ is merely the commutator of two matrices.

#### Subgroup and subalgebra

The subset $H\subset G$ qualifies as a sub Lie group if H, if not embedded, is at least an `immersed`(locally embedded) submanifold of $G$. Furthermore, if the Lie algebra ${\frak h}$ is closed under Lie brackets, then ${\frak h}$ define a Lie algebra, called the `subalgebra` of ${\frak g}$.

In general, if $H$ is a subgroup of $G$, then the Lie algebra ${\frak h}$ of $H$ is a subalgebra of ${\frak g}$. The converse of this is also true and of immense importance.