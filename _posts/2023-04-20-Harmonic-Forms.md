---
layout:     post   				    # 使用的布局（不需要改）
title:     Harmonic Forms			# 标题 
subtitle:   
date:       2023-04-20 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/background18.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Geometry
    - Hodge
    - Frankel
---

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
(d^{\dagger}\beta)_ {K} = - \beta^{i}_ {\;K;i} \equiv - \nabla_ {i}\beta^{i}_ {\;K}.
$$
We shall call the negative of the right-hand side the Divergence (with a capital D) of the form,
$$
(\text{Div}\beta)_ {K} :=  \nabla_ {i}\beta^{i}_ {\;K}.
$$

- - -

Recall that the `periods` of a closed form are the values of the integration of the form along integral (meaning with integer coefficients) homology cycles. Here the question we want to answer is, among all closed forms with a given set of periods, which one has the smallest global norm? 

In a Cartesian coordinate system the Laplacian of a function $f$ is the familiar $\nabla^{2}f=\partial^{2}f / \partial x^{i} \partial x^{i}$. The Laplacian of a $p$-form is more complicated. It is defined as 
$$
\boxed { 
\Delta : \Omega^{p} \to \Omega^{p}, \text{ by } \Delta := dd^{\dagger}+d^{\dagger}d
} 
$$

Occasionally we shall write $\nabla^{2}=-\Delta$, different from the convention in the Cartesian coordinates for functions. 

In components we have 
$$
\Delta \alpha = (- \nabla^{i}\nabla_ {i}\alpha_ {j}\,dx^{j}) + (\alpha_ {k}R^{k}_ {\;\;j}\;dx^{j})\tag{Weizenbock}
$$
where $R^{k}_ {\;j}$ is the Ricci tensor. Note that we have covariant derivative $\nabla$ instead of partial derivative $\partial$. 

- - -

### Harmonic Forms on Closed Manifolds

Let $M$ be a $n$ dimensional compact, Riemannian manifold, then the (global) inner product is positive-definite, 
$$
(\alpha,\alpha)\geq 0
$$
and is zero only if $\alpha=0$. 

A form $\alpha$ is said to be `harmonic` if 
$$
\Delta\alpha = (dd^{\dagger}+d^{\dagger}d)\alpha=0,
$$
if $\alpha$ is a function then it reduces to the usual notion. 

Note that $\Delta$ is `self-adjoint `since $\Delta ^{\dagger}=\Delta$. Let $M$ be a closed (without boundary and compact) manifold, we have 
$$
(\Delta \alpha,\alpha) = (dd^{\dagger}\alpha+d^{\dagger}d\alpha,\alpha)=(d\alpha,d\alpha)+(d^{\dagger}\alpha,d^{\dagger}\alpha)\geq 0
$$
and it is only zero if
$$
d\alpha=0 \text{ and }d^{\dagger}\alpha=0
$$
**thus a form on a a closed manifold is only harmonic if it is both closed and co-closed!** 

This is far different from the situation in $\mathbb{R}^{n}$. For example, a closed 0-form is simply constant function, yet harmonic functions in $\mathbb{R}^{n}$ need not be constant, the real part of any complex analytic function in the plane is harmonic!

The Laplace operator $\Delta: \Omega^{p}\to \Omega^{p}$ is an `elliptic operator` on a Riemannian manifold. The main ingredient is that the metric tensor is positive definite. In Minkowski space, however, the Laplacian of a function becomes the d' Alembertian.

**Hodge's Theorem.** Let $M^{n}$ be a closed Riemannian manifold. The harmonic $p$-forms form a vector space
$$
\mathcal{H}^{p} := \left\{ \alpha \in \Omega^{p}(M)  \,\middle\vert\, d\alpha=d^{\dagger}\alpha=0 \right\} .
$$
It is finite-dimensional and **Poisson's equation**
$$
\Delta \alpha=\rho,\quad \rho \in \Omega^{p}(M)
$$
has solution iff $\rho$ is orthogonal to $\mathcal{H}^{p}$, 
$$
(\rho,\alpha)=0 \;\forall\; \alpha \in \mathcal{H}.
$$


The finite dimensionality $\mathcal{H}$ is a deep result on elliptic operators on closed manifolds. It is easy to see the necessity of the condition on $\rho$ in order that there be a solution to Poisson's equation; if $\rho = \Delta \alpha$,
$$
(\rho,h) = (\Delta \alpha,h)=(\alpha,\Delta ^{\dagger}h)=(\alpha,\Delta h)=0.
$$
The deep part is showing the sufficiency of this condition. 

- - -

**The Hodge decomposition on a closed manifold**

