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

### A little more about differential forms

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
For this reason the wedge product is very convenient for discussing linear dependence.

**Theorem.** 