---
mathjax: true
title: Laplace Transforms
---
{% include navigation.html %}
{% include mathjax.html %}

# The Laplace Transform

Transformations are useful in solving differential equations as they simplify them into algebraic problems. In practice, it is common to use Fourier transforms for spatial variables and Laplace transforms for time. As a rule of thumb, the Laplace Transform is used on nonfinite variables that vary from $0$ to $\infty$, while Fourier transforms are used on finite variables.

Given a function $f(t)$, the Laplace transform of $f(t)$ is denoted by $F(s) = \mathcal{L}\{f(t)\}(s)$ and defined as

$$ \begin{equation} F(s) = \mathcal{L}\{f(t)\}(s) = \int_{0}^{\infty} e^{-st}f(t)dt \end{equation} \,, $$

where $s$ is a complex variable and $F(s)$ is called the **image function** or **Laplace transform** of $f(t)$. This transformation can also be reversed, in which case we call the **original function** $f(t)$ the **inverse Laplace transform** of $F(s)$, which can be calculated as

$$ \begin{equation} f(t) = \mathcal{L}^{-1}\{F(s)\}(t) = \frac{1}{2\pi i} \lim_{T\rightarrow\infty} \int_{c-iT}^{c+iT} e^{st}F(s)ds \end{equation} \,.$$

This is known as **Mellin's integral**. 

Although we can perform the integration, a Laplace transform table is much more useful when doing problems, such as [this one from NIST](https://dlmf.nist.gov/1.14#T4).
