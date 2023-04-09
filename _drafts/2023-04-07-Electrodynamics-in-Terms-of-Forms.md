---
layout:     post   				    # 使用的布局（不需要改）
title:    Electrodynamics in Terms of Differential Forms			# 标题 
subtitle:   A thorough introduction
date:       2023-04-07 				# 时间
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

Next we introduce so-called pseudoforms. Consider ordinary $\mathbb{R}^{3}$ with its euclidean metric. We would like to define the "volume 3-form" Vol$^{3}$ to be the form that assigns to any triple of vectors the volume of the parallelopiped spanned by the vectors; in particular $\text{Vol}(X, Y, Z)$ should be $1$ if $X, Y$, and $Z$ are orthonormal. But if $\text{vol}$ is to be a form we must then have $\text{vol}(Y, X, Z) = -1$, and yet $Y, X$, and $Z$ are orthonormal. 