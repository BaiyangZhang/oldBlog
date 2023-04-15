---
layout:     post   				    # 使用的布局（不需要改）
title:      Discussion with Hui  				# 标题 
subtitle:   Part 1
date:       2023-04-12 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt15.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - Discussion
    - Hui
---



The equation (2.26) reads
$$
\pi_ {0}\left\lvert{\psi}\right\rangle _ {i+1}=- \frac{1}{\sqrt{ Q_ {0} }}P \left\lvert{\psi}\right\rangle _ {i},
$$
to inverse it, we need to inverse 
$$
\boxed { 
\pi_ {0}=-i \frac{ \partial  }{ \partial \phi_ {0} } .
} 
$$

$$
 \frac{ \partial  }{ \partial \phi_ {0} } \left\lvert{\psi}\right\rangle _ {i+1}= \frac{i}{\sqrt{ Q_ {0} }}P \left\lvert{\psi}\right\rangle _ {i}\tag{1}
$$
thus up to a constant of integral we have 
$$
\boxed { 
 \left\lvert{\psi}\right\rangle _ {i+1}=\int d\phi_ {0} \,   \frac{i}{\sqrt{ Q_ {0} }}P \left\lvert{\psi}\right\rangle _ {i} + \text{const}
} \tag{2}
$$
Using some equations, the 

- - -

If you have $\phi_ {0}^{n}$ acting on $\left\lvert{0}\right\rangle_ {0}$ you have $-i \phi_ {0}^{n+1} / (n+1)\left\lvert{0}\right\rangle_ {0}$. 

$$
\int_ {?}^{\overline{\phi}_ {0}} d\phi_ {0} \,  \phi^{n}_ {0}\left\lvert{0}\right\rangle_ {0} 
=\frac{1}{n+1}\overline{\phi}_ {0}^{n+1}\left\lvert{0}\right\rangle _ {0}
$$
if you have $\phi_ {0}^{n}$ acting on $\left\lvert{\psi}\right\rangle_ {0}$ in $P\left\lvert{\psi}\right\rangle_ {i}$, you have $\phi_ {0}^{n+1} / (n+1)\left\lvert{\psi}\right\rangle_ {0}$ in $\left\lvert{\psi}\right\rangle_ {i+1}$

- - -

$$
 \left\lvert{0}\right\rangle _ {1}=\int d\phi_ {0} \,   \frac{i}{\sqrt{ Q_ {0} }}P \left\lvert{0}\right\rangle _ {0} + \text{const}\tag{3}
$$
where
$$
P \left\lvert{0}\right\rangle _ {0} = -i\phi_ {0}\sum\!\!\!\!\!\!\!\!\int \; \frac{d k}{2\pi} \,   \Delta_ {kB}\omega_ {k}\left\lvert{k}\right\rangle _ {0} + \frac{i}{2} \sum\!\!\!\!\!\!\!\!\int \;\frac{d^{2}k}{(2\pi)^{2}} \,  \Delta_ {k_ {1}k_ {2}} (\omega_ {k_ {2}}-\omega_ {k_ {1}})\left\lvert{k_ {1}k_ {2}}\right\rangle _ {0}
$$
substitute into Eq.(3) we have (**up to the integral constant**)
$$
\left\lvert{0}\right\rangle _ {1}=\frac{i}{\sqrt{ Q_ {0} }}\int d\phi_ {0} \,    \left(
 -i\phi_ {0}\sum\!\!\!\!\!\!\!\!\int \; \frac{d k}{2\pi} \,   \Delta_ {kB}\omega_ {k}\left\lvert{k}\right\rangle _ {0} + \frac{i}{2} \sum\!\!\!\!\!\!\!\!\int \;\frac{d^{2}k}{(2\pi)^{2}} \,  \Delta_ {k_ {1}k_ {2}} (\omega_ {k_ {2}}-\omega_ {k_ {1}})\left\lvert{k_ {1}k_ {2}}\right\rangle _ {0} \right)
$$
which seems to be  (**up to the integral constant**)
$$
\left\lvert{0}\right\rangle _ {1}=  \left(
 \frac{1}{2\sqrt{ Q_ {0} }}\phi^{2}_ {0}\sum\!\!\!\!\!\!\!\!\int \; \frac{d k}{2\pi} \,   \Delta_ {kB}\omega_ {k}\left\lvert{k}\right\rangle _ {0} + \frac{-\phi_ {0}}{2\sqrt{ Q_ {0} }} \sum\!\!\!\!\!\!\!\!\int \;\frac{d^{2}k}{(2\pi)^{2}} \,  \Delta_ {k_ {1}k_ {2}} (\omega_ {k_ {2}}-\omega_ {k_ {1}})\left\lvert{k_ {1}k_ {2}}\right\rangle _ {0} \right)
$$