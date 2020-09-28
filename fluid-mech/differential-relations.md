---
mathjax: true
title: Differential Relations for Fluid Flow
---
{% include navigation.html %}
{% include mathjax.html %}

# Differential Relations for Fluid Flow

Rather than working with integrals over control volumes and control surfaces, fluid flow can instead be modelled through differential equations.

## A Few Definitions

For a fluid velocity vector $\textbf{V}(\textbf{r}, t) = u\hat{\textbf{x}} + v\hat{\textbf{y}} + w\hat{\textbf{z}}$, the acceleration vector is given by:

$$ \textbf{a}(\textbf{r}, t) = \frac{d\textbf{V}}{dt} = \frac{\partial \textbf{V}}{\partial t} + \sum_{i} \frac{\partial \textbf{V}}{\partial x_{i}}\frac{dx_{i}}{dt} =  \frac{\partial \textbf{V}}{\partial t} + (\textbf{V} \cdot \nabla)\textbf{V} $$

$$ \begin{equation} \textbf{a}(\textbf{r}, t) =  \underbrace{\frac{\partial \textbf{V}}{\partial t}}_{\text{Local Accel.}} + \underbrace{(\textbf{V} \cdot \nabla)\textbf{V}}_{\text{Convective Accel.}}  \end{equation} $$

Normally, I would not make a distinction here about the derivative but it should be noted that this type of derivative that splits the vector quantity into a time-dependent and spatial-dependent part is known as **substantial** or **material** derivatives. It is common to use the notation $D/Dt$ for this type of derivative.

For a very nice way to get the following equations, we can transform Reynold's transport theorem into differential form using the [divergence (Gauss's) theorem](https://en.wikipedia.org/wiki/Divergence_theorem), where the theorem is, for an arbitrary vector $\textbf{A}$:

$$ \int_{\text{Vol.}} (\nabla \cdot \textbf{A})d\mathcal{V} = \int_{\text{Surf.}} (\textbf{A} \cdot \hat{\textbf{n}})dA  $$

Starting from the integral form, where $B$ is an extensive property and $\beta = dB/dm$ is the intensive property:

$$ \begin{align*} \frac{dB}{dt} = \frac{d}{dt}\left( \int_{V} \beta \rho d\mathcal{V} \right) + \int_{\text{surf}} \beta \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{align*} $$


## Conservation of Mass (Continuity Equation)

![Volume element mass](https://rprador.github.io/rprador/fluid-mech/figures/volume-element-mass.PNG)

Suppose we have a volume element as shown in the figure. One derivation of the continuity equation begins with describing the mass flux through one end of the control volume to the other, in which the fluid velocity runs parallel to the surface normal of the faces. In other words, given a mass flow rate $\rho A V$, where $\rho$ is the mass density, $A$ is the surface area of one face of the control volume and $V$ is the fluid velocity, then what is the change in the mass flow rate $d(\rho A V)$?

Assuming mass conservation holds (and, as usual, it does), then it should be that the mass flow rate in equals the mass flow rate out. Let the fluid flow along the $x$-axis through the surface made by $dydz$, as in the figure. Then the mass flow rate in is $\rho u dydz$. After traveling a distance $dx$, the mass flow rate is approximately:

$$ \dot{m} + d\dot{m} = \dot{m} + \frac{\partial \dot{m}}{\partial x}dx = \rho u dydz + \frac{\partial \rho u}{\partial x} dxdydz$$

Thus:

$$ \begin{align*} \dot{m}_{\text{in}} &= \dot{out}_{\text{out}} \\
\rho u dydz &= \rho u dydz + \frac{\partial}{\partial x}(\rho u) dxdydz \\
0 &= \frac{\partial}{\partial x}(\rho u) \end{align*} $$

If we include the rest of the faces of the differential volume, then we have that total change in mass flow rate is:

$$ 0 = \frac{\partial \rho u}{\partial x} + \frac{\partial \rho v}{\partial y} + \frac{\partial \rho w}{\partial z} = \nabla \cdot (\rho \textbf{V})$$

If the mass flow is time-depedent, an additional contribution $\partial\rho/\partial t$ has to be considered. In summary, we would have:

$$ \begin{equation} \frac{\partial \rho}{\partial t} + \nabla \cdot (\rho \textbf{V}) = 0 \end{equation} $$

Another way to arrive at this is to use the differential form of Reynold's theorem.

$$  \int_{CV} \frac{\partial\rho}{\partial t} d\mathcal{V} + \int_{\text{CS}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \rightarrow  \int_{CV} \frac{\partial\rho}{\partial t} d\mathcal{V} + \int_{\text{CV}} \nabla \cdot (\rho \textbf{V}) d\mathcal{V} $$

hen the integral relation reduces to:

$$ \begin{align*} 0 &= \int_{CV} \frac{\partial\rho}{\partial t} d\mathcal{V} + \int_{\text{CV}} \nabla \cdot (\rho \textbf{V}) d\mathcal{V} \\
&= \int_{CV} \left[ \frac{\partial\rho}{\partial t} + \nabla \cdot (\rho \textbf{V}) \right] d\mathcal{V} \\
&= \frac{\partial\rho}{\partial t} + \nabla \cdot \rho (\textbf{V}) \end{align*} $$

Note: the density $\rho$ has not yet been assumed constant!

### Steady State

If we have steady flow, then the time-dependent term vanishes:

$$ 0 = \nabla \cdot (\rho \textbf{V}) $$

### Incompressible

Now, the density is approximately constant, so:

$$ 0 = \nabla \cdot \textbf{V}$$

Note: White makes a distinction when regarding fluids as incompressible. It turns out that this can be determined through the ***Mach number*** of the fluid flow:

$$ \text{Ma}^{2} \equiv \left(\frac{V}{c_{\text{sound}}}\right)^{2} \ll 1 $$

where $c\_{\text{sound}}$ is the speed of sound in the fluid. White states that a commonly accepted value for incompressibility is when $\text{Ma} \leq 0.3$.

## Linear Momentum Equation


