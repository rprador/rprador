---
mathjax: true
title: Sturm-Liouville Equations
---
{% include navigation.html %}
{% include mathjax.html %}

# Sturm-Liouville Equations

When applying separation of variables to second-order linear PDEs, very often we come across differential equations that reduce to eigenvalue problems. Such eigenvalue problems look something like this:

$$ \frac{d^2 \phi}{dx^2} + \lambda \phi(x) = 0 \,, $$

where $\phi=\phi(x)$ comes from separation of variables and $\lambda$ is a constant from separation of variables. Of course, there are boundary conditions given along side this.

In general, a **Sturm-Liouville equation** has the form:

$$ \begin{equation} \frac{d}{dx}\left[ p(x) \frac{dy}{dx} \right] + [\lambda w(x) - q(x)]y = 0 \end{equation} \,, $$

with the following boundary conditions over the interval $a<x<b$:

$$ \begin{align}  \alpha_1 y(a) + \alpha_2 y'(a) &= 0 \\ \beta_1 y(b) + \beta_2 y'(b) &= 0 \end{align} $$

where $\alpha\_1, \alpha\_2, \beta\_1, \beta\_2$ are constants. In some texts, the coefficient $w(x)$ is called the ***weight function*** and is notated sometimes as $r(x)$.
