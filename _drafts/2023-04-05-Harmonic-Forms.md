---
layout:     post   				    # 使用的布局（不需要改）
title:     Harmonic Forms			# 标题 
subtitle:   
date:       2023-04-17 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background12.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Minkowski
    - Frankel
---

*Disclaimer: Nothing in this note is original.*


### Hodge Operator

On a (pseudo-)Riemannian manifold $M$ we will first introduce a `pointwise scalar product` between $p$-forms, denoted by pointy brackets, then use it to define a `global` scalar product, denoted by parenthesis. 

The local scalar product of two $p$-forms is defined to be 
$$
\left\langle \alpha,\beta \right\rangle := \alpha_ {I_ {<}} \beta^{I}
$$
where again $I={i_ {1},\dots,i_ {p}}$ is the generalized index and $I_ {<}$ denotes that in the implies sum we have $i_ {1}<i_ {2}<\dots<i_ {p}$. We can denote the orthonormal bases of 1-forms by 
$$
\sigma^{1}, \dots,\sigma^{p}.
$$

The `global` or `Hilbert space scalar product` is defined by 
$$
\left( \alpha,\beta \right) := \int _ {M} \, \left\langle \alpha,\beta \right\rangle \text{Vol} ^{n}.
$$
whenever this makes sense. This will be the case when $M$ is compact, or, more generally, when the integrand has compact support.

Note that the space of smooth $p$-forms on a Riemannian $M$ that satisfy $\left( \alpha,\alpha \right)<\infty$ form only a `pre-Hilbert space` since it is not **complete**; a limit of square integrable smooth forms need not even be continuous. To get a Hilbert space we must "complete" this space. We shall not be concerned here with such matters, and we shall continue to use the inaccurate description "Hilbert space." We shall even go a step further and use this denomination even in the pseudo-Riemannian case, where $\left( -,- \right)$ is not even positive definite.

If $\alpha \in\Omega^{1}(M)$, we may look at its contravariant version $A$ and define a $(n-1)$-form $i_ {A}\text{Vol}^{n}$. We can generalize this procedure, associate to each $p$-form a $(n-p)$-form $\star \alpha$, the `Hodge-dual` of $\alpha$, as follows. If 
$$
\alpha = \alpha_ {I_ {<}} dx^{I}
$$
then
$$
\star \alpha = (\star\alpha) _ {J_ {<}} dx^{J}, \quad  (\star\alpha)_ {J} = \sqrt{ \left\lvert g \right\rvert  } \alpha^{K} \epsilon_ {K_ {<}J_ {<}.}
$$
and where the upper indices $K$ in $\alpha^{K}$ indicate that all of the covariant indices in a have been raised by the metric tensor. Note that here $\epsilon_ {KJ}$ is **not** the Levi-Civita tensor but the Levi-Civita symbol, it simplifies the calculation but the price to pay is that $\alpha^{K}\epsilon_ {K_ {<}J_ {<}}$ can no longer be carelessly rewritten as $\alpha_ {K}\epsilon^{K_ {<}}_ {\;\;\;\; J_ {<}}$. 

For an important special case, the 0-form that is the constant function $f=1$ has
$$
\star 1 = \sqrt{ \left\lvert g \right\rvert  } \epsilon_ {12..d} dx^{1}\wedge dx^{2}\dots \wedge dx^{d} = \text{Vol}^{d}.
$$

We have
$$
\alpha \wedge \star \beta=(\alpha \wedge \star \beta)_ {12\dots n} dx^{1}\wedge \dots \wedge dx^{n},
$$
and then
$$
(\alpha \wedge \star \beta)_ {12\dots n} = \alpha_ {A_ {<}}\beta_ {A} \sqrt{ \left\lvert g \right\rvert  }dx^{1}\wedge \dots \wedge dx^{n}= \left\langle \alpha ,\beta \right\rangle\text{Vol}^{n} .
$$

We have claimed that $\star$ generalized the interior product $\alpha\to i_ {A}\text{Vol}^{n}$. To see this, notice that 
$$
i_ {A} \text{Vol}^{n} = i_ {A}\sqrt{ \left\lvert g \right\rvert  }\epsilon_ {I_ {<}}dx^{I} = \sqrt{ \left\lvert g \right\rvert  } A^{i}\epsilon_ {iJ_ {<}}dx^{J} = \star \alpha,\quad  \alpha_ {i}\equiv A^{i}.
$$

Let $\mathbf{e} = (\mathbf{e}_ {1},\mathbf{e}_ {2},\dots,\mathbf{e}_ {n})$ be an orthonormal frame of vectors. Then $\sigma^{i}$ corresponding to $\mathbf{e}_ {i}$ are also orthonormal and 
$$
\sigma^{}\wedge \dots \wedge \sigma^{n} = \pm \text{Vol}^{n},
$$
and 
$$
\star\sigma^{I} = \pm\sigma^{J}, \quad  J\text{ is the complement of }I.
$$

