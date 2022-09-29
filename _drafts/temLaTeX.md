Discussion note

—

### Failure of $\widetilde{f}_{0}$ at finite $\Lambda$

In the note it is mentioned that, from Eq. (38) to Eq. (39),

> we assumed it was valid to commute the operations of taking the $\epsilon_2 \to 0$ limit (implicit in the definition of the principal value integral) with doing the integral over $q_1$.

For your convenience I copy the equations here, Eq. (38) reads 
$$
\begin{align}
\int_{-2\Lambda}^{2\Lambda} G(q) u(p-q) = \frac{1}{2\pi} \text{ Pv}\int_{-\Lambda}^{\Lambda} dq_1 \tilde{f}_0(q_1) \text{ Pv}\int_{-\Lambda}^{\Lambda} dq_2 \tilde{f}_0(q_2) u(p - q_1 - q_2)~, \\
\end{align}
$$
and Equation (39) is 
$$
\begin{align}
\int_{-2\Lambda}^{2\Lambda} G(q) u(p-q) =&~  - \frac{2\pi^2}{(2\pi) g^2} \lim_{\epsilon_1 \to 0} \lim_{\epsilon_2 \to 0} \int_{\epsilon_1 < |q_1| < \Lambda} dq_1 \text{csch}(\pi q_1/m) \times \cr
 & \qquad \qquad \qquad \qquad  \times \int_{\epsilon_2 < |q_2| < \Lambda} dq_2  \text{csch}(\pi q_2/m) u(p - q_1 - q_2)~. \qquad
\end{align}
$$

However, why would we assume that? It's just writing down the explicit definition of $\widetilde{f}_{0}$, no?

I agree with what you said here

>Note in going from \eqref{Gdefone} to \eqref{Fubini}, we assumed it was valid to commute the operations of taking the $\epsilon_2 \to 0$ limit (implicit in the definition of the principal value integral) with doing the integral over $q_1$.  When we do this and then change variables in the integral below, we are effectively changing the test function that $\text{csch}(\pi q_2/m)$ is integrated against from $u(p-q_1 - q_2)$ to $u(p-q) \text{csch}(\pi (q-q_2)/m)$.  This could be problematic when $q \to 0$ since in that case the new test function is not smooth at the point where the principal value prescription is needed.  On the other hand, we do not expect any problems with this for $q$ away from zero.  The example we discussed in the previous appendix illustrates that point.

