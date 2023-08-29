---
layout:     post   				    # 使用的布局（不需要改）
title:     Note-of-Nonlinear-quantization 			# 标题 
subtitle:   
date:       2023-08-28 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/lib13.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 
---

### The Lagrangian

The rescaling works as follows. The length is measured by a length scale $\lambda$ as $x^{\mu} := \lambda x'^{\mu}$ where $x'$ is now dimensionless. I suspect the energy integral is measured by an energy unit $\mu$ by 
$$
E = \int d^{3}x \,  \mathcal{E} := \mu\, \int d^{3}x \,  \mathcal{E} / \mu =\mu\, \int d^{3}x' \, \lambda^{3} \mathcal{E} / \mu.
$$
Then $\mathcal{E} / \mu$ is a dimensionless parameter. 

The term 
$$
\mathcal{L}_ {k} := \frac{F_ {\pi}^{2}}{16}\mathrm{Tr}\,(R_ {\mu}^{2})
$$
(k for kinetic) is re-expressed as
$$
L_ {k} = \frac{F_ {\pi}^{2} \lambda^{-2}}{16}\mathrm{Tr}\,(R_ {\mu'}^{2})
$$
since $R_ {\mu} \sim \partial_ {\mu}(-) = \lambda ^{-1}\partial_ {\mu'}(-)$, where $\partial_ {\mu'}$ is the derivative with respect to $x'$. Then the according contribution to the energy (Denoted by $E_ {k}$)
$$
E_ {k} = \int d^{3}x \,  \mathcal{L}_ {k}
$$
takes the new form
$$
E_ {k} =\mu \int d^{3}x' \, \mu ^{-1}  \lambda^{3} \frac{F_ {\pi}^{2} \lambda^{-2}}{16}\mathrm{Tr}\,(R_ {\mu'}^{2})
$$
and I guess we want this to give
$$
E_ {k} =\mu \int d^{3}x' \, \frac{1}{2} \mathrm{Tr}\,(R_ {\mu'}^{2})
$$
thus we have the relation
$$
\boxed { 
8\mu = F_ {\pi}^{2}\lambda.
}\tag{relation 1}
$$

Now turn the the Skyrme term $\mathcal{L}_ {s}$. Do the same trick, in new unites we have 
$$
\begin{align}
E_ {s} &= \mu \int d^{3}x' \,  \mu ^{-1} \lambda^{3}\mathcal{L}_ {s} \\
&=\mu \int d^{3}x' \,  \mu ^{-1} \lambda^{3} \frac{\lambda^{-4}}{32e^{2}}\mathrm{Tr}\,([R_ {\mu'},R_ {\nu'}]^{2})
\end{align}
$$
where the factor $\lambda^{-4}$ again comes from re-express the derivative in $R_ {\mu}$. If we identify it with
$$
E_ {s} = \mu\,\int d^{3}x' \, \frac{2\eta-1}{16}\mathrm{Tr}\,[R_ {\mu'},R_ {\nu'}]^{2}
$$
where 
$$
\boxed { 
\frac{1}{e^{2}} := \alpha^{2}(2\eta-1),\quad  \beta := 2\alpha^{2}(1-\eta)
}
$$
then we have another relation,
$$
\boxed { \frac{\alpha^{2}}{2}=\mu \lambda .}
\tag{relation 2}
$$

From relation 1 and 2 we can solve for $\lambda$ and $\mu$ in terms of $\alpha$ and $F_ {\pi}$, 
$$
\begin{cases}
\mu = \frac{F_ {\pi}\alpha}{4}, \\
\lambda =\frac{2\alpha}{F_ {\pi}}.
\end{cases}
$$

Then follow the paper draft we can also get 
$$
m_ {1} = \frac{2\alpha m_ {\pi}}{F_ {\pi}}
$$
and 
$$
m_ {2}=\frac{2\alpha M}{F_ {\pi}}.
$$