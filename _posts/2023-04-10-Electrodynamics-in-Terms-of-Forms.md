---
layout:     post   				    # 使用的布局（不需要改）
title:    Electrodynamics in Terms of Differential Forms			# 标题 
subtitle:   A thorough introduction
date:       2023-04-10 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background13.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

### Some Conventions

We will use capital Latin letters such as $I,J,$ etc. to denote sets of indices, for example $a_ {I}$ is the shorthand notation for $a_ {i_ {1}\dots i_ {p}}$. To get rid of annoying factorial factors that frequently appear in differential form calculation, we require the indices to be arranged in increasing order, the indices are denoted $I_ {<}$, 
$$
I_ {<} = \left\{ i_ {1}<i_ {2}<\dots<i_ {p} \right\} .
$$
We also adopt the so-called generalized Kronecker delta symbol,
$$
\delta^{I}_ {J}:= \begin{cases}
1  &  J \text{ is an even permutation of }I \\
-1  &  J \text{ is an odd permutation of }I \\
0 & \text{ otherwise}
\end{cases}
$$
for example, we have 
$$
\delta^{123}_ {132}=-1,\quad  \delta^{123}_ {231}=1, \quad  \delta^{123}_ {124}=0.
$$

We can then define the usual permutation symbol as 
$$
\epsilon_ {I} = \epsilon_ {i_ {1}\dots i_ {n}} =\epsilon^{I}= \delta^{I}_ {12\dots n}.
$$

In the above-mentioned notations, the wedge product of two differential forms $\alpha,\beta$ can be written as (in components)
$$
(\alpha \wedge \beta)_ {I} = \delta_ {I}^{MN} \alpha_ {M_ {<}} \beta_ {N_ {<}}.
$$
where repeated indices are supposed to be summed over, as usual. In functional form
$$
(\alpha \wedge \beta)(V_ {I}) = \delta^{MN}_ {I} \alpha(V_ {M_ {<}})\beta(V_ {N_ {<}}).
$$
As an example of the last definition, take $\alpha,\beta$ to be two 1-forms acting on vectors $V_ {1},V_ {2}$, then by the definition
$$
(\alpha \wedge  \beta)(V_ {1}V_ {2}) = \delta^{MN}_ {12} \alpha(V_ {M_ {<}}) \beta(V_ {N_ {<}})
= \alpha(V_ {1}) \beta(V_ {2}) - \alpha(V_ {1})\beta(V_ {2}),
$$
which reproduced our familiar definition for the wedge product. 

As another example, let $\alpha$ be a 2-form and $\beta$ be a 1-form, then
$$
(\alpha \wedge \beta)_ {523} = \delta_ {523}^{IJ}\; \alpha_ {I_ {<}}\beta_ {J_ {<}} = \delta^{253}_ {523}\alpha_ {25}\beta_ {3}+ \delta^{352}_ {523}\alpha_ {35}\beta_ {2} +\delta^{235}_ {523}\alpha_ {23}\beta_ {5}
$$
which is 
$$
-\alpha_ {25}\beta_ {3} +\alpha_ {35}\beta_ {2} + \alpha_ {23}\beta_ {5}.
$$
The notations we adopt here greatly simplifies the calculation.

The wedge product of three differential forms are also beautifully expressible in our notation,
$$
(\alpha \wedge \beta \wedge \gamma)_ {I} = \delta^{ABC}_ {I} \alpha_ {A} \beta_ {B} \gamma_ {C},\quad A,B,C \text{ in increasing order}.
$$

- - -

The contraction of indices also works in a simple way,

**Lemma.** 
$$
\sum_ {J_ {<}}\delta^{IJ}_ {M}\delta^{KL}_ {J} = \delta^{IKL}_ {J}.
$$

### A little bit more about differential forms

