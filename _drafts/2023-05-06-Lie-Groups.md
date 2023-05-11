---
layout:     post   				    # 使用的布局（不需要改）
title:     Lie Groups, Invariant Vector Fields, and Forms		# 标题 
subtitle:   
date:       2023-05-06 				# 时间
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

For example, $\mathbb{R}$ is a Lie group under addition. This group is commutative, or `abelian`. The positive real numbers $\mathbb{R}^{+}$ also form a abelian group under multiplication. The real and complex general linear matrices $GL(n,\mathbb{R})$ and $GL(n,\mathbb{C})$ are also Lie groups under the usual matric multiplication. The `special linear` group, $SL(n,\mathbb{R})$ is the subset of $GL(n,\mathbb{R})$ that have determinant one. For any matrix group, the adjective **special** means that the determinant is equal to one. Other examples include $\mathbb{T}^{n}$ the $n$-torus group, which is the abelian group of diagonal matrices of the form 
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

Note that in any Lie group, if $X_ {i}$ is a basis for the left invariant vector fields and if $\sigma^{i}$ is the dual basis of 1-forms, then this dual basis is automatically left invariant. This can be shown using the relation $f^{\ast}\alpha(X)=\alpha(f_ {\ast}X)$. Also, note that if $\alpha$ and $\beta$ are invariant differential forms on $G$ then so are $d\alpha$ and $\alpha \wedge\beta$.

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
g'(t) = g(t)g'(0),\quad  g'(0)=\text{const matrix.} 
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


