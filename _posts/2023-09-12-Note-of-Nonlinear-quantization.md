---
layout: post
title: Note of Nonlinear Quantization
subtitle: 
date: 2023-09-12
author: Baiyang Zhang
header-img: img/lib13.jpg
catalog: true
tags: []
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

- - -

### The kinetic term

The kinetic terms are the terms in the Lagrangian that contains time derivatives.

The most general rotation of a Skyrmion include both spatial rotation and iso-rotation, 
$$
U(x,t) = A_ {1}(t) U_ {0}(D(A_ {2})(x-x_ {0})) A_ {1}(t)^{\dagger}
$$
where $U_ {0}$ is the static (time-independent) solution, $x_ {0}$ is the center of the Skyrmion, $A_ {1,2}$ are both $SU(2)$ matrices, $A_ {1}$ denotes the iso-rotation and $D(A_ {2})$ the spatial rotation. However, when we consider *the special Skyrmion configuration*, namely the hedgehog Skyrmion, the iso-rotation is equivalent to spatial rotation (for more details see the other note I made on Skyrmion), so we can just take one $A$ matrix. The convention is that we take $A_ {1}$, neglect the subscript $1$ we have
$$
U(x,t) = A(t)U_ {0}A(t)^{\dagger}.
$$
Making use of the specific form of the hedgehog solution, we can translate the time-dependent in $A(t)$ to 
$$
U(\mathbf{x},t) = U_ {0}(R(t) \mathbf{x}),\quad  R_ {ij}(t) = \frac{1}{2}\mathrm{Tr}\,(\sigma_ {i} A \sigma_ {j} A^{\dagger}).
$$

- - -

Since $A(t)$ can be written as 
$$
A(t) = \alpha_ {0}(t) + i\alpha_ {i}(t)\sigma^{i}, \quad  \alpha \in \mathbb{R}
$$
and $\det(A)=1$ requires that 
$$
\alpha_ {0}^{2}+\alpha_ {i}\alpha_ {i} = 1,
$$
thus the trajectory of $A(t)$ can be regarded as a curve on $\mathbb{S}^{3}$. Then $\dot{A}(t)$ is perpendicular to $A(t)$, thus we have 
$$
\begin{align}
\mathrm{Tr}\,(A ^{\dagger}(t)\dot{A}(t))&=\mathrm{Tr}\,[(\alpha_ {0}\mathbb{1}_ {2}-i\alpha_ {i}\sigma^{i})\cdot(\dot{\alpha}_ {0}\mathbb{1}_ {2}+i \dot{\alpha}_ {j}\sigma^{j})] \\
&=2\alpha_ {0}\dot{\alpha}_ {0}+\alpha_ {i}\dot{\alpha}_ {j}2\delta_ {ij} \\
&= 2(\alpha_ {0},\alpha_ {1},\alpha_ {2},\alpha_ {3})\cdot(\dot{\alpha}_ {0},\dot{\alpha}_ {1},\dot{\alpha}_ {2},\dot{\alpha}_ {3}) \\
&=0.
\end{align}
$$

Furthermore, $A^{\dagger}\dot{A}$ is also skew-hermitian since 
$$
(A^{\dagger}\dot{A})^{\dagger}=(\dot{A}^{\dagger} A) = -A^{\dagger}\dot{A}.
$$

As a traceless anti-hermitian $2\times 2$ matrix, it can be expanded in the basis of three Pauli matrices with pure imaginary coefficients. Writing
$$
A^{\dagger}\dot{A} = \frac{i}{2} a_ {i} \sigma^{i}
$$
then the inverse is easily given by 
$$
a_ {i} = -i \mathrm{Tr}\,\left\{ \sigma _ {i} A^{\dagger}\dot{A} \right\} ,\quad  t\text{-dependent.}
$$

To avoid confusion, let us denote the time dependent rignt-currents as $\widetilde{R}_ {\mu}$ and keep $R_ {\mu}$ for time independent versions, that is $\widetilde{R}_ {\mu}:= A R_ {\mu}A^{\dagger}$. 