Although forms can be expanded in any basis, the geometric meaning of differential forms is most obvious in terms of Cartesian coordinates. By Cartesian coordinates we just mean that the metric is that of the Euclidean space $\mathbb{R}^{n}$. In this case, the basis for the tangent vector space is $\partial_ {i}$ and the dual basis are given by $dx^{i}$. We already know that $dx^{i}$ reads off the i-th component of a vector $\mathbf{v}$, 
$$
\left\langle dx^{i},\mathbf{v} \right\rangle = v^{i}.
$$
Note that there will be problem if you think of $dx^{i}$ as an infinitesimal quantity, as is the case in the classical real analysis! Because then on the left hand side we have the inner product between an infinitesimal thing and one regular-sized thing, the final product should be infinitesimal of order one, but on the right hand side we clearly have a regular-sized thing, the i-th component of a finite-sized vector. In fact, $dx^{i}$ is a special case of $d\mathbf{v}$ for arbitrary vector $\mathbf{v}$, and $d\mathbf{v}$ should be regarded as a **vector-valued 1-form**! That is, something that takes an vector and spits out an vector. For more details, please refer to the other notes in this blog.

Let's start with the 2-dimensional Euclidean space. Given two vectors $\mathbf{v,w}$ we have 
$$
dx^{i}\wedge dx^{j}(\mathbf{v,w}) = \begin{vmatrix}
v^{i} & w^{j} \\
v^{j} & w^{i}
\end{vmatrix} = \pm \text{ area projected on the } x^{i}x^{j} \text{ plane.}
$$

- - -

We will show that exterior products yield a coordinate-free expression for the determinant! Consider an n-tuple of 1-forms $\tau^{1},\dots,\tau^{n}$, given in terms of basis 
$$
\tau^{i} = T^{i}_ {j} \sigma^{j}
$$
where $\sigma^{i}$ are the basis. Then
$$
\begin{align}
\tau^{1}\wedge \dots \wedge \tau^{n} &= T^{1}_ {i_ {1}}\sigma^{i_ {1}}\wedge \dots \wedge T^{n}_ {i_ {n} } \sigma^{i_ {n}} \\
&= T^{1}_ {i_ {1}}\dots T^{n}_ {i_ {n}} \sigma^{i_ {1}}\wedge \dots \wedge \sigma^{i_ {n}} \\
&= T^{1}_ {i_ {1}}\dots T^{n}_ {i_ {n}} \sigma^{1}\wedge \dots \wedge \sigma^{n} \epsilon^{i_ {1}\dots i_ {n}} \\
&= (\det T)  \;\sigma^{1}\wedge \dots \wedge \sigma^{n}
\end{align}
$$
For this reason the wedge product is very convenient for discussing linear dependence. For example, using form it is quite easy to tell if a set of forms are linearly independent, see the theorem below.

**Theorem.** The set of 1-forms $\tau^{i}$ are **linearly dependent** iff
$$
\tau^{1} \wedge  \tau^{2} \wedge \dots \wedge \tau^{n} = 0
$$

- - -

Many formulas given in the form of vectors are more natural in terms of differential forms, here we shall briefly discuss the computations of differential forms and its relation with vector analysis.

Consider $\mathbb{R}^{3}$ as a 3-manifold with any (perhaps curvilinear) coordinate system $x^{1,2,3}$. Let $f$ be a 0-form, that is a function on $\mathbb{R}^{3}$. The 1-forms are written as 
$$
\alpha = \alpha_ {1}dx^{1} + a_ {2} dx^{2} +a_ {3}dx^{3}
$$
and 2-forms are written as 
$$
\begin{align}
\gamma &= \gamma_ {12} dx^{1}\wedge dx^{2} + \gamma_ {23}\, dx^{2}\wedge dx^{3} + \gamma_ {13} dx^{1}\wedge dx^{3}  \\
&:=\gamma_ {3} dx^{2}\wedge dx^{1} + \gamma_ {1}\, dx^{2}\wedge dx^{3} + \gamma_ {2} dx^{3}\wedge dx^{1}
\end{align}
$$
where we used the convention that the indices are always arrange in increasing order in the first line, and indices are cyclic in the second line. 

The 3-forms are the simplest for they only have one component,
$$
\omega = \omega(x^{1},x^{2},x^{3})dx^{1}\wedge dx^{2}\wedge dx^{3}.
$$

