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

$ X'' - \alpha X = 0 $ and $T' - \alpha cT = 0$.
