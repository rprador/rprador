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

If the coefficients $a$ and $b$ are constants or functions of x, we call this a **linear** differential equation. Otherwise, it is **nonlinear**. All of the previous examples above, except the fourth one, are linear. Differential equations that include products of derivatives or functions that are not polynomials (trigonometric, exponential, etc.) are nonlinear. Additionally, if $b=0$, the equation is **homogenous**; otherwise, it is **inhomogenous**.

## Solving First-Order ODEs

### Separation of Variables

If a first-order ODE can be written in the following form:

$$ \begin{equation} \frac{dy}{dx} = -\frac{P(x)}{Q(y)} \,, \end{equation}  $$

we call it a **seperable** equation as it can be split into parts of a single variable. By multiplying the differentials and rearranging, (1) becomes

$$ \begin{equation} P(x)dx + Q(y)dy = 0 \,. \end{equation} $$

Note how each term is either a function of $x$ or $y$ but not both. Integrating both sides (indefinite integral) will lead to the solution to the ODE given by (1), up to an integration constant.

### Exact ODES and Integrating Factors

Seperation of variables only works if $P=P(x)$ and $Q=Q(y)$. However, a more general case is when they are both functions of $x$ and $y$. We then have the differential equation

$$ \begin{equation} P(x,y)dx + Q(x,y)dy = 0 \,. \end{equation} $$

If the following relation holds:

$$ \frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x} \,, $$

then we call (3) an **exact** differential equation. More specfically, if the above relation holds, then there exists some function $F(x,y)$ that if we take the differential of, $dF$, then

$$ \begin{equation} \frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x} \iff P = \frac{\partial F}{\partial x} , Q=\frac{\partial F}{\partial y} \longrightarrow Pdx + Qdy = dF \,.  \end{equation} $$

Therefore, we can obtain the function $F(x,y)$ through straight-forward integration of (4):

$$ \begin{equation} F(x,y) = \int_{x_0}^{x} P(x,y)dx + \int_{y_0}^{y} Q(x_0 ,y)dy = \text{constant} \,, \end{equation} $$

where $(x_0 , y_0)$ come from initial conditions.

So what happens if the ODE is not exact? Sometimes, it is possible to multiply by another function such that the product is exact. The function we need is called an **integrating factor**. Let's derive the expression for the integrating factor $\mu$. Suppose we have the nonexact, first-order linear ODE

$$ \begin{equation} \frac{dy}{dx} + p(x)y = q(x) \end{equation} \,. $$

Multiplying both sides by the integrating factor $\mu(x)$:

$$ \begin{equation} \mu(x)\frac{dy}{dx} + \mu(x)p(x)y = \mu(x)q(x) \end{equation} $$

As the purpose of the integrating factor is to convert this ODE into an exact one, we note that the left-hand side is given by the derivative using the product rule:

$$ \begin{equation} \frac{d}{dx}\left[ \mu(x)y \right] = \mu(x)\frac{dy}{dx} + \mu(x)p(x)y \,,  \end{equation} $$

or 

$$ \frac{d\mu}{dx}y + \mu\frac{dy}{dx} = \mu(x)\frac{dy}{dx} + \mu(x)p(x)y \,. $$

Subtracting both sides by $ \mu(x)\frac{dy}{dx}$ and dividing through by $y$, we get

$$ \frac{d\mu}{dx} = \mu(x)p(x) $$

This is now a separable equation! Therefore, we can multiply terms over and integrate to get

$$ \begin{equation} \mu(x) =  e^{\int^{x}p(x')dx' } \end{equation} $$

A word on the notation for the integrating factor: although the integration is technically definite, we exclude the lower limit as the results from it yield a constant that does not affect our end results. In effect, that constant from evaluating the lower limit can be set equal to 0. Thus, the notation $\int^{x}$ means to evaluate the definite integral at $x$ only, do not include an integration constant!

Now that we know what the integrating factor is given by (9), we use the result of (8) and plug into (7) to get

$$ \frac{d}{dx}\left[ \mu(x)y \right] = \mu(x)q(x) \,. $$

Integrating, we get the solution:

$$ \begin{equation} y(x) = \frac{1}{\mu(x)} \left[ \int^{x} \mu(x)q(x)dx + C \right] = \frac{1}{\mu(x)}\int^{x} \mu(x)q(x)dx + \frac{C}{\mu(x)} \,, \end{equation} $$

where $C$ is a constant. To get the constant, we would need to supply an initial condition $(x_0, y_0)$.

Example. $\frac{dI}{dt} + \frac{R}{L}I = \frac{V_0}{L}$, where $I=I(t)$ and $L,R, V_0$ are constants. The integrating factor is

$$ \mu(t) = e^{\int^{t}\frac{R}{L}dt'} = e^{\frac{R}{L}t} \,. $$

Then,

$$ I(t) = \frac{1}{\mu(t)}\int^{t} \mu(t)q(t)dx + \frac{C}{\mu(t)} = e^{-\frac{R}{L}t} \int^{t} e^{\frac{R}{L}t'} \frac{V_0}{L} dt' + Ce^{\frac{R}{L}t} \,. $$

Simplifying,

$$ I(t) = \frac{V_0}{R} + Ce^{\frac{R}{L}t} ]\,. $$

If we have the initial condition $I(0)=0$, then $C=-V_0/R$, thus

$$ I(t) = \frac{V_0}{R}\left( 1- e^{-Rt/L} \right) \,. $$

### Picard's Method - Iterative Method

Suppose we have a first-order ODE of the form

$$ \begin{equation} y'(x) = f(x,y) \end{equation}  \,, $$

with the initial conditions ($x_0, y_0$). Suppose $y$ and $y'$ are continuous when $\|x\| \leq a $ and $\|y\| \leq b$, for some constants $a,b$. If we integrate both sides, we obtain

$$ y - y_0 = \int_{x_0}^{x} f(x', y)dx' $$

The way Picard's method works is that we define a sequence of solutions ${y_0, y_1, y_2, \dots, y_n}$ that approaches the real solution $y$ as $n \rightarrow \infty$. By iteratively computing the integrals:

$$ \begin{align*} y_1 &= y_0 + \int_{x_0}^{x} f(x', y_0)dx' \\ 
y_2 &= y_0 + \int_{x_0}^{x} f(x', y_1)dx' \\
 y_3 &= y_0 + \int_{x_0}^{x} f(x', y_2)dx' \\
&\vdots \\
 y_n &= y_0 + \int_{x_0}^{x} f(x', y_{n-1})dx' \\\end{align*} $$ 

we can approach the real solution. If no initial condition is given, then we would have to "guess" one as a starting value for ($x_0, y_0$).