There are familiar expressions used in vector analysis in the case when the coordinates are Cartesian, involving line, surface, and volume integrals. Let's look at some examples.

Given 1-forms $\alpha,\beta$, let $\mathbf{a,b}$ be the corresponding vectors defined components-wise, namely 
$$
\mathbf{a} = a^{i} \partial _ {i},\quad  a^{i} \equiv \alpha_ {i}, \text{the same for }b \text{ and }\beta
$$
then we have 
$$
\alpha \wedge \beta = \mathbf{a}\times \mathbf{b} \,dS^{i} \text{ component-wise}
$$
where $ds^{1} \equiv dx^{2}\wedge dx^{3}$ and etc. Note that this correspondence in general does not hold in curvilinear coordinates.

- - -

There has already been a lot of discussions about the theoretical importance and philosophy of the exterior differential, I will not dive in them here, interested readers can refer to various textbooks and lecture notes. Here instead I'll just focus on the calculation methods, starting with some examples in $\mathbb{R}^{3}$.

Given a function $f(x)$ which is by definition also a 0-form. The differential of $f$ is 
$$
df = \partial_ {x}f dx + \partial _ {y}f dy + \partial _ {z}f dz
$$
If the coordinates are Cartesian, then the components are the components of the gradient of $f$,
$$
\nabla_ {i} f = \partial _ {i}f,\quad  df = \nabla f \cdot d\mathbf{x}
$$
where $d\mathbf{x} = (dx^{1},dx^{2},dx^{3})$. 

That is for 0-form. Given a 1-form $\alpha$ and the corresponding vector $a$ whose components are given by that by $\alpha$, we have 
$$
d \alpha = (\text{curl }a) \cdot d\mathbf{x} \text{ component wise.}
$$

Finally, for a 2-form $\beta$ and corresponding vector $b$, namely $b_ {i} =\epsilon_ {ijk}\beta_ {jk}$, we have 
$$
d\beta = (\partial _ {1}b_ {1}+\partial _ {2}b_ {2}+\partial _ {3}b_ {3})dx\wedge dy\wedge dz,
$$
in Cartesian coordinates $d\beta$ is the divergence of the vector $b$.

$d^{2}=0$ in any coordinate system; in Cartesian coordinates this yields the famous $\text{curl }\text{grad }=0$ and $\text{grad }\text{curl }=0$.

It is important to realize that it is no more difficult to compute d in a curvilinear coordinate system than in a Cartesian one. For example, in spherical coordinates, for 1-form 
$$
\alpha =\alpha_ {r} dr +  \alpha_ {\theta}d\theta+ \alpha_ {\phi}d\phi
$$
and the orientation is given by $dr\wedge d\theta \wedge d\phi$, then $d\alpha$ is simply
$$
d\alpha = d\alpha_ {r}\wedge  dr + d \alpha_ {\theta}\wedge  d\theta + d\alpha_ {\phi} \wedge  d\phi
$$
where
$$
d\alpha_ {r}\wedge  dr = (\partial _ {\theta}\alpha_ {r}) d\theta \wedge dr + (\partial _ {\phi}\alpha _ {r}) d \phi \wedge  dr, \text{ etc. }
$$

In general, in situations where the "curl " of a "vector" is required, the "vector" will most naturally appear in covariant form, i.e., it will be a 1-form. 

Next we give the coordinate expression for $d$. Let $\alpha \in \Omega^{p}(\mathbb{R}^{n})$ and explicitly
$$
\alpha = \alpha_ {I_ {<}} dx^{I}.
$$
Then 
$$
d\alpha = (d \alpha_ {I_ {<}}) \wedge dx^{I} = (\partial _ {j}\alpha_ {I_ {<}}) dx^{j} \wedge  dx^{I}.
$$
In component form we have 
$$
(d\alpha)_ {I} = \delta_ {I}^{jK_ {<}} \;\partial _ {j}\alpha_ {K}.
$$
### Orientation and Pseudo-forms

