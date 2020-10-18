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

$$ \textbf{r}_{1}^{'} = -\frac{m_{2}}{m_{1}+m_{2}}\textbf{r} \quad \textbf{r}_{2}^{'} = -\frac{m_{1}}{m_{1}+m_{2}}\textbf{r} \,. $$

In terms of $\textbf{r}$, the kinetic energy is

$$ T = \frac{1}{2}(m_{1} + m_{2})\dot{\textbf{R}}^{2} + \frac{1}{2}m_{1}(\frac{m_{2}}{m_{1}+m_{2}})^{2}\dot{\textbf{r}}^{2} + \frac{1}{2}m_{1}(\frac{m_{1}}{m_{1}+m_{2}})^{2}  \dot{\textbf{r}}^{2} $$

By using $\textbf{R}$ and $\textbf{r}$, the problem will simplify greatly.
