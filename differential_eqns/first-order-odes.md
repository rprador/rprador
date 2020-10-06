---
mathjax: true
title: First-Order Ordinary Differential Equations
---
{% include navigation.html %}
{% include mathjax.html %}

Given an ordinary (only total derivatives) differential equation, the **order** of the differential equation is given by the order of the highest derivative. For example,

$$ \begin{align*} y' + 2y &= 1 \quad & (\text{First-order}) \\
y' + y^2 &= 2 \quad & (\text{First-order}) \\
m\frac{d^2 r}{dx^2} &= F \quad & (\text{Second-order}) \\
\left( \frac{d^2 u}{dx^2} \right)^4 + \frac{du}{dx} &= 0 \quad & (\text{Second-order}) \\ \end{align*}$$

Note to be careful with confusing powers for order. The last example above is still second-order as its derivative is of order 2 -- the power of 4 does not count! Suppose we have a general $n$th-order ordinary differential equation of one variable:

$$ a_0 y + a_1 y' + a_2 y'' + a_3 y''' + \dots + a_{(n-1)}y^{(n-1)} + a_{n}y^{(n)} = b; $$

If the coefficients $a$ and $b$ are constants or functions of x, we call this a **linear** differential equation. Otherwise, we it is **nonlinear**. All of the previous examples above are linear. Differential equations that include products of derivatives or functions that are not polynomials (trigonometric, exponential, etc.) are nonlinear.  
