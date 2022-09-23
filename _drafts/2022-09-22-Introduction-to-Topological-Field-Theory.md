---
---
layout:     post   				    # 使用的布局（不需要改）
title:      Introduction to Topological Field Theory			# 标题 
subtitle:   
date:       2022-09-22 				# 时间
author:     Baiyang Zhang 						# 作者
header-img: img/mathArt12.jpg 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - TopologicalFieldTheory
    - CategoryTheory
    - Notes
---

### Path Integral Topological QFT

Consider a set of fields on a Riemannian n-manifold $M^n$ with a metric $g_{\mu\nu}$, the action of the theory, which is a real-valued function of the fields $S[\phi_{i}]$, and a set of special operators which we call observables, $\mathcal{O}_{i}(\phi_{j})$. The vacuum expectation value (VEV) of these operators are usually of interests to us. It is given by the path-integral form
$$
\left\langle \mathcal{O}_{1} \dots \mathcal{O}_{p} \right\rangle = \int \mathcal{D}\phi_{i} \mathcal{O}_{1} \dots \mathcal{O}_{p} \exp(-S[\phi_{i}])
$$
where we assume the correct normalization. 

A quantum field theory is considered **topological** if the observable operators are invariant under the change of the metric, 
$$
\frac{\delta}{\delta g_{\mu\nu}} \left\langle \mathcal{O}_{1} \dots \mathcal{O}_{p} \right\rangle = 0
$$

There are two ways of making this happen. One of them is most obvious,
- The action is independent of  the metric $g_{\mu\nu}$,
- The operator whose vev we are interested in is also independent of the metric.

This is called the Schwarz-type TQFT (short for topological Quantum Field Theory).

At first sight this condition seems too good to be true, for instance, the kinetic term in the Lagrangian $\partial_{\mu}\phi \partial^{\mu}\phi$ is not independent of the metric, since by definition $\partial_{\mu}\phi \partial^{\mu}\phi = g^{\mu\nu} \partial_{\mu}\phi \partial_{}{\nu}\phi$. However, there really exists examples of Schwarz-type TQFT models, the most famous and important one being the Chern-Simons model.

The data in Chern-Simons gauge theory are the following:
- A differentiable 3-manifold $M$, 
- a gauge group $G$, which we assume is simple and compact. Recall that a group is simple if the only normal subgroups are trivial and itself, and a subgroup $N<G$ is said to be normal if for all $g\in G$, we have $g N g^{-1} = N$, and a normal subgroup is denoted $N \lhd G$.
- 