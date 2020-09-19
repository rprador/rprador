---
mathjax: true
title: Applications of Reynold's Transport Theorem
---
{% include navigation.html %}
{% include mathjax.html %}

# Conservation of Mass

Recall that Reynold's transport theorem stated, that for an extensive property $B$ and its intensive form, $\beta = dB/dm$:

\begin{equation} \frac{dB}{dt} = \frac{d}{dt}\left( \int_{V} \beta \rho d\mathcal{V} \right) + \int_{\text{surf}} \beta \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation}

Our choice for $B$ is the mass, so $B=m$ and $\beta=dm/dm=1$. Thus,

$$ \begin{align*} \left(\frac{dm}{dt}\right)_{\text{sys}} &= \frac{d}{dt}\left( \int_{V} (1) \rho d\mathcal{V} \right) + \int_{\text{surf}} (1) \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \frac{d}{dt}\left( \int_{V} \rho d\mathcal{V} \right) + \int_{\text{surf}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \int_{V} \frac{\partial\rho}{\partial t} d\mathcal{V} + \int_{\text{surf}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{align*} $$

Mass conservation states explicitly that $dm/dt$ of the system is zero. Therefore:

\begin{equation} 0 = \int_{V} \frac{\partial\rho}{\partial t} d\mathcal{V} + \int_{\text{surf}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation}

This is the most general form of the **conservation of mass** for a control volume. However, a few simplifications can be made with the right assumptions.

## Steady Flow

In the case of steady flow, the time dependence of the Reynold's transport theorem is taken to be zero. In other words, every time derivative vanishes. Hence, $\partial \rho /\partial t = 0$, and so:

$$ \int_{\text{surf}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA = 0 \;\;\;\; \text{Steady flow}$$

In the one-dimensional case, the integral reduces to individual contributions $\rho_{i}A_{i}V_{i}$. This leads to the very simple relation:

$$ \sum_{i} (\dot{m}_{i})_{\text{in}} = \sum_{i} (\dot{m}_{i})_{\text{out}} $$

## Incompressible Flow

By incompressible, we mean the change in density (time derivative here) is negligible. In other words, $\rho \approx$ constant. It is useful to know that although it is not general true that most fluids are incompressible, it is true that all liquids are ***nearly*** incompressible. Like from the case of steady flow, we therefore have:

$$ \begin{align*} 0 &= \int_{\text{surf}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \rho \int_{\text{surf}} (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \int_{\text{surf}} (\textbf{V}\cdot \hat{\textbf{n}})dA \end{align*} $$