Let $\mathbf{e}=(\mathbf{e_ {1},\dots,e_ {n}})$ and $\mathbf{f} = (\mathbf{f_ {1},\dots,f_ {n}})$ be two sets of basis, with transition matrix $P:\mathbf{e}\mapsto \mathbf{f}$ acting from the right, according to our convention, namely $\mathbf{f}=\mathbf{e}P$. They are said to be of the same `orientation` iff $\det P>0$. Thus orientation can be seen as equivalences classes of basis, with only two elements. **We orient a vector space by declaring one of the two classes of bases to be positive**. In our 3-space it is usual to declare the right-handed bases to be positively oriented, but we could just as well have the left-handed bases as positive. 

Now consider a manifold $M$, at each point $p$ there is a tangent vector space $T_ {p}M$ on which we need to define an orientation. We shall define the orientation in a continuous manner. Given a parametrization $\mathbb{R}^{n}\to M$ of $M$ in terms of $x$, we have a set of natural basis given by $\left\{ \partial_ {1},\dots,\partial_ {n} \right\}$ and we can simply define the orientation by saying that the order $\partial_ {1},\partial_ {2},\dots,\partial_ {n}$ is positive. Then any even permutation of it is still even, and odd permutation would be odd, simple as that.

We shall say that a manifold $M$ is orientable if we can cover $M$ by coordinate patches having positive Jacobians in each overlap. We can then declare the given coordinate bases to be positively oriented, and we then say that we have oriented the manifold. Briefly speaking, if a manifold is orientable it is then possible to pick out, in a continuous fashion, an orientation for each tangent space $T_ {x}M$ of $M$. Conversely, if it is possible to pick out continuously an orientation in each tangent space, we can assume that the coordinate frames in each coordinate patch have the chosen orientation and Mil must be orientable. **An interesting fact is that complex manifolds are always orientable.** 

Next we introduce so-called pseudoforms. Consider ordinary $\mathbb{R}^{3}$ with its euclidean metric. We would like to define the "volume 3-form" Vol$^{3}$ to be the form that assigns to any triple of vectors the volume of the parallelopiped spanned by the vectors; in particular $\text{Vol}(X, Y, Z)$ should be $1$ if $X, Y$, and $Z$ are orthonormal. But if $\text{vol}$ is to be a form we must then have $\text{vol}(Y, X, Z) = -1$, and yet $Y, X$, and $Z$ are orthonormal. We have asked too much of vol. In some books they get around this by taking absolute value $\left\lvert \text{Vol} \right\rvert$, but it this does great harm to the machinery of forms that we have labored to develop. What we could do is require that $\text{Vol}(X, Y, Z) = 1$ if the triple is an orthonormal right-handed system. This makes the volume form orientation-dependent. There is a serious drawback to this definition; what if we are dealing with a space that is not orientable? The physical space in which we live is, according to general relativity, curved and perhaps not orientable. 

We compromise by defining a new type of form (called "`form of odd kind`" by its inventor Georges de Rham) differing from our usual forms (of "`even kind`") in a way that will not seriously harm our machinery.

First note that the assignment of an orientation to a vector space $E$ is the same as the assignment of a function $o$ on bases of $E$ whose values are the two integers $\pm {1}$. If $(x)$ is a coordinate system, we should write $o(x)$ rather than $o(\partial_ {x})$. 

**Definition.** A `pseudo-p-form` $\alpha$ on a vector space $E$ assigns,for each orientation $o(E)$, an exterior p-form $\alpha_ {o}$ such that if the orientation is reversed the exterior form is replaced by its negative,
$$
\alpha_ {-o} = - \alpha_ {0}.
$$
An example is the volume form of $\mathbb{R}^{3}$. Let $(x,y,z)$ be the Cartesian coordinate system in $\mathbb{R}^{3}$, we don't endow it with an orientation yet, then 
$$
\text{Vol} := o(x,y,z) dx\wedge dy\wedge dz.
$$
Note that the order in the orientation $o(x,y,z)$ is matched with the order in the differential form $dx,dy,dz$. If we adopt the familiar right-handed orientation then $\text{Vol}$ is $dx\wedge dy \wedge dz$, but if we adopt the left-handed orientation then $\text{Vol}$ would be $-dx \wedge dy \wedge dz$. 

