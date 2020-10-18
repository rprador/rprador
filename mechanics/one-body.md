---
mathjax: true
title: Derivation of the Equivalent One-Body Problem
---
{% include navigation.html %}
{% include mathjax.html %}

# Derivation of the Equivalent One-Body Problem

![Coordinates](https://rprador.github.io/rprador/mechanics/figures/CM_coords.PNG)

Suppose we have two masses, $m_1$ and $m_2$, with the only forces present being an interaction potential $U$. We also assume that the interaction potential depends either on the positions of the masses relative to one another ($\textbf{r}\_2 - \textbf{r}\_1$) or on their relative derivatives ($\dot{\textbf{r}}\_2 - \dot{\textbf{r}}\_2$), which we allow to be of any higher order. Note that these are _relative_ quantities. What we do now is encode the six degrees of degrees (three per mass) into two vectors: the radius vector of the center-of-mass (CM) $\textbf{R}$ and the position vector from one mass to the other $\textbf{r}=\textbf{r}\_2 - \textbf{r}\_1$. As a reminder, the CM vector is given by:

$$ \textbf{R} = \frac{1}{M}\sum_{i}m_{i}\textbf{r}_{i} = \frac{m_1 \textbf{r}_1 + m_2 \textbf{r}_2}{m_1 + m_2} \,, $$

where $\textbf{r}\_1$ and $\textbf{r}\_2$ are the position vectors of the masses with respect to the origin of the system.

The general Lagrangian will then look like

$$ \begin{equation} L = T(\dot{\textbf{R}}, \dot{\textbf{r}}) - U(\textbf{r}, \dot{\textbf{r}}, \dots) \,. \end{equation}$$

Here, the kinetic energy $T$ can be split into components of the CM plus the components of motion about the CM:

$$ T = \frac{1}{2}(m_{1} + m_{2})\dot{\textbf{R}}^{2} + \frac{1}{2}m_{1}\dot{\textbf{r}}_{1}^{'2} + \frac{1}{2}m_{2}\dot{\textbf{r}}_{2}^{'2} \,, $$

where $\dot{\textbf{r}}\_{1}^{\'}$ and $\dot{\textbf{r}}\_{1}^{\'}$ are the radial vectors of the masses _relative_ to the CM, not the origin, and are given by

$$ \textbf{r}_{1}^{'} = -\frac{m_{2}}{m_{1}+m_{2}}\textbf{r} , \quad \textbf{r}_{2}^{'} = -\frac{m_{1}}{m_{1}+m_{2}}\textbf{r} \,. $$

In terms of $\textbf{r}$, the kinetic energy is

$$ \begin{align*} T &= \frac{1}{2}(m_{1} + m_{2})\dot{\textbf{R}}^{2} + \frac{1}{2}m_{1} \left(\frac{m_{2}}{m_{1}+m_{2}}\right)^{2} \dot{\textbf{r}}^{2} + \frac{1}{2}m_{1} \left(\frac{m_{1}}{m_{1}+m_{2}}\right)^{2}  \dot{\textbf{r}}^{2} \\ &= \frac{1}{2}(m_{1} + m_{2})\dot{\textbf{R}}^{2} + \frac{1}{2}\frac{m_{1}m_{2}}{m_{1}+m_{2}}\dot{\textbf{r}}^{2} \end{align*} $$

One last thing we can do is introduced the **reduced mass**, defined as

$$ \mu = \frac{m_1 m_2}{m_1 + m_2 \,. }$$

The Lagrangian can be written as

$$ \begin{equation} L =  \frac{1}{2}(m_{1} + m_{2})\dot{\textbf{R}}^{2} + \frac{1}{2}\mu\dot{\textbf{r}}^{2} - U(\textbf{r}, \dot{\textbf{r}}, \dots) \,. \end{equation} $$

By using $\textbf{R}$ and $\textbf{r}$, the problem can now be interpreted as one of two fictitious particles of mass $M=m\_1 + m\_2$ moving with the speed of the CM, and another of mass $\mu$ moving with a speed of the relative position $\textbf{r}$. Thus, the problem has been reduced to a one-body problem based around the CM of the system. In deriving the equations of motion, we can now focus on just a single particle Lagrangian.

# Equations of Motion

We assume that the interaction potential is due to a conservative central force, $V(r)$, so that the forces is only along $\textbf{r}$. Since the potential only depends on the radial coordinate $r$, the problem is spherically symmetric. Furthermore, the Lagrangian depends on $\textbf{r}, \dot{\textbf{r}}, \dot{\textbf{R}}$ but not on $\textbf{R}$, meaning that $\textbf{R}$ is a cyclic coordinate. Therefore, $m\dot{\textbf{R}}=0$, implying uniform motion of the CM. Through the spherical symmetry of the problem, we know that the total angular momentum of the system is conserved:

$$ \textbf{L} = \textbf{r} \times \textbf{p} = \text{constant} \,. $$

From this, the central force motion is always in a plane.

Moving back to the Lagrangian, in polar coordinates we have for a single particle of mass $m$

$$ L = \frac{1}{2}m(\dot{r}^{2} + r^{2}\dot{\theta}^{2}) - V(r) \,. $$

The $\theta$ coordinate is cyclic, so its canonical momentum $p\_\theta$ is conserved:

$$ p_\theta = \frac{\partial L}{\partial \dot{\theta}} = mr^{2}\dot{\theta} = l = \text{const.}  \,, $$

where $l$ is the constant magnitude of the angular momentum.
