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

where $\alpha\_1, \alpha\_2, \beta\_1, \beta\_2$ are constants. In some texts, the coefficient $w(x)$ is called the ***weight function*** and is notated sometimes as $r(x)$. If the coefficients of (1)-(3) are real and continuous everywhere (including at the end points), and $p>0$ and $w>0$, then we call this a **regular** Sturm-Liouville eigenvalue problem.

The following theorems (stated without proof) hold for the regular Sturm-Liouville eigenvalue problem.

- All the eigenvalues $\lambda$ are real.

- There exists an infinite number of eigenvalues that are ordered by magnitude:

$$ \lambda_{1} < \lambda_{2} < \dots < \lambda_{n} < \lambda_{n+1} < \dots $$

- For each eigenvalue there is a corresponding eigenfunction $\phi_{n}$ that is unique to within a multiplicative factor and that has $n-1$ zeros on the interval $a<x<b$.

- The eigenfunctions form a complete set, that is, any piecewise smooth function $f(x)$ can be represented by a generalized Fourier series of $\phi_{n}$:

$$ f(x) \approx \sum_{n=1}^{\infty} a_{n}\phi_{n}(x) \,, $$

which converges to $\[f(x^{+} + f(x^{-})\]/2$. The coefficients $a_{n}$ are found through application of orthogonality of the eigenfunctions:

$$ a_{m} = \frac{\int_{a}^{b}f(x)\phi_{m}(x)w(x)dx}{\int_{a}^{b}\phi_{m}^{2}(x)w(x)dx} $$

- The eigenfunctions are orthogonal to each other relative to the weight function $w(x)$:

$$ \int_{a}^{b} \phi_{n}(x)\phi_{m}(x)w(x)dx = 0 \quad \text{if } n \neq m $$

- Any eigenvalue can be related to its eigenfunction by the **Rayleigh quotient**:

$$ \lambda = \frac{-p\phi\frac{d\phi}{dx}|_{a}^{b} + \int_{a}^{b} \left[ p \left( \frac{d\phi}{dx} \right)^{2} - q\phi^{2}\right]dx}{\int_{a}^{b}\phi^{2}w(x)dx} \,, $$

where the boundary conditions can be used to simplify this expression.