So roughly speaking 
$$
\text{pseudo-forms} = \text{orientation}\times \text{forms}.
$$

Similarly we can define pseudovectors, pseudoscalars, and so on, pseudo always referring to a change of sign with a change of orientation.

The volume form in a Riemannian manifold is very similar to that in $\mathbb{R}^{3}$. The `volume (pseudo)-n-form` $\text{Vol}^{n}$ is by definition the unique n-form that 1) assigns to an orientation $o$ of the tangent space $M$ and 2) a positively oriented orthonormal basis $\mathbf{e}$ the value $+1$.  Based on that, given an arbitrary coordinate system denoted by $(y)$, after some calculation we find that 
$$
\boxed{
\text{Vol}^{n} = o(y) \sqrt{ \left\lvert g \right\rvert  }\; dy^{1} \wedge  \dots dy^{n}.
}
$$

It is traditional to omit the orientation function $o(y)$, and we shall do so when no confusion can arise.

### Interior Products and Vector Analysis

We know that the contraction between a contravariant index and a covariant index gives us a scalar, the two indices cancel each other. The interior product between a form and a vector is the application of that idea. 

Let $v$ be a vector and $\alpha$ a p-form. Their `interior product` is a $(p-1)$-form $i_ {v}\alpha$ defined by 
$$
i_ {v}\alpha = 0 \text{ if } \alpha \text{ is a 0-form},
$$
$$
i_ {v}\alpha = \alpha(v) \text{ if }\alpha \text{ is a }1\text{-form},
$$
and 
$$
i_ {v}\alpha(w_ {2},\dots,w_ {p}) := \alpha(v,w_ {1},\dots,w_ {p}).
$$

Sometimes we shall write $i(v)$. 

**Theorem.** The interior product $i_ {v}: \Omega^{p} \to \Omega^{p-1}$ is an `antiderivation`, that is, for two forms $\alpha \in \Omega^{p}$ and $\beta \in \Omega^{q}$
$$
i_ {v}(\alpha \wedge  \beta) = (i_ {v}\alpha)\wedge \beta + (-1)^{p} \alpha \wedge i_ {v}\beta.
$$

Pushing $i_ {v}$ through $\alpha$ gives us an extra factor $(-1)^{p}$, just like the exterior differentiation.

In components, we have 
$$
i_ {v}\alpha = \sum_ {I_ {<}}v^{j}\alpha_ {jI}\; dx^{I}.
$$

- - -

Given a specific coordinate system, we can associate a 1-form to a vector by identifying the components. Of course this wouldn't work under a change of coordinates, since a covariant vector (1-form) and a contravariant vector (regular vectors) have different transformation rules, but we can forget about the transformation rule for now. Writing the contraction as left-right angle brackets, i.e. for a vector $v$ and a 1-form $\alpha$
$$
v(\alpha) = \alpha(v) =: \left\langle \alpha,v \right\rangle 
$$
where we adopted the convention that in $\left\langle -,- \right\rangle$ the vector appears on the right. The above mentioned associating to a vector a 1-form is just dualization, namely, given the 1-form $\nu$, which acts on any vector as $\left\langle \nu,- \right\rangle$, the associated vector is the unique vector $v$ that acts on any 1-forms as $\left\langle -,v \right\rangle$. We will write 
$$
\nu = \left\langle -,v \right\rangle .
$$
For example, 
$$
\left\langle \nu, X \right\rangle  \equiv \left\langle X,v \right\rangle,
$$
where $\left\langle -,- \right\rangle$ is the inner product between two vectors on the right hand side. We use the same notation for all kind of "inner products", may that be inner products between vectors, or between a vector and a 1-form.