Let $\beta$ be a $p$-form on $M$ and let $h_ {1},\dots,h_ {r}$ be an orthonormal basis for $\mathcal{H}^{p}(M)$. For notation simplicity, define
$$
\beta-h := \beta - \sum_ {r} (\beta,h_ {r}) h_ {r},
$$
which is the component orthogonal to $\mathcal{H}$. Then, by Hodge's theorem, we can solve 
$$
\Delta \alpha = \beta-h
$$
for some p-form $\alpha$. In other words, for any $\beta$ on $M$ we could write 
$$
\beta = dd^{\dagger}\alpha + d^{\dagger}d\alpha + h
$$
which is a sum of exact form $d(d^{\dagger}\alpha)$ and coexact form $d^{\dagger}d\alpha$ and a harmonic form.  This is true for any p-form on the closed $M$. Hence
$$
\boxed { 
\Omega^{p} = d\Omega^{p-1}+d^{\dagger}\Omega^{p+1}+ \mathcal{H}^{p}.
} 
$$
Note further that the three subspaces are mutually orthogonal,
$$
(d,d^{\dagger})\equiv 0.
$$
This is called the **Hodge decomposition.**

Note that the decomposition is unique. 

In the case of a closed 3-manifold we have $\beta^{1}= d\phi^{0}+d^{\dagger}\mu^{2}+h^{1}$, that is,
$$
\mathbf{B} = \text{grad }\phi + \text{curl }\mathbf{M} + \mathbf{H}
$$
that is, a smooth vector field can be written as the sum of a gradient, a curl, and a vector field that has both vanishing curl and divergence. This version is also true in the noncompact $\mathbb{R}^{3}$, at least when the growth of $\mathbf{B}$ at infinity is controlled; this is the classical `Helmholtz decomposition`, which is so useful in vector analysis.

### Harmonic Forms and De Rham's Theorem

Any p-form $\beta$ may be written in the form 
$$
\beta = d \alpha + d^{\dagger}\gamma+h,\quad h\text{ is harmonic,}
$$
since the decomposition is orthogonal, if $\beta$ is closed, then 
$$
\beta = d \alpha + h, \text{ no } d^{\dagger}\gamma.
$$
Now, $\beta$ and $\beta - d\alpha$ are in the same de Rham class since they differ by $d(\text{sth})$, thus

**Corollary.** In each de Rham class $[\beta]$ there is a unique harmonic representative $h(\beta)$. Thus there exists a unique harmonic $p$-form with $b_ {p}$ (the Betti number) prescribed periods on a homology basis for the real p-cycles on $M$. 

Assume that one has a *closed* p-form $\beta^{p}$ on a closed manifold $M$. The 1-parameter family of forms $\beta(\epsilon):= \beta+\epsilon d\alpha$ are closed, with the same period, for all $\alpha$. This yields a variation of $\beta$ with $\delta \beta = d\alpha$. Supposed $\beta$ is the closed form with the prescribed periods *whose norm is a minimum.*` Dirichlet's principle` presumed that such a minimum norm element had to exist. Look then at the first variation as we vary $\alpha$, 
$$
\delta(\beta,\beta)=0=2(\delta \beta,\beta) = 2(d \alpha,\beta)=2(\alpha,d^{\dagger}\beta),
$$
**since this holds for all $\alpha$ we conclude that $\beta$ is not only closed, it is coclosed, $d^{\dagger}\beta=0$, and thus harmonic!**

We just mention that it was pointed out by Weierstrass that Dirichlet's principle was not always reliable and thus the indicated proof is defective.  However, the (difficult) Hodge decomposition justifies the norm claim since
$$
\left\lvert \beta \right\rvert ^{2}=\left\lvert d\alpha \right\rvert ^{2}+\left\lvert h \right\rvert ^{2}
$$
shows that in the de Rham class $[\beta]$, **the harmonic representative $h$ has the smallest norm!**

- - -

The prime example of a manifold with boundary is the case of a bounded region in $\mathbb{R}^{3}$ with smooth boundary. If a fluid fills such a domain, with smooth walls forming the boundary, then the velocity vector field $\mathbf{v}$ is tangent to the boundary. If the flow is incompressible, then the velocity field has divergence $0$. If further the flow is irrotational, then the velocity has zero curl and the resulting velocity 1-form field $\nu$ is harmonic. We are interested in the existence of such fields and we shall find that with some type of prescribed topological restriction the solution becomes unique.

**Note that in a compact manifold with boundary, $d$ and $d^{\dagger}$ are not necessarily adjoints, and it is no longer true that $\Delta \alpha=0$ iff $d\alpha = d^{\dagger}\alpha=0$.** There will be extra surface terms. Furthermore, $\Delta$ is no longer self-adjoint. For physical problems involving forms we shall reserve the term harmonic `field` for forms that satisfy
$$
d\alpha = d^{\dagger}\alpha =0.
$$

Thus a harmonic 0-`field` is constant, whereas a harmonic function, that is 0-form , of course, need not be.