For example, look at the electromagnetic field in a perhaps curved space-time manifold $M^{4}$. Using the space-time metric, we have 
$$
\star F = \star(E\wedge dt)+\star B.
$$
We know $E = E_ {i} dx^{1}$ so $\star (E\wedge dt)= \star (E_ {i}dx^{i}\wedge dt)= E_ {i}\star(dx^{i}\wedge dt)$ but what is, for example, $\star (dx^{1}\wedge dt)$? We usually don't need to resort to the original definition which can be pretty cumbersome in calculations. Instead we notice that the **Hodge dual is closed related to the inner product and volume form**.  In Minkowski space we have $\left\lvert g \right\rvert=1$ thus we can neglect it. Say, we want to calculate $\star(dx^{2}\wedge dx^{3})$, it has the property that 
$$
(dx^{2}\wedge dx^{3})\wedge \star (dx^{2}\wedge dx^{3}) = \left\langle dx^{2}\wedge dx^{3},dx^{2}\wedge dx^{3} \right\rangle\; \text{Vol}^{4},
$$
which can be calculated using a relation which says that, given 1-forms $\alpha_ {i},\beta_ {j}$ we have 
$$
\left\langle \alpha_ {i_ {1}}\wedge \dots \wedge \alpha_ {i_ {d}}, \beta_ {j_ {1}} \wedge \dots \wedge  \beta_ {j_ {d}}\right\rangle = \det \left\langle \alpha_ {i_ {m}},\beta_ {j_ {n}} \right\rangle  
$$
where the right hand side is a matrix with entry $(m,n)$ given by the inner product. Equipped with above relation and the fact that $dx$ are orthonormal, with convention $g=\text{diag} (1,-1,-1,-1)$ we have 
$$
\begin{align}
(dx^{2}\wedge dx^{3})\wedge \star (dx^{2}\wedge dx^{3}) &= \left\langle dx^{2}\wedge dx^{3},dx^{2}\wedge dx^{3} \right\rangle \text{Vol}^{4} = \left\langle dx^{2},dx^{2} \right\rangle \times \left\langle dx^{3},dx^{3} \right\rangle \text{Vol}^{4}  \\
&=\text{Vol}^{4} = dt\wedge dx^{1}\wedge dx^{2}\wedge dx^{3}
\end{align}
$$
thus we can read-off that 
$$
\star(dx^{2}\wedge dx^{3}) = dt\wedge dx^{1}.
$$
likewise we have 
$$
\star(dt\wedge dx^{1}) = -dx^{2}\wedge dx^{3}.
$$
To summarize, we have
$$
\boxed { 
\begin{align}
\star(dx^{i}\wedge dx^{j} ) &= -\epsilon^{ijk} \,  dx^{k}\wedge dt, \\
\star(dt \wedge dx^{i} ) &= -\frac{1}{2} \epsilon^{ijk}\, dx^{j}\wedge dx^{k}. 
\end{align}
} 
$$


It can be shown that, given $\alpha \in\Omega^{p}(M^{n})$,
$$
\star^{2} = \text{det}(g) (-1)^{p(n-p)}
$$

It is sufficient to verify these for terms of the form $\sigma^{I}$ and to assume these are orthonormal. Remember that $\star\sigma^{I_ {<}} = \pm \sigma^{J_ {<}}$ where $J$ is the compliment of $I$, and the sign dependent on the nature of the metric. 


#### The Codifferential Operator $d^{\dagger}=d^{\star}=\delta$

The codifferential operator $d^{\dagger}$ is the dual of exterior differential $d$ in the sense that, in the global inner product,
$$
(d \alpha^{p-1},\beta^{p} ) \equiv (\alpha^{p-1},d^{\dagger}\beta^{p-1}).
$$
where the superscript denotes the dimension of the form. Thus $d^{\dagger}$ must send a $p$-form to a $(p-1)$-form.

Not recall that 
$$
(d \alpha^{p-1},\beta^{p} ) = \int_ {M} \,  (d\alpha^{p-1})\wedge \star \beta^{p}=(-1)^{p-1}\int_ {M} \,  \alpha^{p-1}\wedge d\star \beta^{p}
$$
and 
$$
(\alpha^{p-1},d^{\dagger}\beta^{p-1}) = \int_ {M} \,  \alpha^{p-1}\wedge \star d^{\dagger}\beta^{p}
$$
then it can be shown that given $\beta \in\Omega^{p}(M)$ if we define 
$$
\boxed { 
d^{\dagger}\beta := \text{det}(g)\, (-1)^{n(p+1)+1}\star d\, \star \beta = (-1)^{p}\star^{-1}d \star \beta
} 
$$
then we would have, given $\alpha \in\Omega^{p-1}(M)$, 
$$
(d\alpha,\beta) - (\alpha,d^{\dagger}\beta) = \int_ {M} \,  d(\alpha \wedge \star \beta).
$$
at least when $\alpha,\beta$ has **compact support**. If $M^{n}$ is closed then $d^{\dagger}$ is indeed the dual of $d$ in the pre-Hilbert space. If $M$ has a boundary, then the statement still holds if either of $\alpha$ and $\beta$ is zero on the boundary. 

The operator $d^{^{\dagger}}$ is called the `codifferential`. The traditional notation is $\delta$ but we will not use it, since we want to keep $\delta$ for variation. Instead we will use $d^{\dagger}$.

A consequence of the definition for exterior derivative 
$$
d\alpha = (\partial _ {\mu}\alpha_ {I_ {<}})dx^{\mu}\wedge dx^{I}
$$
is that, *in a spacetime with a symmetric connection* $\Gamma^{\alpha}_ {\;\mu \nu}=\Gamma^{\alpha}_ {\;\nu \mu}$,  the partial derivative $\partial_ {\mu}$ can always be replaced by the **covariant derivative** $\nabla_ {\mu}$, as the readers can verify, the covariant derivatives introduce new terms concerning the connections, and these terms identically vanish due to the anti-symmetric nature of differential forms. Some calculation shows that a coordinate expression for the $(p-1)$-form $d^{\dagger}\beta$ is 
$$
(d^{\dagger}\beta)_ {K} = - \beta^{i}_ {\;K;j}.
$$

- - -

Recall that the `period` of a form