In 3D Euclidean space, a vector can also be associated to a 2-form given by $v_ {1}dx^{2}\wedge dx^{3}+\dots$, so how does this work in a general coordinate system? For example, given a curved 3D Riemannian manifold, is there a universal way to associate a vector to a 2-form? To to that, we need the interior product we just introduced. 

We claim that 
$$
\mathbf{v} \longleftrightarrow \tilde{\nu} := i_ {\mathbf{v}}\text{Vol}^{3}.
$$
In curvilinear coordinates $(u)$, omitting the orientation $o(u)$, we have 
$$
i_ {v}\sqrt{ \left\lvert g \right\rvert  }\; du^{1}\wedge du^{2}\wedge du^{3}=\sqrt{ \left\lvert g \right\rvert  }(v^{1} du^{2}\wedge du^{3}+u^{2}du^{3}\wedge du^{1}+v^{3} du^{2}\wedge du^{1}).
$$

Conversely, if $\beta$ is a 2-form, we can associate to it a vector $b$ with components 
$$
\mathbf{b} := \frac{1}{\sqrt{ \left\lvert g \right\rvert  }}(b_ {23},b_ {31},b_ {12}) .
$$
The same procedure will work with in any manifold $M^{n}$ having some distinguished volume form (not necessarily coming from a Riemannian metric). To the vector $v$ we may associate the (pseudo-)$(n-1)$-form $i_ {v}\text{Vol}^{n}$. It is pseudo since the volume is pseudo and $v$ is not.

Let $v,w$ be two vectors and $\nu,\omega$ be the corresponding 1-forms. What about the cross product of the vectors? We know that $v\times w$ is antisymmetric and so is $\nu \wedge\omega$ , thus we would guess that $\nu \wedge\omega$ is the 2-form associated to the so-called vector $v\times w$. It turns out to be correct. Recall that the 2-form associated to vector $v\times w$ is $i_ {v\times w}\text{Vol}^{3}$ , we have 
$$
\nu \wedge \omega=i_ {v\times w}\text{Vol}^{3}.
$$

Although not usually mentioned in elementary books, the vector product is defined in $\mathbb{R}^{3}$ as follows: $v\times w$ is the unique pseudovector such that
$$
\text{Vol}(v,w,c) = \left\langle v\times w, c \right\rangle \text{ for each vector }c.
$$

- - -

Vector algebra in $\mathbb{R}^{3}$ is easily handled by use of interior and exterior products; the only question is, should one associate to a vector $\mathbf{B}$ its 1-form $\beta : =  \left\langle -,\mathbf{B} \right\rangle$ or its 2-form $\beta^{(2)} = i_ {\mathbf{B}} \text{vol}^{3}$?

We already know that $df$ is associated to $\nabla f$. 

We **define** the `curl` of $A$ by using $\mathbf{A}\leftrightarrow \alpha \in\Omega^{1}$ and then 
$$
\text{curl } \mathbf{A} = d\alpha,\quad  d\alpha = i_ {\text{curl A}}\text{Vol}^{3}.
$$
We **define** $\text{div }\mathbf{B}$ by using $\mathbf{B} \leftrightarrow \beta^{(2)}$ and 
$$
d \beta^{(2)} := \text{div }\mathbf{B} \;\text{Vol}^{3}.
$$

Given in coordinates, we have 
$$
\text{div }\mathbf{B} = \frac{1}{\sqrt{ \left\lvert g \right\rvert  }} \frac{ \partial  }{ \partial u^{i} } \left( \sqrt{ \left\lvert g \right\rvert  }b^{i} \right).
$$

