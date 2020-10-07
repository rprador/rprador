---
mathjax: true
title: First-Order Ordinary Differential Equations
---
{% include navigation.html %}
{% include mathjax.html %}

# First-Order Ordinary Differential Equations (ODEs)

Given an ordinary (only total derivatives) differential equation, the **order** of the differential equation is given by the order of the highest derivative. For example,

$$ \begin{align*} y' + 2y &= 1 \quad & (\text{First-order}) \\
y' + y^2 &= 2 \quad & (\text{First-order}) \\
m\frac{d^2 r}{dx^2} &= F \quad & (\text{Second-order}) \\
\left( \frac{d^2 u}{dx^2} \right)^4 + \frac{du}{dx} &= 0 \quad & (\text{Second-order}) \end{align*}$$

Note to be careful with confusing powers for order. The last example above is still second-order as its derivative is of order 2 -- the power of 4 does not count! 

Suppose we have a general $n$th-order ordinary differential equation of one variable:

$$ a_0 y + a_1 y' + a_2 y'' + a_3 y''' + \dots + a_{(n-1)}y^{(n-1)} + a_{n}y^{(n)} = b; $$

If the coefficients $a$ and $b$ are constants or functions of x, we call this a **linear** differential equation. Otherwise, it is **nonlinear**. All of the previous examples above, except the fourth one, are linear. Differential equations that include products of derivatives or functions that are not polynomials (trigonometric, exponential, etc.) are nonlinear. Additionally, if $b=0$, the equation is **homogenous**; otherwise, it is **nonhomogenous**.

## Solving First-Order ODEs

### Separation of Variables

If a first-order ODE can be written in the following form:

$$ \begin{equation} \frac{dy}{dx} = -\frac{P(x)}{Q(y)} \,, \end{equation}  $$

we call it a **seperable** equation as it can be split into parts of a single variable. By multiplying the differentials and rearranging, (1) becomes

$$ \begin{equation} P(x)dx + Q(y)dy = 0 \,. \end{equation} $$

Note how each term is either a function of $x$ or $y$ but not both. Integrating both sides (indefinite integral) will lead to the solution to the ODE given by (1), up to an integration constant.

### Integrating Factors

Seperation of variables only works if $P=P(x)$ and $Q=Q(y)$. However, a more general case is when they are both functions of $x$ and $y$. We then have the differential equation

$$ \begin{equation} P(x,y)dx + Q(x,y)dy = 0 \,. \end{equation} $$

If the following relation holds:

$$ \frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x} \,, $$

then we call (3) an **exact** differential equation. More specfically, if the above relation holds, then there exists some function $F(x,y)$ that if we take the differential of, $dF$, then

$$ \begin{equation} \frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x} \iff P = \frac{\partial F}{\partial x} , Q=\frac{\partial F}{\partial y} \longrightarrow Pdx + Qdy = dF \,.  \end{equation} $$

Therefore, we can obtain the function $F(x,y)$ through straight-forward integration of (4):

$$ \begin{equation} F(x,y) = \int_{x_0}^{x} P(x,y)dx + \int_{y_0}^{y} Q(x_0 ,y)dy = \text{constant} \,, \end{equation} $$

where $(x_0 , y_0)$ come from initial conditions.

So what happens if the ODE is not exact? Sometimes, it is possible to multiply by another function such that the product is exact. The function we need is called an integrating factor.
