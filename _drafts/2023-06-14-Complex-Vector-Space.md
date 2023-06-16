---
layout:     post   				    # 使用的布局（不需要改）
title:     Complex Vector Space			# 标题 
subtitle:   
date:       2023-06-14 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background12.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

Quantum mechanics deals almost exclusively with sections of complex vector fields, so it is important to understand the mathematical structure of it. 

Consider the complex plane $\mathbb{C}$ with $z=x+iy$. $\mathbb{C}$ is a one-dimensional vector space in terms of complex dimension $\text{dim}_ {\mathbb{C}}$, which is also a two dimension manifold in terms of real dimension $\text{dim}_ {\mathbb{R}}$. A complex number $z$ can be written as a 
$$
z= (x,y)^{T}
$$
where $T$ is the transpose. With this notation, the multiplication of $i$ is translated into a $2\times 2$ matrix, 
$$
iz = i(x+iy) = -y+ix,\quad  i: 
\begin{pmatrix}
x \\ y
\end{pmatrix} \to 
\begin{pmatrix}
0 & -1 \\
1 & 0
\end{pmatrix}
\begin{pmatrix}
x \\ y
\end{pmatrix}
$$
It is conventional to denote the matrix by $J$,
$$
J = \begin{pmatrix}
0 & -1 \\
1 & 0
\end{pmatrix}, \quad  J^{2}=-\mathbb{1}_ {2\times 2}.
$$

What we did before can be trivially generalized to $\mathbb{C}^{K}$, then 
$$
z = (z_ {1},\dots,z_ {K}) = (x_ {1}+iy_ {1},\dots,x_ {k}+iy_ {K})\to(x_ {1},y_ {1},\dots,x_ {K},y_ {K}) =: \mathbf{x} \in \mathbb{R}^{2K}
$$
and
$$
J = \text{diag}(J, \dots,J)
$$
where we have abused the notation a little, it is understood that $J$ in the parenthesis are two-dimensional and $J$ on the LHS is $2K$ dimensional, all in the sense of real dimensions.

Note that, given the Euclidian metric, $J$ is an isometry,
$$
\left\langle x,x' \right\rangle =\left\langle Jx,Jx' \right\rangle .
$$