We define the `Laplacian` of a function f by
$$
\nabla^{2}f = \Delta f := \text{div }\text{grad }f= \frac{1}{\sqrt{ \left\lvert g \right\rvert  }} \frac{ \partial  }{ \partial u^{i} } \left( \sqrt{ \left\lvert g \right\rvert  } \partial ^{i}f \right),\quad  \partial ^{i} = g^{ij} \partial _ {j}.
$$
To continue with vector identities it is useful to associate a pseudo-3-form to each scalar $f$, namely
$$
f \longleftrightarrow f(x)\,\text{Vol}^{n}.
$$
Then we can use forms to calculate $\text{div }\mathbf{A}\times \mathbf{B}$. Recall that in $\mathbb{R}^{3}$ we have $(i_ {A}\text{Vol}^{3})\wedge \beta = \left\langle \mathbf{A,B} \right\rangle\text{Vol}^{3}$, we have 
$$
\begin{align}
\text{div }(\mathbf{A\times B })  \longleftrightarrow & d(\alpha \wedge \beta) = (d\alpha)\wedge \beta-\alpha \wedge  d\beta \\
&= i_ {\text{curl} A}\text{Vol} \wedge  \beta - \alpha \wedge  i_ {\text{curl B}}\text{Vol} \\
&= \left\langle \text{curl }\mathbf{A},\mathbf{B} \right\rangle \text{Vol} - \left\langle \mathbf{A},\text{curl }\mathbf{B} \right\rangle\text{Vol}  \\
&\longleftrightarrow \left\langle \text{curl }\mathbf{A},\mathbf{B} \right\rangle - \left\langle \mathbf{A},\text{curl }\mathbf{B} \right\rangle.
\end{align}
$$
### Dictionary




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

### Hodge Operator

On a (pseudo-)Riemannian manifold $M$ we will first introduce a pointwise scalar product between $p$-forms, denoted by pointy brackets, then use it to define a `global` scalar product, denoted with parenthesis. 

The local scalar product of two $p$-forms is defined to be 
$$
\left\langle \alpha,\beta \right\rangle := \alpha_ {I_ {<}} \beta^{I}
$$
where $I={i_ {1},\dots,i_ {p}}$ is the generalized index and $I_ {<}$ denotes that in the implies sum we have $i_ {1}<i_ {2}<\dots<i_ {p}$. We can denote the orthonormal basis of 1-forms by 
$$
\sigma^{1}, \dots,\sigma^{p}.
$$

The `global` or `Hilbert space scalar product` is defined by 
$$
\left( \alpha,\beta \right) := \int _ {m} \, \left\langle \alpha,\beta \right\rangle \text{Vol} ^{n}.
$$
whenever this makes sense. This will be the case when $M$ is compact, or, more generally, when $M$ has compact support.

note that the space of smooth $p$-forms on a Riemannian $M$ that satisfy $\left( \alpha,\alpha \right)<\infty$ form only a `pre-Hilbert space` since it is not **complete**; a limit of square integrable smooth forms need not even be continuous. To get a Hilbert space we must "complete" this space. We shall not be concerned here with such matters, and we shall continue to use the inaccurate description "Hilbert space." We shall even go a step further and use this denomination even in the pseudo-Riemannian case, where $\left( -,- \right)$ is not even positive definite.

If $\alpha \in\Omega^{1}(M)$, we may look at its contravariant version $A$ and define a $(n-1)$-form $i_ {A}\text{Vol}^{n}$. We are now going to generalize this procedure, associate to each $p$-form a $(n-p)$-form $\star \alpha$, the `Hodge-dual` of $\alpha$, as follows. If 
$$
\alpha = \alpha_ {I_ {<}} dx^{I}
$$
then
$$
\star \alpha = (\star\alpha) _ {J_ {<}} dx^{J}, \quad  (\star\alpha)_ {J} = \sqrt{ \left\lvert g \right\rvert  } \alpha^{K} \epsilon_ {K_ {<}J_ {<}.}
$$
This definition is quite a mouthful, whoever sees it for the first time needs to take some time to digest it.

Technically speaking the smooth p-forms with finite inner product does not form a Hilbert space, but just a pre-Hilbert space, since a Hilbert space must be a Banach space, which is a `complete` vector space with norm defined, but a limit of square integrable smooth forms need not even be continuous, so definitely not complete.

For an important special case, the 0-form that is the constant function $f=1$ has
$$
\star 1 = \sqrt{ \left\lvert g \right\rvert  } \epsilon_ {12..d} dx^{1}\wedge dx^{2}\dots \wedge dx^{d} = \text{Vol}^{d}.
$$

