---
layout:     post   				    # 使用的布局（不需要改）
title:     The Classical Electrodynamics in terms of Forms			# 标题 
subtitle:   ?
date:       2023-04-05 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background11.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*

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

