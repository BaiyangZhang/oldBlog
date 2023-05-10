---
layout:     post   				        # 使用的布局（不需要改）
title:      Soliton Particle Duality in (1+1)D 	# 标题 
subtitle:   T-Duality, etc.      # 副标题
date:       2023-05-07			        # 时间
author:     Baiyang Zhang 				# 作者
header-img: img/lib1.jpg 	        # 这篇文章标题背景图片
catalog: true 						    # 是否归档
tags:								    # 标签
    - math
    - quantum field theory
    - confinement
    - duality
---

### Convention and Notations
We will often neglect the wedge symbol $\wedge$ in writing products of differential forms; for example, if $a$ is a one-form then 
$$
a^{3}:=a\wedge a\wedge a.
$$

Antisymmetrization of indices is denoted with square brackets so that e.g.
$$
T_ {[abc]}:= \frac{1}{3!} \sum_ {P} (-1)^{P}\,T_ {P(abc)},\quad  P(abc) \text{ is the permutation of } abc.
$$

The field strength in terms of differential forms is 
$$
F = dA -i A \wedge A=: dA-iA^{2}.
$$

We will use $\epsilon_ {ijk}$ to denote the usual Levi-Civita tensor with no spacetime signature, using the metric to raise the indices we get the $\epsilon^{ijk}=\sqrt{ g }\,\tilde{\epsilon}^{ijk}$ where $g$ is the determinant of the metric and $\tilde{\epsilon}$ is the Levi-Civita symbol. 

The $\gamma$ matrices in $(2+1)$ dimension are taken to be 
$$
\gamma^{0} = \sigma^{2}, \quad  \gamma^{1} = i\sigma^{1},\quad  \gamma^{2} = i\sigma^{3}.
$$
This is the Majorana basis, in which all the gamma matrices are imaginary. 

The gamma matrices must satisfy 
$$
\left\{ \gamma^{\mu},\gamma^{\nu} \right\} = 2\eta^{\mu \nu}.
$$

They also satisfy
$$
\mathrm{Tr}\,\gamma^{\mu}\gamma^{\nu} = 2\eta^{\mu \nu},\quad  \mathrm{Tr}\,\gamma^{\mu}\gamma^{\nu}\gamma^{\sigma} = 2i\epsilon^{\mu \nu \sigma},\quad  \mathrm{Tr}\,\gamma^{\mu}\gamma^{\nu}\gamma^{\rho}\gamma^{\sigma}=2\eta^{\mu \nu}\eta^{\rho \sigma}-(\nu \leftrightarrow \rho)+(\nu \leftrightarrow \sigma).
$$
A Dirac spinor in 2+1 dimension is a two-component, complex vector object. 

### Electromagnetism in Three Dimensions



