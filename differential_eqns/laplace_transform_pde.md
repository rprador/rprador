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

- _First derivative_.

$$ \mathcal{L}\left\{ \frac{d}{dt}f(t) \right\}(s) = sF(s) - f(t=0^{+}) $$

- _Second derivative_.

$$ \mathcal{L}\left\{ \frac{d^{2}}{dt^{2}}f(t) \right\}(s) = s^{2}F(s)-sf(t=0)-\frac{df}{dt}|_{t=0} $$

- _General derivative_.

$$ \mathcal{L}\left\{ \frac{d^{(n)}}{dt^{(n)}}f(t) \right\}(s) = s^{n}F(s) - \sum_{i=1}^{n-1}s^{n-i}f(t=0^{+})  $$

## Use in ODEs

To see how Laplace transforms are used, consider the following ODE for the function $y=y(t)$:

$$ y'' - 2y' + y = 2te^{t} \,, $$

subject to the boundary conditions $y(0)=y'(0)=0$. Taking the Laplace transform of both sides, we get

$$ \mathcal{L}\{ y'' \} - 2\mathcal{L}\{ y' \} + \mathcal{L}\{ y \} = 2 \mathcal{L}\{ te^{t} \} \,. $$

Denoting the image function as $Y=Y(s)$, and using the following transforms:

$$ \begin{align*} \mathcal{L}\{ y'' \} &= s^{2}Y(s)-sy(0) - y'(0) \\ \mathcal{L}\{ y' \} &= sY(s) - y(0) \\ \mathcal{L}\{ te^{-at} \} &= \frac{1}{(s+a)^{2}} \end{align*} \,, $$

we get

$$ s^{2}Y - sy(0) - y'(0) -2(sY - y(0)) + Y = \frac{2}{(s-1)^{2}} \,. $$

Note how important it is to have the boundary conditions! Without them, we cannot move further in the problem. Using $y(0)=y'(0)=0$, the above equation reduces to

$$ s^{2}Y - 2sY + Y = \frac{2}{(s-1)^{2}} \,. $$

Solving for the image function $Y(s)$, 

$$ Y(s) = \frac{2}{(s-1)^{4}} $$

Finally, we take the inverse Laplace transform to convert back to $y(t)$. Using the inverse Laplace transform

$$ \mathcal{L}^{-1} \left\{ \frac{1}{(s+a)^{n}} \right\} = \frac{t^{n-1}e^{-at}}{(n-1)!}, \quad (n=1,2,3,\dots) \,, $$

the solution to the ODE is

$$ \begin{align*} y(t) &= \mathcal{L}^{-1} \{ Y(s) \} \\ &= \mathcal{L}^{-1} \left\{ \frac{2}{(s-1)^{4}} \right\} \\ &= \frac{t^{3}e^{t}}{3} \end{align*}$$

## Partial Fractions

Oftentimes, especially when finding inverse Laplace transforms, we will have the expression $q(s)/p(s)$, where $q$ and $p$ are both polynomials. One way to deal with this is to factor $p(s)$ into its roots such that 

$$ \frac{q(s)}{p(s)} = \frac{c_1}{s-s_1} + \frac{c_2}{s-s_2} + \dots + \frac{c_n}{s-s_n} \,, $$

where $c\_i$ are coefficients to be determined and the roots of $p(s)$ are called **simple poles** of $q/p$. Normally, as would have been taught in a calculus course or before, the way to get the coefficients is to multiply both sides of the expression above by the $(s-s\_i)$, and choose a value for $s\_i$ such that all the other terms except for one go to zero. Afterwards, a comparison of coefficients or algebra is done. However, a much quicker way is to use a limit instead:

$$ c_i = \lim_{s\rightarrows_i} \frac{(s-s_i)q(s)}{p(s)} \,. $$

By taking this limit, all terms except for $c\_i$ will vanish and the result of the limit will determine the coefficient. To get all of the coefficients, we simply apply this limit for all of the simple poles of $q/p$.

## Convolution Theorem

The convolution theorem is used to obtain the inverse Laplace transform of a product of functions. Stated:

$$ \mathcal{L}^{-1} \{ F(s)G(s) \}(t) = g * f = \int_{0}^{t} g(\overbar{t})f(t-\overbar{t})d\overbar{t} \,, $$

where $g\*f$ is called the **convolution** of $g(t)=\mathcal{L}^{-1} \{ G(s) \} $ and $f(t)=\mathcal{L}^{-1} \{ F(s) \}$.
