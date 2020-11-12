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

