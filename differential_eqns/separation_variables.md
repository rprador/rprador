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

where $c_j$ are constant coefficients. The solution $u$ also satisfies the (linear+homogenous) boundary conditions and initial conditions that $u_j$ do. Known as the superposition principle.

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

The above theorem states that a solution can be found from a linear combination of individual solutions for linear, homogenous conditions. However, what do we do if the problem is inherently nonhomogenous? 

### Method of Splitting for Time-independent Inhomogenieties

In similar thought to separation of variables, we can split the problem into separate parts. Suppose we are dealing with a heat conduction problem through a rod

$$ \begin{align*} \frac{\partial U}{\partial t} &= k \frac{\partial^2 U}{\partial x^2}, \quad 0<x<L,\quad t>0 \\ U(0, t) &= U_0, \quad t>0 \\ U(L, t)&=U_L, \quad t>0 \\ U(x,0) &= f(x),\quad 0<x<L  \end{align*} $$

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

The transient solution(s) is therefore

$$ V_{n} (x,t) = b e^{-n^2 \pi^2 kt/L^2} \sin\left(\frac{n\pi}{L}x\right) $$

where we combined the constants $b=BC$. Invoking theorem 1 gives the complete transient solution

$$ V(x,t) = \sum_{n=1}^{\infty} b_n e^{-n^2 \pi^2 kt/L^2} \sin\left(\frac{n\pi}{L}x\right)  $$

Note that the superposition is done so that the initial condition can be satisfied. Using the initial condition,

$$ V(x,0) = f(x) - U_0 - \frac{U_L - U_0}{L} = \sum_{n=1}^{\infty} b \sin\left(\frac{n\pi}{L}x\right) $$

Here, we recognized this as a Fourier sine series. Thus, we are able to get the coefficients as

$$ b_n = \frac{2}{L} \int_{0}^{L}\left( f(x) - U_0 - \frac{U_L - U_0}{L} \right) \sin\left(\frac{n\pi}{L}x\right) dx $$

The solution to the heat conduction problem is, finally,

$$ U(x,t) = \sum_{n=1}^{\infty} b_n e^{-n^2 \pi^2 kt/L^2} \sin\left(\frac{n\pi}{L}x\right) + U_0 + \frac{U_L - U_0}{L}x $$

where we combine the steady state and transient solutions together.

### Variation of Constants for Time-dependent Inhomogeneities

This method works similar to variation of parameters for ODEs. Here is a quick summary of how this method is performed:

1) Solve the PDE as if it were homogenous, with homogenous boundary conditions and initial conditions. Let $X_n(x)$ be the eigenfunction determined from this step.

2) Convert the homogenous solution to one that varies on a time-depedent coefficient:

$$ \sum_n C_n X_n(x) T(t) \longrightarrow \sum_n d_n(t) X_n(x) $$

where $T(t)$ is the time-dependent solution from separation of variables and $d_n(t)$ are the now time-dependent coefficients of the eigenfunctions. This expression for the solution will be called the **eigenfunction expansion**.

3) Substitue the eigenfunction expansion into the original PDE. 

4) Obtain and solve the resulting ODEs for $d_n(t)$.

5) Use the initial conditions on the PDE to find any integration constants from the previous step.

To understand this process, let's look to an example. Consider the one-dimensional vibration problem of a taut string with a forcing function $F(x,t)=e^{-t}$:

$$ \begin{align*} \frac{\partial^2 y}{\partial t^2} &= c^2 \frac{\partial^2 y}{\partial x^2} + \frac{e^{-t}}{\rho}, \quad 0<x<L, \quad t>0 \\ y(0, t) &= 0, \quad t>0 \\ y(L,t) &= 0, \quad t>0 \\ y(x,0) &= f(x), \quad 0<x<L \\ \frac{\partial y}{\partial t} &= 0, \quad 0<x<L \end{align*} $$

The homogenous PDE is given by

$$ \frac{\partial^2 y}{\partial t^2} = c^2 \frac{\partial^2 y}{\partial x^2} \,. $$

Using separation of variables, we are lead to the following ODEs:

$$ \begin{align*}  X'' + \lambda^2 X &= 0 \\ X(0) &= 0 \\ X(L) &= 0 \end{align*} $$

where $\alpha = -\lambda^2$ are the eigenvalues chosen to obtain oscillatory solutions; and,

