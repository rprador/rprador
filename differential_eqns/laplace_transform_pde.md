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

where $s$ is a complex variable (sometimes called the **frequency parameter**) and $F(s)$ is called the **image function** or **Laplace transform** of $f(t)$. A Laplace transform exists if $f(t)$ is piece-wise continuous on every finite interval $0 \leq t \leq T$, $t^{n}\|f(t)\|$ is bounded near $t=0$ for some $n<1$, and $e^{-s\_{0}t}\|f(t)\|$ is bounded for a large $t$ for some value of $s_{0}$.

This transformation can also be reversed, in which case we call the **original function** $f(t)$ the **inverse Laplace transform** of $F(s)$, which can be calculated as

$$ \begin{equation} f(t) = \mathcal{L}^{-1}\{F(s)\}(t) = \frac{1}{2\pi i} \lim_{T\rightarrow\infty} \int_{c-iT}^{c+iT} e^{st}F(s)ds \end{equation} \,.$$

This is known as **Mellin's integral**. 

Although we can perform the integration, a Laplace transform table is much more useful when doing problems, such as [this one from NIST](https://dlmf.nist.gov/1.14#T4).

## A Few Properties of the Laplace Transform

- _Linearity (linear operator)_. 

$$ \mathcal{L}\{ af(t)+bg(t) \}(s) = aF(s)+bG(s) $$

Note: it is implied here that the multiplicative constants $a$ and $b$ can be taken outside the operator,

$$ \mathcal{L}\{ af(t) \} = a \mathcal{L}\{ f(t) \} = aF(s) $$

- _Shifting property by frequency_. 

$$ \begin{align*}\mathcal{L} \{ e^{at}f(t) \}(s) &= F(s-a) \\ \mathcal{L}^{-1} \{ F(s-a) \}(t) &= e^{at}f(t) \end{align*} $$

- _Shifting property by time_. 

$$ \begin{align*} \mathcal{L} \{ f(t)H(t-a) \}(s) &= e^{-as}\mathcal{L}\{ f(t+a) \}(s) \\ \mathcal{L}^{-1} \{ e^{-as}F(s) \}(t) &= f(t-a)H(t-a) \end{align*} $$

where $H(t-a)$ is the Heaviside step function. $H(t-a)$ is equal to 0 when $t<a$ and 1 when $t>a$.

- _Time scaling_.

$$ \mathcal{L}\{ f(at)\}(s) = \frac{1}{a}F(\frac{s}{a}) $$

- _First derivatives_.

$$ \mathcal{L}\{ \frac{d}{dt}f(t) \}(s) = sF(s) - f(t=0^{+}) $$

- _General derivative_.

$$ \mathcal{L}\{ \frac{d^{(n)}}{dt^{(n)}}f(t) \}(s) = s^{n}F(s) - \sum_{i=1}^{n-1}s^{n-i}f(t=0^{+})  $$

