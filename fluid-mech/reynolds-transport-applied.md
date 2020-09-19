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

\begin{align} \frac{dm}{dt}_{\text{sys}} &= \frac{d}{dt}\left( \int_{V} (1) \rho d\mathcal{V} \right) + \int_{\text{surf}} (1) \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \frac{d}{dt}\left( \int_{V} \rho d\mathcal{V} \right) + \int_{\text{surf}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \int_{V} \frac{\partial\rho}{\partial t} d\mathcal{V} + \int_{\text{surf}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{align}

Mass conservation states explicitly that $dm/dt$ of the system is zero. Therefore:

\begin{equation} 0 = \int_{V} \frac{\partial\rho}{\partial t} d\mathcal{V} + \int_{\text{surf}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation}

t
