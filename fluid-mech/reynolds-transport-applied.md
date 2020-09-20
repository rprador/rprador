---
mathjax: true
title: Applications of Reynold's Transport Theorem
---
{% include navigation.html %}
{% include mathjax.html %}

# Applications of Reynold's Transport Theorem

The usefulness of the transport theorem is in its ability to find relations between the control volume and relevant properties. Below show such relations for various properties.

## Conservation of Mass

Recall that Reynold's transport theorem stated for an extensive property $B$ and its intensive form, $\beta = dB/dm$:

\begin{equation} \frac{dB}{dt} = \frac{d}{dt}\left( \int_{CV} \beta \rho d\mathcal{V} \right) + \int_{\text{CS}} \beta \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation}

Our choice for $B$ is the mass, so $B=m$ and $\beta=dm/dm=1$. Thus,

$$ \begin{align*} \left(\frac{dm}{dt}\right)_{\text{sys}} &= \frac{d}{dt}\left( \int_{CV} (1) \rho d\mathcal{V} \right) + \int_{\text{CS}} (1) \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \frac{d}{dt}\left( \int_{CV} \rho d\mathcal{V} \right) + \int_{\text{CS}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \int_{CV} \frac{\partial\rho}{\partial t} d\mathcal{V} + \int_{\text{CS}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{align*} $$

Mass conservation states explicitly that $dm/dt$ of the system is zero. Therefore:

\begin{equation} 0 = \int_{CV} \frac{\partial\rho}{\partial t} d\mathcal{V} + \int_{\text{CS}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation}

This is the most general form of the **conservation of mass** for a control volume. However, a few simplifications can be made with the right assumptions.

### Steady Flow

In the case of steady flow, the time dependence of the Reynold's transport theorem is taken to be zero. In other words, every time derivative vanishes. Hence, $\partial \rho /\partial t = 0$, and so:

$$ \int_{\text{CS}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA = 0 \;\;\;\; \text{(Steady flow)} $$

In the case that inlet/outlet surfaces are one-dimensional, the integral reduces to individual contributions $\rho_{i}A_{i}V_{i}$. This leads to the very simple relation:

$$ \sum_{i} (\dot{m}_{i})_{\text{in}} = \sum_{i} (\dot{m}_{i})_{\text{out}} \;\;\;\; \text{(1D Steady flow)} $$

However, if not then we have to calculated an integral for each inlet/outlet:

$$\dot{m} = \int_{\text{CS}} \rho (\textbf{V} \cdot \hat{\textbf{n}}) $$

### Incompressible Flow

By incompressible, we mean the change in density (time derivative here) is negligible. In other words, $\rho \approx$ constant. It is useful to know that although it is not general true that most fluids are incompressible, it is true that all liquids are ***nearly*** incompressible. Like from the case of steady flow, we therefore have:

$$ \begin{align*} 0 &= \int_{\text{CS}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \rho \int_{\text{CS}} (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \int_{\text{CS}} (\textbf{V}\cdot \hat{\textbf{n}})dA \end{align*} $$

For a general control surface, we have that the volumetric flow rate must be zero:

$$Q_{\text{CS}} = \int_{\text{CS}} (\textbf{V}\cdot \hat{\textbf{n}})dA = 0 \;\;\;\; \text{(Incompressible flow)}$$

If the inlets/outlets are one-dimensional:

$$ \sum Q_{\text{in}} = \sum Q_{\text{out}} \;\;\;\; \text{(1D Incompressible flow)}$$

where $Q = A_{i}V_{i}$.

## Newton's Second Law

The next extensive property that can be worked with is momentum. Then $\textbf{B} = \textbf{p}$ and $\beta = d\textbf{p}/dm = \textbf{V} $, where we are keeping track of the vector components. Substituting this into the general Reynold's transport theorem:

$$ \begin{equation}  \left(\frac{d\textbf{p}}{dt}\right)_{\text{sys}} = \sum_{i}\textbf{F}_{i} = \frac{d}{dt} \int_{\text{CV}} \textbf{V} \rho d\mathcal{V} + \int_{\text{CS}}\textbf{V} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation} $$

where Newton's second law has been used on the LHS. Since Newton's law was used, it should be noted that the reference frame of the control volume must be inertial, i.e. it is not accelerating. This equation is called the **linear momentum equation**.

In the case of one dimensional inlets/outlets, we have:

$$ \sum_{i}\textbf{F}_{i} = \frac{d}{dt} \int_{\text{CV}} \textbf{V} \rho d\mathcal{V} + \sum(\dot{m}_{i}\textbf{V}_{i})_{\text{out}} - \sum(\dot{m}_{i}\textbf{V}_{i})_{\text{in}} \;\;\;\; (\text{1D momentum flux}) $$

The label ***momentum flux*** refers to the momentum analogue for the mass flow rate:

$$ \dot{\textbf{M}}_{\text{CS}} = \int \textbf{V} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA $$

which in the one dimensional case with constant density is:

$$ \dot{\textbf{M}} = \dot{m}_{i}\textbf{V}_{i} $$

### Noninertial Frames

### Time derivatives in rotating frames

Suppose we have a fixed inertial frame $S_{0}$ with coordinates $(x_{0}, y_{0}, z_{0})$. Let there be another frame $S$ with coordinates $(x, y, z)$ that shares an origin with $S_{0}$ and is rotating with angular velocity $\boldsymbol{\Omega}$. Let $Q$ be an arbitrary vector:

$$ \textbf{Q} = Q_{1}\hat{\textbf{e}}_{1} + Q_{2}\hat{\textbf{e}}_{2} + Q_{3}\hat{\textbf{e}}_{3} $$

where $\hat{\textbf{e}}\_{i}$ are unit vectors. The time derivative of $\textbf{Q}$ relative to the inertial fram $S_{0}$ is:

$$ \left(\frac{d\textbf{Q}}{dt}\right)_{S_{0}} $$

and the time derivative of $\textbf{Q}$ relative to the noninertial frame $S$ is:

$$ \left(\frac{d\textbf{Q}}{dt}\right)_{S} $$

Within the noninertial frame $S$, the unit vectors $\hat{\textbf{e}}_{i}$ are stationary, so that the time derivative is simply:

$$ \left(\frac{d\textbf{Q}}{dt}\right)_{S} = \sum_{i} \frac{dQ_{i}}{dt}\hat{\textbf{e}}_{i} $$

However, in the fixed inertial frame $S_{0}$, the unit vectors are rotating, so they undergo a change:

$$ \left(\frac{d\textbf{Q}}{dt}\right)_{S_{0}} = \sum_{i} \frac{dQ_{i}}{dt}\hat{\textbf{e}}_{i} + \sum_{i}Q_{i} \left( \frac{d\hat{\textbf{e}_{i}}}{dt} \right)_{S_{0}} $$

The second term on the RHS can be evaluated as (need to find proof somewhere of this):

$$ \frac{d\hat{\textbf{e}}}{dt} = \boldsymbol{\Omega} \times \hat{\textbf{e}} $$

Hence:

$$ \begin{align*} \left(\frac{d\textbf{Q}}{dt}\right)_{S_{0}} &= \sum_{i} \frac{dQ_{i}}{dt}\hat{\textbf{e}}_{i} + \sum_{i}Q_{i} (\boldsymbol{\Omega} \times \hat{\textbf{e}}) \\ 
&= \sum_{i} \frac{dQ_{i}}{dt}\hat{\textbf{e}}_{i} + \boldsymbol{\Omega} \times \sum_{i}Q_{i}\hat{\textbf{e}}_{i} \\
&= \sum_{i} \frac{dQ_{i}}{dt}\hat{\textbf{e}}_{i}  + \boldsymbol{\Omega} \times \textbf{Q} \end{align*} $$

Therefore, any time derivative of a vector within an inertial frame is equal to a time derivative in the noninterial frame plus a rotational effect $\textbf{\Omega} \times \textbf{Q}$:

$$ \left(\frac{d\textbf{Q}}{dt}\right)_{S_{0}} = \left( \frac{d\textbf{Q}}{dt} \right)_{S}  + \boldsymbol{\Omega} \times \textbf{Q} $$

### Newton's second law in a rotating frame

With the results from above, we can easily derive the velocity and acceleration vectors in a rotating frame. Let the position of a fluid particle be $\textbf{r}$

The velocity $\textbf{V}$ of a fluid particle is:

$$ \left(\frac{d\textbf{r}}{dt}\right)_{S_{0}} = \left( \frac{d\textbf{r}}{dt} \right)_{S}  + \boldsymbol{\Omega} \times \textbf{r} $$

Defining the velocities:

$$ \textbf{V}_{\text{in}} = \left(\frac{d\textbf{r}}{dt}\right)_{S_{0}} , \;\;\;\; \textbf{V}_{\text{rot}} = \left(\frac{d\textbf{r}}{dt}\right)_{S_{0}} $$

We get:

$$ \textbf{V}_{\text{in}} = \textbf{V}_{\text{rot}} + \boldsymbol{\Omega} \times \textbf{r} $$

A second differentiation yields:

$$ \begin{align*} \frac{\textbf{V}_{\text{in}}}{dt} &= \frac{d\textbf{V}_{\text{rot}}}{dt} + \frac{d}{dt}\left( \boldsymbol{\Omega} \times \textbf{r} \right) \\
&= \frac{d\textbf{V}_{\text{rot}}}{dt} + \frac{d\boldsymbol{\Omega}}{dt}\times \textbf{r} + \boldsymbol{\Omega}\times \frac{d\textbf{r}}{dt} \end{align*} $$
