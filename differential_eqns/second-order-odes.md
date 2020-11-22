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

## Second-Order Linear Homogenous ODEs With Constant Coefficients

Consider the following ODE:

$$ \begin{equation} ay'' + by' + cy = 0 \end{equation} \,, $$

where $a,b,c$ are constants. The trick here is to assume that the solution takes on the form $y=e^{rx}$, $r$ is a constant, such that the general solution is given by

$$ \begin{equation} y = C_1 e^{r_1 t} + C_2 e^{r_2 t} \end{equation} $$

Doing so, (2) becomes

$$  \begin{align*} 0 &= ar^{2}e^{rt} + bre^{rt} + ce^{rt} \\ 
&=e^{rt}(ar^2 + br + c) \\  &= ar^2 + br + c \end{align*} \,.  $$

The end result:

$$ \begin{equation} 0=ar^2 + br + c \end{equation} \,, $$

is known as the **characteristic equation**. Solving this quadratic equation will give the values for $r_1$ and $r_2$. Based on these roots, different methods exists to obtain the general solution.

### Complex roots for $r_1, r_2$

If the characteristic equation yields complex roots, then we have to make sure to use Euler's formula:

$$ e^{i\theta} = \cos\theta + i \sin\theta \,, $$

to convert our solutions. Therefore, if the roots are of the complex form $r=\lambda \pm i\mu$, then the solutions are given by

$$ \begin{align} y_1 &= C_1 e^{\lambda x} \cos(\mu x) \\ y_2 &= C_2 e^{\lambda x}\sin(\mu x) \end{align} $$

### Repeated roots for $r_1 = r_2$

If the characteristic equation yields repeated roots, then (through the method of reduction of order: see next section) the solution is given by 

$$ \begin{equation}  y = C_1e^{r_1 x} + C_2 xe^{r_1 x} \end{equation} $$

## General Second-Order Homogenous ODEs

For the second-order ODE

$$ y'' + p(x)y' + q(x)y = 0 \,, $$

suppose we already have a solution, $y_1 (x)$. We can fashion a second solution of the form

$$ \begin{equation} y_2 (x) = v(x)y_1(x) \,,  \end{equation} $$

where $v(x)$ is an arbitary function. The goal is to use this trial solution, find $v'(x)$, integrate it to get $v(x)$, and fully determine $y_2$. By plugging in $y_2$ into the original ODE, we end up with a first-order ODE, hence the name of the method **reduction of order**. The equation for $v(x)$ is given by

$$ \begin{equation} v(x) = \int^{x} \frac{1}{(y_1(s))^{2}} e^{-1\int^{s}p(t)dt}ds \end{equation} $$

Thus, we get the homogenous solution: $y_h = C_1 y_1 (x) + C_2 y_2 (x)$.

## General Second-Order Linear Inhomogenous ODEs

For an inhomogenous second-order linear ODES of the form:

$$ y'' + p(x)y' + q(x)y = g(x) \,, $$

the general solution is found by following three steps:

1. Find the **homogenous** (or **complementary**) solution $y_h$ to $$ y'' + p(x)y' + q(x) = 0$$.
2. Determine the **particular** solution $y_p$ to the inhomogenous ODE using any method (see below).
3. Take their sum: $y = C_1 y_h (x) + C_2 y_p (x)$. This is the general solution.

### Particular Solution by the Method of Undetermined Coefficients

The method of undetermined coefficients relies on noting that the inhomogeneous part of an ODE has an intuitive solution. In essence, it is an "educated guessing" method that uses commonly-seen solutions. For the ODE

$$ y'' + p(x) y' + q(x)y = g(x) = g_{1}(x) + g_{2}(x) + \dots \,, $$

the solution $y(x)$ can be speculated through $g(x)$. Below is a table showing possibilities for $y$ given $g(x)$, where $P\_n = a\_n x^{n} + a\_{n-1}x^{n-1} + \dots + a\_{0}$ is an $n$-th degree polynomial and $p\_n = A\_n x^{n} + A\_{n-1}x^{n-1} + \dots + A\_{0}$ is also a polynomial. 

| $g\_i(x)$ | $y\_i(x)$ |
| --------- | --------- |
| $ae^{\alpha x}$ | $Ae^{\alpha x}$ |
| $a\cos(\beta x)$ | $A\cos(\beta x) + B\sin(\beta x)$|
| $a\sin(\beta x)$ | $A\cos(\beta x) + B\sin(\beta x)$|
| $a\cos(\beta x) + b\cos(\beta x)$ | $A\cos(\beta x) + B\sin(\beta x)$| 
| $P\_n$ | $x^{s}p\_n$ |
| $P\_n e^{\alpha t}$ | $x^{s}p\_n e^{\alpha t}$ |
| $P\_n e^{\alpha t}\sin(\beta t)$ | $x^{s} (p\_n e^{\alpha t} \cos(\beta t) + p\_m e^{\alpha t} \sin(\beta t))$ |
| $P\_n e^{\alpha t}\cos(\beta t)$ | $x^{s} (p\_n e^{\alpha t} \cos(\beta t) + p\_m e^{\alpha t} \sin(\beta t))$ |

Note: $s=0,1,2$ is the smallest nonnegative integer that will ensure that no term in $y\_i$ is a solution to the corresponding homogenous equation. 

### Particular Solution by the Method of Variation of Parameters

This method is particularly useful as it can be used for any equation that we need the particular solution of. The first step is to find the homogenous solution $y_h = C_1 y_1 (x) + C_2 y_2 (x)$. This can be done using reduction of order as described above. The next step is to assume that the particular solution is given by

$$ \begin{equation} y_p = u_1 (x)y_1 + u_2 (x)y_2 \end{equation} $$

where $u_1$ and $u_2$ are the varied parameters and $y_1 , y_2$ are from the homogenous solution. The varied parameters are given by:

$$ \begin{align} u_1 (x) &= \int^{x} \frac{-g(t)y_2 (t)dt}{W(y1, y2)} \\  u_2 (x) &= \int^{x} \frac{g(t)y_1 (t)dt}{W(y1, y2)} \end{align} $$

where 

$$ W(y_1 , y_2) = y_1 y'_2 - y_1 ' y_2 \,, $$ 

is the Wronskian. Note that if $W(y_1 , y_2) \neq 0 $, then $y_1$ and $y_2$ are linear independent solutions are we can write $y_p$ in the form given above. Finally, we take the sum:

$$ \begin{equation} y = y_p + y_h \end{equation} \,. $$

## Series Solutions To Second-Order Linear Homogenous ODEs

It is sometimes possible to seek a series solution. Suppose we are given:

$$ \begin{equation}  P_0(x)y'' + P_1(x)y' + P_2(x)y = 0  \end{equation} \,, $$

then we can classify the coefficient $P_0$ as either **ordinary** or **singular** using the following classification: At the point $x=a$,

$$ \begin{align*} P_0(a) &\neq 0 \longrightarrow \text{Ordinary point} \\  P_0(a) &= 0 \longrightarrow \text{Singular point} \end{align*} $$

For a **singular** point, we can break it down further as

$$ \begin{align*} & \lim_{x\rightarrow a} \frac{P_1(x)}{P_0(x)}(x-a) = \text{finite} , \quad \lim_{x\rightarrow a} \frac{P_2(x)}{P_0(x)}(x-a)^2 = \text{finite} \longrightarrow \text{Regular} \\ & \text{Either limit is not finite} \longrightarrow \text{Irregular} \end{align*} $$

### Method of Frobenius When There Is Regular Singular Point


