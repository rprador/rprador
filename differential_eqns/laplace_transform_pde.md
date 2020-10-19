---
mathjax: true
title: Laplace Transforms
---
{% include navigation.html %}
{% include mathjax.html %}

# The Laplace Transform

Transformations are useful in solving differential equations as they simplify them into algebraic problems. In practice, it is common to use Fourier transforms for spatial variables and Laplace transforms for time. As a rule of thumb, the Laplace Transform is used on nonfinite variables that vary from $0$ to $\infty$, while Fourier transforms are used on finite variables.

Given a function $F(t)$, the Laplace transform of $F(t)$ is denoted by $f(s) = \mathcal{L}{F(t)}(s)$ and defined as

$$ \begin{equation} f(s) = \mathcal{L}{F(t)}(s) = \int_{0}^{\infty} e^{-st}F(t)dt \end{equation} \,, $$

where $s$ is a complex variable and $f(s)$ is called the _image_ of $F(t)$.
