

### Some questions about the failure of $\widetilde{f}_{0}$ at finite $\Lambda$

In your AppAdetail note it is mentioned that, from Eq. (38) to Eq. (39),

> we assumed it was valid to commute the operations of taking the $\epsilon_2 \to 0$ limit (implicit in the definition of the principal value integral) with doing the integral over $q_1$.

For your convenience I copy the equations here, Eq. (38) reads 
$$
\begin{align}
\int_{-2\Lambda}^{2\Lambda} G(q) u(p-q) = \frac{1}{2\pi} \text{ Pv.}\int_{-\Lambda}^{\Lambda} dq_1 \tilde{f}_0(q_1) \text{ Pv.}\int_{-\Lambda}^{\Lambda} dq_2 \tilde{f}_0(q_2) u(p - q_1 - q_2)~, 
\end{align}
$$
and Equation (39) is 
$$
\begin{align}
\int_{-2\Lambda}^{2\Lambda} G(q) u(p-q) =&~  - \frac{2\pi^2}{(2\pi) g^2} \lim_{\epsilon_1 \to 0} \lim_{\epsilon_2 \to 0} \int_{\epsilon_1 < |q_1| < \Lambda} dq_1 \text{csch}(\pi q_1/m) \times \cr
 & \qquad \qquad \qquad \qquad  \times \int_{\epsilon_2 < |q_2| < \Lambda} dq_2  \text{csch}(\pi q_2/m) u(p - q_1 - q_2)~. \qquad
\end{align}
$$

And you wrote

>Note in going from (38) to (39), we assumed it was valid to commute the operations of taking the $\epsilon_2 \to 0$ limit (implicit in the definition of the principal value integral) with doing the integral over $q_1$.  When we do this and then change variables in the integral below, we are effectively changing the test function that $\text{csch}(\pi q_2/m)$ is integrated against from $u(p-q_1 - q_2)$ to $u(p-q) \text{csch}(\pi (q-q_2)/m)$.  This could be problematic when $q \to 0$ since in that case the new test function is not smooth at the point where the principal value prescription is needed.  On the other hand, we do not expect any problems with this for $q$ away from zero.  The example we discussed in the previous appendix illustrates that point.

I agree with it in general but I have some doubts about interchanging the order of 
- taking $\epsilon_{2}\to 0$ limit and 
- the integral over $q_{1}$.

I noticed that your label for one of the equations is Fubini, does it mean that you used Fubini's theorem in interchanging the order of integrals? To adopt Fubini's theorem, we must treat $\text{csch}\left( \frac{\pi q}{m} \right)$ as a normal function instead of distribution, but when treated as a functions, it is not Lebesgue integrable on $(-\infty,0)\cup(0,\infty)$ since
$$
\int_{0}^{a} \text{csch} x \, dx = \ln \left\lvert \tanh\left( \frac{a}{2} \right) \right\rvert - \ln \left\lvert \tanh\left( \frac{0}{2} \right) \right\rvert = \infty,
$$
while a function $f$ is Lebesgue integrable if and only if $\int f \, dx<\infty$. However, Fubini's theorem only applies to $\mu$-finite (which is satisfied here since we are integrating over $\mathbb{R}$), Lebesgue integrable functions, thus here we can't use Fubini's theorem to argue that it is legit to interchange the order of integrals.

Of course if you didn't mean to use Fubini's theorem here then please ignore what I said above.

- - -

If $\text{csch}(x)$ is regarded as a tempered distribution, I am not sure why we should assume it is legit to interchange the orders. In Eq.(39) is well defined to integrate over $q_{2}$ then $q_{1}$ since the integral over $q_{2}$ gives $\langle \text{csch}(\pi q_{2} / m), u(p-q_{1}-q_{2}) \rangle$, where $\langle T_{x},f(x) \rangle$ denotes the distribution $T_{x}$ acting on $f(x)$, which is a Schwarz function, then integrating over $q_{1}$ is just 
$$
\langle \text{csch}(\pi q_{1} / m), \text{ some Schwarz function} \rangle 
$$
where the Schwarz function is $\langle \text{csch}(\pi q_{2} / m), u(p-q_{1}-q_{2}) \rangle$. It is well defined. However, if we interchange the order, then we run into the singularity problem you described (and solved later) in you note...

I've put together a note on basic measure theory [here](http://www.mathlimbo.net/2022/10/13/Basic-Measure-Theory-Part-II/), there is a section on Fubini's theorem if you are interested. 