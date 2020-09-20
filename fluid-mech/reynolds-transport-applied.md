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

### Control Volumes in Noninertial Frames

This case might not be very common in many problems but it will be here anyways. Suppose we have a fluid flowing within a noninertial reference frame. Let $\textbf{R}$ be the radial vector from a fixed inertial frame pointing to the origin of the noninertial frame. Let $\textbf{r}$ be the radial vector within the noninertial frame that points to a particle. The position of the particle with respect to the fixed inertial frame can be written as:

$$ \textbf{r}' = \textbf{R} + \textbf{r} $$

Differentiating with respect to time,

$$ \textbf{V}' = \textbf{V} + \frac{d\textbf{r}}{dt} $$
