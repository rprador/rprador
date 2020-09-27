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

Normally, I would not make a distinction here about the derivative but it should be noted that this type of derivative that splits the vector quantity into a time-dependent and spatial-dependent part is known as **substantial** or **material** derivatives. It is common to use the notation $D/DT$ for this type of derivative.

## Conservation of Mass (Continuity Equation)

![Volume element mass](https://rprador.github.io/rprador/fluid-mech/figures/volume-element-mass.PNG)

Suppose we have a volume element as shown in the figure. One derivation of the continuity equation begins with describing the mass flux through one end of the control volume to the other, in which the fluid velocity runs parallel to the surface normal of the faces. In other words, given a mass flow rate $\rho A V$, where $\rho$ is the mass density, $A$ is the surface area of one face of the control volume and $V$ is the fluid velocity, then what is the change in the mass flow rate $d(\rho A V)$? Assuming mass conservation holds (and, as usual, it does), then it should be that the mass flow rate in equals the mass flow rate out. Let the fluid flow along the $x$-axos through the surface made by $dydz$, as in the figure. Then the mass flow rate in is $\rho u dydz$. After traveling a distance $dx$, the mass flow rate is approximately:

$$ \dot{m} + d\dot{m} = \dot{m} + \frac{\partial \dot{m}}{\partial x}dx = \rho u dydz + \frac{\partial \rho u}{\partial x} dxdydz$$

