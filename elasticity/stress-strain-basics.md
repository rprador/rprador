---
mathjax: true
title: Basics of Stress and Strain
---
{% include navigation.html %}
{% include mathjax.html %}

# Stress and Strain Basics

Short reference page dedicated to definitions and notation (I frequently forget them).

## Definitions

For a given force $F$ acting over a cross-sectional area $A$ of a *prismatic bar* (a bar with constant cross-sectional area along the length), the average *stress* is defined as the ratio

$$ \begin{equation} \boldsymbol{\sigma} = \lim_{\delta A\rightarrow 0} \frac{\delta F}{\delta A} \approx \frac{\mathbf{F}}{A} \end{equation} $$

Since the stress depends on an applied force to the body, it is a vector quantity. The stress components that are perpendicular to the area $A$ are called *normal stresses* and the stress components acting in the plane of $A$ are called *shearing stresses*. The following notation is frequently used:

$$ \sigma_{x}, \quad \sigma_{y}, \quad \sigma_{z} \quad \text{(Normal Stresses)} $$

$$ \tau_{xy} = \tau_{yx}, \quad  \tau_{zx}=\tau_{xz}, \quad \tau_{zy}=\tau_{yz} \quad \text{(Shear Stresses)} $$

Suppose a given body is deformed by a small amount, with displacement coordinates $(u, v, w)$ along the $x, y, z$ axes. This deformation causes changes in the length of the body and displaces it at an angle different from the initial set up. The ratio of the displacement to the axes coordinates are called the *unit elongation* along the axes and the change in the angle is called the *shearing strain*. The following notation is frequently used:

$$ \epsilon_{x} = \frac{\partial u}{\partial x} \quad \epsilon_{y} = \frac{\partial v}{\partial y} \quad \epsilon_{x} = \frac{\partial u}{\partial x} \quad \text{(Elongations)}$$

$$ \gamma_{xy} = \frac{\partial u}{\partial y} + \frac{\partial v}{\partial x}, \quad \gamma_{xz} = \frac{\partial u}{\partial z} + \frac{\partial w}{\partial x}, \quad \gamma_{yz} = \frac{\partial v}{\partial z} + \frac{\partial w}{\partial y} \quad \text{(Shearing Strains)}$$

The stresses and strains are related through the empirically established Hooke's law:

$$ \begin{equation} \sigma = E\epsilon \end{equation} \quad \text{(Hooke's Law)} $$

where $E$ is the modulus of elasticty or *Young's modulus*. Materials that obey Hooke's law are known as *linearly elastic* materials. The strains are also related to the stresses more generally by the *method of superposition*, which states that for a uniformly applied set of stresses on the body

$$ \begin{align} \epsilon_{x} &= \frac{1}{E} [\sigma_{x} - \nu( \sigma_{y} + \sigma_{x})] \\ \epsilon_{y} &= \frac{1}{E} [\sigma_{y} - \nu( \sigma_{x} + \sigma_{z})] \\ \epsilon_{z} &= \frac{1}{E} [\sigma_{z} - \nu( \sigma_{x} + \sigma_{y})] \end{align} $$

where $\nu$ is called **Poisson's ratio**. This can be considered Hooke's law in three dimensions. A compact way to write this is 

$$ \epsilon_{ij} = \frac{1}{E} \left[\sigma_{ij}(1+\nu) - \nu \delta-{ij}\sum_{k}\sigma_{kk}\right] $$

where $\delta_{ij}$ is the Kronecker delta.

Shearing strain and shearing stress can be related to each other using $E$ and $\nu$ as

$$ \gamma = \frac{2(1+\nu)\tau}{E} $$

Frequently, rearrangement of this relation is denoted through another constant $G$, known as the *modulus of elasticity in shear* or *modulus or rigidity* or *shear modulus*,

$$ G = \frac{\tau}{\gamma} = \frac{E}{2(1+\nu)} \quad \text{(Shear Modulus)} $$

Suppose we have a body in tension from an axial force, creating strains both in the axial and lateral (perpendicular to axial direction) directions. The ratio between both strains is called *Poisson's ratio*,

$$ \nu = -\frac{\text{lateral strain}}{\text{axial strain}} = -\frac{\varepsilon_{\text{lat}}}{\varepsilon_{\text{ax}}} \quad \text{(Poisson's Ratio)} $$

This is useful for calculating the lateral strain using $\varepsilon_{\text{lat}} = \nu \varepsilon_{\text{ax}}$.

Similar to the unit elongation concept (strains) is unit *volume change*, or the *dilatation*, 

$$ e = \frac{\Delta V}{V_{\text{initial}}} = \varepsilon (1-2\nu) = \frac{\sigma}{E}(1-2\nu) \quad \text{(Dilatation)} $$



## Special Cases for Simplification

### Plane Stress

For a thin plate loaded by forces applied at the boundary so that the force components are all in-plane to the face of the plate, the out-of-plane stress components can be taken to be zero on both the face of the plate and within the body of the plate. In other words, loads applied parallel to the $xy$-plane create nonzero stresses only in the $xy$-plane. Therefore, $\sigma_z$, $\tau_{zz}$, and $\tau_{yz}$ are zero. 

### Plane Strain

This simplification can be made for bodies that have very large dimensions in one (or more) directions. If a body is very long, say, in the $z$-direction, then loads applied perpendicular to the $z$-axis do not vary the elemental lengths within the body. In other words, the state of the strains on the cross section in the perpendicular directions ($xy$ in this example) are constant and the only nonzero strains, i.e. strains in $z$ ($\epsilon_{z}$, $\gamma_{xz}$, $\gamma_{yz}$) are all zero.

## Cauchy Stress Tensor

It is convenient to think of the state of stresses on a body to be fully defined by the nine components of the **Cauchy stress tensor**:

$$ \boldsymbol{\sigma} \equiv \begin{pmatrix} \sigma_{11} & \sigma_{12} & \sigma_{13} \\ \sigma_{21} & \sigma_{22} & \sigma_{23} \\ \sigma_{31} & \sigma_{32} & \sigma_{33} \end{pmatrix} \equiv \begin{pmatrix} \sigma_{xx} & \sigma_{xy} & \sigma_{xz} \\ \sigma_{yx} & \sigma_{yy} & \sigma_{yz} \\ \sigma_{zx} & \sigma_{zy} & \sigma_{zz} \end{pmatrix} \equiv \begin{pmatrix} \sigma_{x} & \tau_{xy} & \tau_{xz} \\ \tau_{yx} & \sigma_{y} & \tau_{yz} \\ \tau_{zx} & \tau_{zy} & \sigma_{z} \end{pmatrix} $$

$$ \boldsymbol{\sigma} = \sum_{i=1}^{3}\sum_{j=1}^{3} \sigma_{ij} \hat{e}_{i}\hat{e}_{j} = \sigma_{11}\hat{e}_{1}\hat{e}_{1} + \sigma_{12}\hat{e}_{1}\hat{e}_{2} + \sigma_{13}\hat{e}_{1}\hat{e}_{3} + \dots $$

The tensor and its components are in units of stress (N/m$^2$). The directions of the component $\sigma_{ij}$ is defined as $i$ being the direction perpendicular to the plane that the stress is acting in and $j$ is the specific directional component within the plane. For example, $\sigma_{xy}$ is the stress component in the $y$ direction created by the plane perpedicular to the $x$ axis.

Accompanying the stress tensor is the **traction vector** $T$, which can be thought of as just the sum of the stresses on a cross section. Alternatively, the traction vector is a particular row of the stress tensor:

$$ \mathbf{T} = \boldsymbol{\sigma} \cdot \mathbf{n} = \begin{pmatrix} T_{x} \\ T_{y} \\ T_{z} \end{pmatrix} $$

$$ T_{i} = \sum_{i}\sigma_{ij}n_{j} $$

$$ T_{x} = \sigma_{xx}\hat{n}_{x} + \sigma_{xy}\hat{n}_{y} + \sigma_{xz}\hat{n}_{z} $$ 

$$ T_{y} = \sigma_{yx}\hat{n}_{x} + \sigma_{yy}\hat{n}_{y} + \sigma_{yz}\hat{n}_{z} $$ 

$$ T_{z} = \sigma_{zx}\hat{n}_{x} + \sigma_{zy}\hat{n}_{y} + \sigma_{zz}\hat{n}_{z} $$ 

where $\mathbf{\sigma}$ is the stress tensor and $\mathbf{n}$ is a unit vector that can be either $\hat{n}\_{x}$, $\hat{n}\_{y}$, or $\hat{n}\_{z}$.

Physically, the traction vector is similar to a stress but it measures the (internal) force vector acting on a cross section divided by that cross section's area.

Individual stress components can be extracted from the stress tensor and traction vectors as follows:

$$ \hat{n}_{y} \cdot T_{y} = \hat{n}_{y} (\sigma_{yx}\hat{n}_{x} + \sigma_{yy}\hat{n}_{y} + \sigma_{yz}\hat{n}_{z}) = \sigma_{yy} $$

or

$$ \hat{n}_{y} \cdot \mathbf{\sigma} \cdot \hat{n}_{y} = \hat{n}_{y} \cdot \begin{pmatrix} \sigma_{xx} & \sigma_{xy} & \sigma_{xz} \\ \sigma_{yx} & \sigma_{yy} & \sigma_{yz} \\ \sigma_{zx} & \sigma_{zy} & \sigma_{zz} \end{pmatrix} \cdot \hat{n}_{y} = \sigma_{yy} $$

## Common Metrics for Safety

For reference, a *structure* is any object that supports or transmits loads. The *strength* of a structure is its ability to resist loads. The strength that a structure needs during common application is called the *required strength* while the largest strength a structure can have is called *actual strength*. Going by these, one type of safety measure is the *safety factor*

$$ n = \frac{\text{Actual Strength}}{\text{Required Strength}} $$ 

Usual safe range used is from 1 to 10, but this can vary. Of course, the higher the safety factory, the better.

Yield strength (i.e. the amount of force required to cause yielding, that is, elongation of a material at constant tension) can also be used as a safety measure through the quantity *allowable stress*

$$ \text{Allowable Stress} = \frac{\text{Yield Strength}}{Safety Factor} $$

which can be broken down into its normal and shear components

$$ \sigma_{\text{allow}} = \frac{\sigma_y}{n_1}, \quad \tau_{\text{allow}} = \frac{\tau_y}{n_2} $$

where $n_1, n_2$ are safety factors. The allowable stress is useful as the dependence on the yield strength provides a way to know if the material is being kept within the linearly elastic limit (note: yield stress is roughly the upper limit of the linear elastic range).
