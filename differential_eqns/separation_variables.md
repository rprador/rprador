---
mathjax: true
title: Separation of Variables
---
{% include navigation.html %}
{% include mathjax.html %}

# Separation of Variables

Separation of variables is one of the most useful methods to try at first when solving poth PDes and ODes. The basic idea is to split the solution into functions of a single variable, like so

$$ u(x,t) = X(x)T(t) ,. $$

For the linear PDes solved with this method, we can employ a useful theorem.

**Theorem 1**. Given a linear, homogenous or nonhomogenous PDE, if $u_j$ (where $j=1,\dots, n$) are solutions to the same linear PDE, then another solution is given by any linear combination of these individual solutions:

$$ u = \sum_{j=1}^{n} c_{j}u_{j} \,, $$

where $c_j$ are constant coefficients. The solution $u$ also satisfies the (linear+homogenous) boundary conditions and initial conditions that $u_j$ do.

Suppose we are given a simple yet common PDE to solve

$$ \frac{\partial u}{\partial t} = c\frac{\partial u^2}{\partial x^2} $$

Let $u(x,t) = X(x)T(t)$. Then the PDE becomes

$$ XT' = cTX'' \longrightarrow \frac{X''}{X} = \frac{T'}{cT} \,, $$

where $T' = dT/dt$ and $X' = dX/dx$. Since both sides of the equation are derivatives, the only way for the equation to hold is if both sides are equal to a constant, say $\alpha$:

$$ \frac{X''}{X} = \frac{T'}{cT} = \alpha \,, $$

which leads to two separate ODEs that can be solved

$$ X'' - \alpha X = 0  \quad \text{and} \quad T' - \alpha cT = 0  \,. $$

The solution will depend on whether $\alpha$ is positive, negative, or zero, as well as on the boundary and initial conditions. When a physical argument cannot be made to determine $\alpha$, the safest bet is to go through all three cases and see which on satisfies the conditions.

## Nonhomogenous Problems

The above theorem states that a solution can be found from a linear combination of individual solutions for linear, homogenous conditions. However, what do we do if the problem is inherently nonhomogenous? In similar thought to separation of variables, we can split the problem into separate parts. Suppose we are dealing with a heat conduction problem through a rod

$$ \begin{align*} \frac{\partial U}{\partial t} &= k \frac{\partial^2 U}{\partial x^2}, \quad 0<x<L,\quad t>0 \\ U(0, t) &= U_0, \quad t>0 \\ U(L, t)&=U_L, \quad t>0 \\ U(x,0) &= f(x),\quad 0<x<L   \end{align*} $$

The boundary conditions are nonhomogenous, so we can try to split up the problem into a homogenous and nonhomogenous parts:

$$ U(x,t) = V(x,t) + \psi(x) \,, $$

where $V(x,t)$ is the transient solution that depends on time and $\psi(x)$ is the steady state solution that depends only on $x$. Substituting this split solution into the PDE,

$$ \frac{\partial V}{\partial t} = k\left( \frac{\partial^2 V}{\partial x^2} + \frac{d^2 \psi}{d x^2} \right) $$

The steady state problem is thus given by

$$ \begin{align*} 0 &= k\frac{d^2 \psi}{d x^2} \\ \psi(0)&=U_0 \\ \psi(L)&=U_L \end{align*} $$

The general solution is 

$$ \psi(x) = Ax + B \,, $$

which, after applying the boundary conditions, becomes

$$ \psi(x) = U_0 + \frac{U_L - U_0}{L}x $$

Going back to the original PDE, we know from the steady state problem that $\psi(x)$ vanishes at its second derivative. Hence,

$$ \frac{\partial V}{\partial t} = k \frac{\partial^2 V}{\partial x^2} $$

The transient boundary conditions come from the original ones and using the split solution, but now in terms of $V$: $V(x,t) = U(x,t) - \psi(x)$. Hence,

$$ \begin{align*} V(0,t) &= U(0,t) - \psi(0) = U_0 - U_0 = 0 \\ V(L,t) &= U(L,t) - \psi(L) = U_L - U_L = 0 \end{align*} $$

So we have $V(0,t)=0$ and $V(L,t)=0$ as our boundary conditions for the transient solution. The initial condition is derived similarly,

$$ V(x,0) = U(x,0) - \psi(x) = f(x) - U_0 - \frac{U_L - U_0}{L} \,. $$

What remains now is to simplify the transient problem using separation of variables: $V(x,t) = X(x)T(t)$. Applying this to the transient PDE,

$$ XT' = kTX'' \longrightarrow \frac{X''}{X} = \frac{T'}{kT} = \alpha $$

In this case, a physically acceptable problem comes from having $\alpha$ be negative. Hence, $\alpha = -\lambda^2$, leading to

$$ X'' + \lambda^2 X = 0 \,, $$

with boundary conditions $V(0,t)=0 \rightarrow X(0)=0$ and $V(L,t)=0 \rightarrow X(L)=0$, and

$$ T' + k\lambda^2 T = 0 \,, $$

with initial condition left arbitrary (original gives no new information).

We can now solve these two ODEs. For $X$ we have a linear 2nd-order ODE. The characteristic equation yields a complex solution ($r = 0 \pm i\lambda$), so the general solution is given by

$$ X(x) = A\sin(\lambda x) + B\cos(\lambda x) \,. $$

Using the boundary conditions lead to

$$ \begin{align*} X(0) &= 0 \longrightarrow B=0 \\ X(L) &= 0 \longrightarrow \lambda = \frac{n\pi}{L} (n=1,2,\dots)  \end{align*} $$

Thus,

$$ X(x) = A \sin\left(\frac{n\pi}{L}x\right) $$

For $T$, we have a 1st-order linear ODE that happens to be a separable equation. Thus, the general solution is (keeping mind our result for $\lambda$) 

$$ T(t) = Ce^{-n^2 \pi^2 kt/L^2} \,. $$

The complete transient solution is therefore

$$ V(x,t) = be^{-n^2 \pi^2 kt/L^2}\sin\left(\frac{n\pi}{L}x $$

where we combined the constants $b=BC$.
