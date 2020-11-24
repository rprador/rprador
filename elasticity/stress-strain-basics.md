---
mathjax: true
title: Basics of Stress and Strain
---
{% include navigation.html %}
{% include mathjax.html %}

# Stress and Strain Basics

Short reference page dedicated to definitions and notation (I frequently forget them).

For a given force $F$ acting over a cross-sectional area $A$ of a prismatic bar, the average **stress** is defined as the ratio

$$ \begin{equation} \mathbf{\sigma} = \lim_{\delta A\rightarrow 0} \frac{\delta F}{\delta A} \approx \frac{\mathbf{F}}{A} \end{equation} $$

Since the stress depends on an applied force to the body, it is a vector quantity. The stress components that are perpendicular to the area $A$ are called **normal stresses** and the stress components acting in the plane of $A$ are called **shearing stresses**. The following notation is frequently used:

$$ \sigma_{x}, \quad \sigma_{y}, \quad \sigma_{z} \quad \text{(Normal Stresses)} $$

$$ \tau_{xy} = \tau{yx}, \quad  \tau_{zx}=\tau_{xz}, \quad \tau_{zy}=\tau_{yz} \quad text{(Shear Stresses)} $$

Suppose a given body is deformed by a small amount, with displacement coordinates $(u, v, w)$ along the $x, y, z$ axes. This deformation causes changes in the length of the body and displaces it at an angle different from the initial set up. The ratio of the displacement to the axes coordinates are called the **unit elongation** along the axes and the change in the angle is called the **shearing strain**. The following notation is frequently used:

$$ \begin{align*} \epsilon_{x} &= \frac{\partial u}{\partial x} \quad \epsilon_{y} &= \frac{\partial v}{\partial y} \quad \epsilon_{x} &= \frac{\partial u}{\partial x} \\ \gamma_{xy} &= \frac{\partial u}{\partial y} + \frac{\partial v}{\partial x}, \quad \gamma_{xz} &= \frac{\partial u}{\partial z} + \frac{\partial w}{\partial x}, \quad \gamma_{yz} &= \frac{\partial v}{\partial z} + \frac{\partial w}{\partial y} \end{align} $$