$$ \begin{align*} T'' + \lambda^2 c^2 T &= 0  \\ \left.\frac{\partial T}{\partial t}\right|_{t=0} = 0 \end{align*}$$

The general solutions to both ODEs are

$$ \begin{align*} X(x) &= A\sin(\lambda x) + B\cos(\lambda x) \\ T(t) &= C\sin(c\lambda t) + D\cos(c\lambda t)  \end{align*} $$

Applying the boundary conditions,

$$ \begin{align*} X(0)=0 &\rightarrow B=0 \\ X(L) = 0 &\rightarrow \lambda = \frac{n\pi}{L} \\ \left.\frac{\partial T}{\partial t}\right|_{t=0} = 0 &\rightarrow C=0 \end{align*} $$

Hence, the individual solutions are given by

$$ y_n(x,t) = X_n(x)T(t) = C_n\sin(\frac{n\pi}{L}x)\cos(\frac{cn\pi}{L}t) \,. $$

Using the superposition principle to satisfy the initial condition, we have

$$ y(x,t) = \sum_{n=1}^{\infty} y_n(x,t) = \sum_{n=1}^{\infty}C_n\sin(\frac{n\pi}{L}x)\cos(\frac{cn\pi}{L}t) \,. $$

We now swap to a time-dependent coefficient to achieve the eigenfunction expansion:

$$ \sum_{n=1}^{\infty}C_n\sin(\frac{n\pi}{L}x)\cos(\frac{cn\pi}{L}t) \longrightarrow \sum_{n=1}^{\infty}d_n(t) \sin(\frac{n\pi}{L}x) \,. $$

To see if this eigenfunction expansion works, substitute back into the PDE:

$$ \sum_{n=1}^{\infty} d''_n(t) \sin(\frac{n\pi}{L}x) = -c^2 \sum_{n=1}^{\infty}\frac{n^2 \pi^2}{L^2}d_n(t) \sin(\frac{n\pi}{L}x) + \frac{e^{-t}}{\rho} \,. $$

One additional modification is now made. We expand $e^{-t}/\rho$ as a Fourier sine series

$$ \frac{e^{-t}}{\rho} = \sum_{n=1}^{\infty} F_n \sin(\frac{n\pi}{L}x), \quad F_n(t) = \frac{2}{L}\int_{0}^{L}\frac{e^{-t}}{\rho}\sin(\frac{n\pi}{L}x)=\frac{2e^{-t}(1+(-1)^{n+1})}{n\pi\rho} \,. $$

Substituting this into the expanded PDE and reducing yields

$$ \sum_{n=1}^{\infty} \left[ d''_n(t) + \frac{n^2 \pi^2 c^2}{L^2}d_n(t) - \frac{2e^{-t}(1+(-1)^{n+1})}{n\pi\rho} \right] \sin(\frac{n\pi}{L}x) = 0 \,. $$

It follows that the coefficients must vanish as

$$d''_n(t) + \frac{n^2 \pi^2 c^2}{L^2}d_n(t) - \frac{2e^{-t}(1+(-1)^{n+1})}{n\pi\rho} = 0 \,. $$

This is a second-order nonhomogenous linear ODE for $d_n(t)$. The general solution is by variation of parameters:

$$ d_n(t) = b_n \cos(\frac{n\pi c}{L}t) + a_n \sin(\frac{n\pi c}{L}t) + \frac{2L^2 (1+(-1)^{n+1})}{n\pi\rho (L^2 + n^2 \pi^2 c^2)}e^{-t} \,. $$

The initial condition $d'\_n(0)=0$ gives

$$ a_n = \frac{2L^2 (1+(-1)^{n+1})}{n\pi\rho (L^2 + n^2 \pi^2 c^2)} \,. $$

Finally, the solution looks like

$$ y(x,t) = \sum_{n=1}^{\infty} \left[ b_n \cos(\frac{n\pi c}{L}t) + \frac{2L^2 (1+(-1)^{n+1})}{n\pi\rho (L^2 + n^2 \pi^2 c^2)} \left( n\pice^{-t} + L\sin(\frac{n\pi c}{L}t) \right) sin(\frac{n\pi}{L}x) \right]  \,, $$

with the coefficient given by the initial condition $y(x,0)=f(x)$ as:

$$ b_n = \frac{2}{L}\int_{0}^{L}f(x)\sin(\frac{n\pi}{L}x) - \frac{2L^2 (1+(-1)^{n+1})}{n\pi\rho (L^2 + n^2 \pi^2 c^2)} \,. $$


