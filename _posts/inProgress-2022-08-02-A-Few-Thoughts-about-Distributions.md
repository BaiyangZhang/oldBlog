---
layout:     post   				    # 使用的布局（不需要改）
title:      A few thoughts about distributions 				# 标题 
subtitle:    #副标题
date:       2022-08-02 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/functionalAnalysis.png 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 数学
    - 泛函分析
    - 分布
---

<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>



## There are so much more to integrals than just Riemann integral

The concept of integral is deceptively simple -- just summation at its finest.

As Terence Tao pointed out in the book... (three kinds of integrals)

Introduce the measure theory here, the $\sigma$-algebra, where $sigma$ stands for the union, and the measureble sets $\mathfrak{m}$.

## Distributions against Test function in $l^n$ and $L^n$


Classically, function are defined set-theoretically. For example, on the Wiki page of function it says 

>In mathematics, a function from a set X to a set Y assigns to each element of X exactly one element of Y. The set X is called the domain of the function and the set Y is called the codomain of the function. Functions were originally the idealization of how a varying quantity depends on another quantity. For example, the position of a planet is a function of time. Historically, the concept was elaborated with the infinitesimal calculus at the end of the 17th century, and, until the 19th century, the functions that were considered were differentiable (that is, they had a high degree of regularity). The concept of a function was formalized at the end of the 19th century in terms of set theory, and this greatly enlarged the domains of application of the concept.
>
>A function is most often denoted by letters such as $f$, $g$ and $h$, and the value of a function f at an element $x$ of its domain is denoted by $f(x)$; the numerical value resulting from the function evaluation at a particular input value is denoted by replacing $x$ with this value; for example, the value of $f$ at $x = 4$ is denoted by $f(4)$. When the function is not named and is represented by an expression $E$, the value of the function at, say, $x = 4$ may be denoted by $E\rvert_x=4$. For example, the value at $4$ of the function that maps $x$ to $(x+1)^{2}$ may be denoted by $\left.(x+1)^{2}\right\rvert _{x=4}$ (which results in 25).
>
>A function is uniquely represented by the set of all pairs (x, f (x)), called the *graph* of the function, a popular means of illustrating the function. When the domain and the codomain are sets of real numbers, each such pair may be thought of as the Cartesian coordinates of a point in the plane.

The most important operation for a function is *evaluation*.

Two evaluations are not defined for test functions in $L^2(\Omega)$. First is the evaluation. *Evaluation is not important for test functions*! Second is the *point-wise operations between two functions*, such as point-wise multiplication or division or additions or subtraction, precicely because evaluation is not defined!

There are various kinds of functions, they could be very smooth hence quite special, or very general but don't have any of the nice properties such as smoothness or continuity.

So what is Dirac $\delta$ function? It's better to consider it as an abstract things that, when given a function, it spits out a real or complex number.

First explain the name, why are they called distributions. Then introduce it as the dual space of test functions. 

Distributions can also be treated as the weak limit of functions. Explain what is weak limit and strong limit in a vector space. Example 1, $\sin(nx)$ on $[0,2\pi]$ weakly converges to $0$. In this sense, the inner product is degenerate, it's not a psudo-Riemann space.

## Schwartz functions and tempered distribution. What are they and why we need them.

Mention Parseval's theorem.

Some functions are integrable, $\int dx |f(x)|<\infty$, but their Fourier transform are not, $\int dk \tilde{f}(k) \to \infty$. Give an example.

Introduce the space of Schwartz functions and tempered distributions.

Finally, as an example, we can understand better the equality $\frac{1}{1+i\epsilon} = \text{p.v.} \frac{1}{x}  - i\pi \delta(x)$.

