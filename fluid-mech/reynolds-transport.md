---
mathjax: true
title: Statement of Reynold's transport theorem
---
{% include navigation.html %}
{% include mathjax.html %}
# Reynold's Transport Theorem
Studying fluids typically involve looking at specific "sections" of the fluid known as *control volumes*. This is not the only way to study a fluid but it is the most commonly introduced method. We start with a few definitions.

## Quick definitions
![Arbitrary control volume](https://rprador.github.io/rprador/fluid-mech/figures/control-volume.PNG)
The above figure shows such a control volume for a fluid flowing through an arbitrary surface (a). The differential volume through a differential element $dA$ traces out a slanted parallelepiped (b) that is along the direction of the flow, which in this case is affected by the orientation of the elemental area. To account for this orientation, we simply take velocity $\textbf{V}$ projected onto the normal of the elemental area, $\textbf{V} \cdot \hat{\textbf{n}}$. The differential volume is, therefore, (think base times height):

$$d \mathcal{V} = (\textbf{V}\cdot \hat{\textbf{n}})dAdt$$

Dividing both sides by $$dt$$ and integrating gives the **volumetric flow rate** $$Q$$:

\begin{equation} Q=\int_{\text{surf}}(\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation}

Lots of times, the geometry of the control volume is not complicated, the velocity is constant, and the flow is one-dimensional, so we can specify the integral more succinctly as:

$$Q = AV$$

Conveniently, we can multiply the volumetric flow rate by the fluid's density to obtain the **mass flow rate**:

\begin{equation} \dot{m} = \int_{\text{surf}}\rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation}

Like before, this takes on a simple form assuming the case of a one-dimensional flow at constant velocity and density:

$$\dot{m} = \rho Q = \rho A V$$

Note: units of volumetric flow rate are m<sup>3</sup>/s; mass flow rate are kg/s. It should also be noted that by the nature of the dot product in the expressions above, we can define the direction of flow. Going by the convention in White's textbook, $\hat{\textbf{n}}$ is taken to be an ***outward*** normal vector to the surface. Therefore, the dot product $$\textbf{V}\cdot \hat{\textbf{n}}$$ is ***positive*** for an ***outgoing*** flow (outflow) and ***negative*** for an ***incoming*** flow (inflow).

## Statement of theorem

Moving on, let $B$ be an extensive property of the system such as energy, momentum, etc. We can define an intensive property by taking the amount of $B$ per unit mass, i.e.:

$$\beta = \frac{dB}{dm}$$

such that the "total" amount of $B$ in a general control volume is:

$$B_{CV} = \int_{V} \beta dm = \int_{V} \beta \rho d \mathcal{V} $$

Now, if we consider the possibility of having changes with respect to the control volume, we have ***flow terms***:

$$\int_{\text{surf}} \beta \rho (\textbf{V}\cdot \hat{\textbf{n}})dA $$

and the change of $\beta$ within the control volume with respect to time:

$$\frac{d}{dt}\left( \int_{V} \beta \rho d\mathcal{V} \right)$$

The time derivative of any extensive property of the system is given by **Reynold's transport theorem**:
\begin{equation} \frac{dB}{dt} = \frac{d}{dt}\left( \int_{V} \beta \rho d\mathcal{V} \right) + \int_{\text{surf}} \beta \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation}

Schematically:

$$\text{Change in } B = (\text{Change within CV}) + (\text{Outgoing Flow}) - (\text{Incoming flow}) $$

By applying Reynold's transport theorem for different quantities $B$, we can derive useful relationships.

### One-dimensional case

Suppose the inlets/outlets are one-dimensional. Reynold's transport theorem simplifies to a very useful form:

$$ \frac{dB}{dt} = \frac{d}{dt} \left( \int_{V}\beta dm \right) +  \left( \sum_{i} \beta_{i} \dot{m}_{i}\right)_{\text{out}} - \left( \sum_{j} \beta_{j} \dot{m}_{j}\right)_{\text{in}} $$

where the summations go over every inlet and outlet.