Straightforward calculation shows that 
$$
\mathrm{Tr}\,\widetilde{R}_ {0}^{2}=2\mathrm{Tr}\,(M\cdot M-MU_ {0}MU_ {0}^{\dagger}),\quad  M:=A^{\dagger}\dot{A}
$$
and if we define 
$$
T_ {i} =\frac{i}{2}[\sigma _ {i} ,U_ {0}]U_ {0}^{\dagger}
$$
we have
$$
\mathrm{Tr}\,\widetilde{R}_ {0}^{2}=\mathrm{Tr}\,(T_ {i} a_ {i} T_ {j} a_ {j} ) = \mathrm{Tr}(T_ {i} T_ {j} ) \,a_ {i} a_ {j} .
$$

The kinetic energy reads
$$
T = \int d^3x \left[-\frac12\mathrm{Tr}\,(\widetilde{R}_0^2)-\frac{2\eta-1}{8}\mathrm{Tr}\,\left([\widetilde{R}_0,\widetilde{R}_i]^2\right)-\frac{1-\eta}{8}\left(\mathrm{Tr}\,(\widetilde{R}_0^2)\right)^2+\frac{1-\eta}{4}\mathrm{Tr}\,(\widetilde{R}_0^2)\mathrm{Tr}\,(\widetilde{R}_i^2)\right]
$$
We can rewrite it in terms of $a_ {i}$'s and regard $a_ {i}$'s as some kind of **angular velocity**.  We have
$$
\boxed {
T_ {i} a_ {i}  = [A^{\dagger}\dot{A},U_ {0}]U_ {0}^{\dagger} = A^{\dagger}\widetilde{R}_ {0}A
} 
$$
and
$$
\widetilde{R}_ {i}  = A (\partial_ {i}U_ {0})U_ {0}^{\dagger}A^{\dagger} = A R_ {i} A^{\dagger},
$$
Then we can rewrite the Lagrangian as following (to isolate-out the time dependent part).

$$
\begin{align}
 \mathrm{Tr}\,\widetilde{R}_ {0}^{2}& =  \mathrm{Tr}\,(T_ {i} T_ {j} )a_ {i} a_ {j} , \\
\mathrm{Tr}\,\left([\widetilde{R}_0,\widetilde{R}_i]^2\right)&= \mathrm{Tr}\,([T_ {i},R_ {i} ][T_ {j},R_ {i} ])a_ {i} a_ {j} , \\
\left(\mathrm{Tr}\,(\widetilde{R}_0^2)\right)^2&= \mathrm{Tr}\,(T_ {i} T_ {j} ) \mathrm{Tr}\,(T_ {m} T_ {n} ) a_ {i} a_ {j} a_ {m} a_ {n}
\end{align}
$$

This agrees with Eq.(2.16) in the paper draft, which is 
$$
\begin{align}
T &= \int d^3x\left[-\frac12\mathrm{Tr}\,(T_i T_j)-\frac{2\eta-1}{8}\mathrm{Tr}\,\left([T_i,R_k][T_j,R_k]\right)+\frac{1-\eta}{4}\mathrm{Tr}\,(T_i T_j)\mathrm{Tr}\,(R_k^2)\right]a_i a_j \\
&\phantom{=\ }+\int d^3x\left[-\frac{1-\eta}{8}\mathrm{Tr}\,(T_i T_j)\mathrm{Tr}\,(T_k T_l)\right]a_i a_j a_k a_l,
\end{align}
$$

Now what we need to do is to substitute the Hedgehog solution into the above expression. It's done with the help of Mathematica.

- - -

By the end of the day, we have the expression for kinetic energy where the Hedgehog ansatz is adopted, 
$$
T = \frac{1}{2} \Lambda_ {1} a ^{2}  - \frac{1}{4} \Lambda_ {2} a^{4},\quad  a^{2}:=a_ {i} a_ {i} , \,a^{4}:= a_ {i} a_ {i} a_ {j} a_ {j} ,
$$
where $\Lambda_ {1}$ is something like $\text{positive}+ \eta(\text{positive})$, while $\Lambda_ {2}$ is something like $(1-\eta)\text{positive}$. 

From this we can get the canonical momentum of $a_ {i}$, call it $J_ {i}$
$$
J_ {i}  = \Lambda_ {1}a_ {i} -\Lambda_ {2}a^{2} a_ {i}
$$
which squares to 
$$
J^{2} = \Lambda_ {2}^{2}a^{6}-2\Lambda_ {1}\Lambda_ {2}a^{4}+\Lambda_ {1}^{2}a^{2}.
$$
Define $x:=a^{2}$ to simplify the notations, we want to solve the equation
$$
y(x) =  \Lambda_ {2}^{2} x^{3}-2\Lambda_ {1}\Lambda_ {2}x^{2}+\Lambda_ {1}^{2}x-J^{2}=0,
$$
the solution will be something like $x=x(J)$. 

