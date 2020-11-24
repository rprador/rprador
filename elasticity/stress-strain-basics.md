---
mathjax: true
title: Basics of Stress and Strain
---
{% include navigation.html %}
{% include mathjax.html %}

# Stress and Strain Basics

Short reference page dedicated to definitions and notation (I frequently forget them).

## Definitions

For a given force $F$ acting over a cross-sectional area $A$ of a prismatic bar, the average **stress** is defined as the ratio

$$ \begin{equation} \mathbf{\sigma} = \lim_{\delta A\rightarrow 0} \frac{\delta F}{\delta A} \approx \frac{\mathbf{F}}{A} \end{equation} $$

Since the stress depends on an applied force to the body, it is a vector quantity. The stress components that are perpendicular to the area $A$ are called **normal stresses** and the stress components acting in the plane of $A$ are called **shearing stresses**. The following notation is frequently used:

$$ \sigma_{x}, \quad \sigma_{y}, \quad \sigma_{z} \quad \text{(Normal Stresses)} $$

$$ \tau_{xy} = \tau{yx}, \quad  \tau_{zx}=\tau_{xz}, \quad \tau_{zy}=\tau_{yz} \quad \text{(Shear Stresses)} $$

Suppose a given body is deformed by a small amount, with displacement coordinates $(u, v, w)$ along the $x, y, z$ axes. This deformation causes changes in the length of the body and displaces it at an angle different from the initial set up. The ratio of the displacement to the axes coordinates are called the **unit elongation** along the axes and the change in the angle is called the **shearing strain**. The following notation is frequently used:

$$ \epsilon_{x} = \frac{\partial u}{\partial x} \quad \epsilon_{y} = \frac{\partial v}{\partial y} \quad \epsilon_{x} = \frac{\partial u}{\partial x} \quad \text{(Elongations)}$$

$$ \gamma_{xy} = \frac{\partial u}{\partial y} + \frac{\partial v}{\partial x}, \quad \gamma_{xz} = \frac{\partial u}{\partial z} + \frac{\partial w}{\partial x}, \quad \gamma_{yz} = \frac{\partial v}{\partial z} + \frac{\partial w}{\partial y} \quad \text{(Shearing Strains)}$$

The stresses and strains are related through the empirically established Hooke's law:

$$ \begin{equation} \sigma = E\epsilon \end{equation} $$

where $E$ is the modulus of elasticty or *Young's modulus*. Materials that obey Hooke's law are known as *linearly elastic* materials. The strains are also related to the stresses more generally by the **method of superposition**, which states that for a uniformly applied set of stresses on the body

$$ \begin{align} \epsilon_{x} &= \frac{1}{E} [\sigma_{x} - \nu( \sigma_{y} + \sigma_{x})] \\ \epsilon_{y} &= \frac{1}{E} [\sigma_{y} - \nu( \sigma_{x} + \sigma_{z})] \\ \epsilon_{z} &= \frac{1}{E} [\sigma_{z} - \nu( \sigma_{x} + \sigma_{y})] \end{align} $$

where $\nu$ is called **Poisson's ratio**. This can be considered Hooke's law in three dimensions. A compact way to write this is 

$$ \epsilon_{ij} = \frac{1}{E} \left[\sigma_{ij}(1+\nu) - \nu \delta-{ij}\sum_{k}\sigma_{kk}\right] $$

where $\delta_{ij}$ is the Kronecker delta.

## Special Cases for Simplification

### Plane Stress

For a thin plate loaded by forces applied at the boundary so that the force components are all in-plane to the face of the plate, the out-of-plane stress components can be taken to be zero on both the face of the plate and within the body of the plate. In other words, loads applied parallel to the $xy$-plane create nonzero stresses only in the $xy$-plane. Therefore, $\sigma_z$, $\tau_{zz}$, and $\tau_{yz}$ are zero. 

### Plane Strain

This simplification can be made for bodies that have very large dimensions in one (or more) directions. If a body is very long, say, in the $z$-direction, then loads applied perpendicular to the $z$-axis do not vary the elemental lengths within the body. In other words, the state of the strains on the cross section in the perpendicular directions ($xy$ in this example) are constant and the only nonzero strains, i.e. strains in $z$ ($\epsilon_{z}$, $\gamma_{xz}$, $\gamma_{yz}$) are all zero.

## Cauchy Stress Tensor

It is convenient to think of the state of stresses on a body to be fully defined by the nine components of the **Cauchy stress tensor**:

$$ \mathbf{\sigma} \equiv \begin{pmatrix} \sigma_{11} & \sigma_{12} & \sigma_{13} \\ \sigma_{21} & \sigma_{22} & \sigma_{23} \\ \sigma_{31} & \sigma_{32} & \sigma_{33} \end{pmatrix} \equiv \begin{pmatrix} \sigma_{xx} & \sigma_{xy} & \sigma_{xz} \\ \sigma_{yx} & \sigma_{yy} & \sigma_{yz} \\ \sigma_{zx} & \sigma_{zy} & \sigma_{zz} \end{pmatrix} \equiv \begin{pmatrix} \sigma_{x} & \tau_{xy} & \tau_{xz} \\ \tau_{yx} & \sigma_{y} & \tau_{yz} \\ \tau_{zx} & \tau_{zy} & \sigma_{z} \end{pmatrix} $$

The tensor and its components are in units of stress (N/m$^2$). The directions of the component $\sigma_{ij}$ is defined as $i$ being the direction perpendicular to the plane that the stress is acting in and $j$ is the specific directional component within the plane. For example, $\sigma_{xy}$ is the stress component in the $y$ direction created by the plane perpedicular to the $x$ axis.
