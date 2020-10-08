---
mathjax: true
title: Second-Order Ordinary Differential Equations
---
{% include navigation.html %}
{% include mathjax.html %}

# Second-Order ODEs

Here, we look at differential equations of the form

$$ \begin{equation} y'' + p(x)y' + q(x)y = g(x) \,. \end{equation} $$

Many problems in physics and engineering involve these types of ODEs.

## Homogenous Linear Second-Order ODEs With Constant Coefficients

Consider the following ODE:

$$ \begin{equation} ay'' + by' + cy = 0 \end{equation} \,, $$

where $a,b,c$ are constants. The trick here is to assume that the solution takes on the form $y=e^{rx}$, $r$ is a constant, such that the general solution is given by

$$ \begin{equation} y = C_1 e^{r_1 t} + C_2 e^{r_2 t} \end{equation} $$

Doing so, (2) becomes

$$  \begin{align*} 0 &= ar^{2}e^{rt} + bre^{rt} + ce^{rt} \\ 
&=e^{rt}(ar^2 + br + c) \\  &= ar^2 + br + c \end{align*} \,.  $$

The end result:

$$ \begin{equation} 0=ar^2 br + c \end{equation} \,, $$

is known as the **characteristic equation**. Solving this quadratic equation will give the values for $r_1$ and $r_2$. Based on these roots, different methods exists to obtain

### Complex roots for $r_1, r_2$

If the characteristic equation yields complex roots, then we have to make sure to use Euler's formula:

$$ e^{i\theta} = cos\theta + i sin\theta \,, $$

to convert our solutions. Therefore, if the roots are of the complex form $r=\lambda \pm i\mu$, then the solutions are given by

$$ \begin{align} y_1 &= C_1 e^{\lambda x} cos(\mu x) \\ y_2 &= C_2 e^{\lambda x}sin(\mu x) \end{align} $$