Being a cubic equation there exists three solutions, for details see the other note [here](http://www.mathlimbo.net/2023/07/07/Quartic-Time-Derivative/). 

In the limit $\eta\to 1$, for a finite positive $J^{2}$, there will always be three roots, all positive. The smallest one goes to a fixed finite value, while the other two goes to infinite. The root that stays finite in this limit is the root that goes to the original Skyrme result. So it makes sense to focus on it and regard it as the correct starting point. 

Now the question is, what are the kinetic energies given by the three non-degenerate roots, when $\eta<1$. The kinetic energy in terms of $x$ reads
$$
T = \frac{1}{2} \Lambda_ {1} x  - \frac{1}{4} \Lambda_ {2} x^{2},\quad  x:=a_ {i} a_ {i}.
$$

Our goal is to substitute $x$ in kinetic energy from $x$ to $J^{2}$. The problem is that, for each value of $J^{2}$ we have three different values of $x$. Given three real roots $x_ {\text{min}}$, $x_ {\text{mid}}$ and $x_ {\text{max}}$, they will give different value of $T$, however in terms of $J^{2}$ they will give the same $T$ since they give the same $J^{2}$. It is reasonable to adopt $x_ {\text{min}}$ as the correct solution since it is what reproduces the Skyrme result when $\eta\to 0$. Let's go back to the original equation
$$
y(x) =  \Lambda_ {2}^{2} x^{3}-2\Lambda_ {1}\Lambda_ {2}x^{2}+\Lambda_ {1}^{2}x-J^{2}=0,
$$
and see if we can express $x$ in terms of $J^{2}$ explicitly. The `discriminant` of above equation is 
$$
\Delta = -J^{2} \beta^3  \left(4 \alpha ^3+27 \beta  J^{2}\right).
$$
where 
$$
\alpha :=\Lambda_ {1}>0,\quad \beta:=-\Lambda_ {2}<0$$
and $J^{2}>0$. If the discriminant $\Delta>0$ then we have three non-degenerate roots, the positivity of $\Delta$ means
$$
\alpha^{3}>- \frac{27}{4} \beta J^{2}.
$$
In the limit $\eta\to 1$, $\beta\to 0$ so we require $\alpha^{3}>0$, which is automatically satisfied. This confirms that in this limit there will always be three degenerate roots. 

Define 
$$
x=t-\frac{2\alpha}{3\beta}=:t+\frac{2\sqrt{ -p }}{\sqrt{ 3 }}
$$
where
$$
\begin{align}
p&= -\frac{\alpha^{2}}{3\beta^{2}}, \\
q&= - \frac{2\alpha^{3}}{27\beta^{3}}-\frac{J^{2}}{\beta^{2}},
\end{align}
$$
then the cubic equation adopts the depressed form,
$$
t^{3}+p y^{2} +q=0.
$$
The discriminant in terms of $p$ and $q$ is 
$$
\Delta = -4 p^3 - 27 q^2, \quad  \Delta > 0 \implies 4 p^3 + 27 q^2<0.
$$
We can see from the definition that $p<0$ but $q$ is not necessarily so. If we solve for the minimum root $x$, we get (from mathematica)
$$
\boxed { 
x_ {\text{min}}=\frac{i \left(\sqrt{3}+i\right) \sqrt[3]{\sqrt{12 p^3+81 q^2}-9 q}}{2 \sqrt[3]{2} 3^{2/3}}+\frac{p+i \sqrt{3} p}{2^{2/3} \sqrt[3]{3} \sqrt[3]{\sqrt{12 p^3+81 q^2}-9 q}}+\frac{2}{3} \sqrt{ -3p }
\tag{3}
}
$$
which simplifies to (by hand mostly) 
$$
\boxed {
x_ {\text{min}} = \frac{4}{\sqrt{ 3 }}\sqrt{ -p }\,\sin ^{2}\left( \frac{\theta}{6}\right) ,\quad  \theta=\arctan \left( \frac{\sqrt{-12 p^3-81 q^2}}{-9q} \right)
\tag{4}.
}
$$
This is as simple as I can get. I check it numerically, it works out.