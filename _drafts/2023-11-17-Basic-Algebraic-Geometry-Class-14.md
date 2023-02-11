---
layout:     post   				                    # 使用的布局（不需要改）
title:      Basic Algebraic Geometry Class 14		# 标题 
subtitle:   The Tangent Space
date:       2023-2-11 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt8.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Math
    - Commutative Algebra
    - Notes
---

### Smoothness

Intuitively speaking, a curve is smooth at a point if the tangent line there is well defined (linearization). Sometimes when people speak of smoothness they mean the infinite derivatives are all smooth, but here we only talk about one order of derivative. For example, if a line intersects with itself, then it is not clear how the tangent line there is defined. 

Similarly, a variety is smooth at a point if it has a tangent space of the same dimension there. A `tangent space` of a variety $X$ at point $a$ is the zero set of linear equations whose coefficients are the values of $\partial f / \partial T_ {i}$ at $a$, for $f \in I(X)$. The derivative is defined formally here, since when we are talking about derivatives of formal polynomials we can not really adopt the limit process. The `formal derivative` $\frac{ \partial f }{ \partial T_ {i} }$ is defined by extending 
$$
\frac{ \partial T_ {i}^{d} }{ \partial T_ {i} }  = d T_ {i}^{d-1}.
$$

Then you can define the tangent space of affine variety. The affine variety is embedded in a specific way in some affine space $X\subset\mathbb{A}^{n}$, and the `tangent space` $T_ {a}X$ of $X$ at $a$ is the set of all pints $(x_{1},\dots,x_{n})$ in the ambient space with
$$
\sum_ {i=1}^{n} \frac{ \partial f }{ \partial T_ {i} } (a) \times (x_ {i}-a_ {i})=0 \text{ for all } f\in I(X),
$$
this is analogous to how we define tangent plane in analytical geometry. 

Notice that $T_ {a}X$ is a vector space in affine space with origin $a$. We can always translate $X$ such that the origin is at $(0,\dots,0)$. Then $x_ {i}-a_ {i}$ becomes $x_ {i}$. Then the tangent plane can be written as a variety itself, since $T_ {a}X = V(f_ {1})$ where $f_ {1}$ is the degree one components of all the $f\in I(X)$. It is because we set $a$ to zero and evaluate $\frac{ \partial f }{ \partial T_ {i} }$ at $a$. 

As an example take 
$$
f(T_{1},T_{2}) = 1+T_{1}-T_{2}+T_{1}T_{2}
$$
then $f_ {1}$ would be 
$$
T_{1}-T_{2}.
$$

Of course we don't have to check everything in $I(X)$ but only the generating functions $S(X)$ of $I(X)$.

For example, let
$$
X = V(x_{2}-x_{1}^{2}),
$$
then the tangent plane at $a = (0,0)$ is just the variety of the degree one components of the defining polynomial $x_{2}-x_{1}^{2}$, which is $x_{2}$. Thus the tangent plane is 
$$
T_ {a}(X) = V(x_{2})
$$
which is the plane given by $x_{2}=0$. 

As our next example, take 
$$
X = V(x_{2}^{2}-x_{1}^{2}-x_{1}^{3})
$$
which intersects itself at the origin. The tangent space by definition is the zero loci of the degree one terms, in our case it is null, then we have 
$$
T_ {0}X = V(\emptyset ) = \text{ the whole } \mathbb{A}^{2}.
$$

As our last example, take
$$
X = V(x_{2}^{2}-x_{1}^{3})
$$
where there is a cusp at the origin. The tangent plane is again $\mathbb{A}^{2}$ at the origin. 

- - -

Well, things are always easier in affine spaces. What if we are facing a general algebraic variety, not necessarily affine, such as projective? The solution is to embed the algebraic variety into affine space again, then the problem becomes a solved one. 

Given an algebraic variety $X$, define $T_ {a}X$ by taking an affine open $U\subset X$ containing $a$, then embed $a$ into $\mathbb{A}^{n}$ with high enough $n$, and setting $T_ {a}X:=T_ {a}U$. 

The problem with this description is that there are a lot of choices one can make. There will be more than one way to choose $U$ and more than one way to choose the imbedding. So is the business independent of all these choices? The answer is luckily yes. 

The trick is to look at the whole thing locally and it become independent of all the choices. 