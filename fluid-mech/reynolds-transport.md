---
mathjax: true
title: Statement of Reynold's transport theorem
---
{% include navigation.html %}
{% include mathjax.html %}
# Reynold's Transport Theorem
Studying fluids typically involve looking at specific "sections" of the fluid known as *control volumes*. This is not the only way to study a fluid but it is the most commonly introduced method.

![Arbitrary control volume](https://rprador.github.io/rprador/fluid-mech/figures/control-volume.PNG)
The above figure shows such a control volume for a fluid flowing through an arbitrary surface (a). The differential volume through a differential element $$dA$$ traces out a slanted parallelepiped (b) that is along the direction of the flow, which in this case is affected by the orientation of the elemental area. To account for this orientation, we simply take velocity $$\textbf{V}$$ projected onto the normal of the elemental area, $$\textbf{V} \cdot \hat{\textbf{n}}$$. The differential volume is, therefore, (think base times height):

$$d \mathcal{V} = (\textbf{V}\cdot \hat{\textbf{n}})dAdt$$

Dividing both sides by $$dt$$ and integrating gives the **volumetric flow rate** $$Q$$:

$$\begin{equation}Q=\int_{\text{surf}}(\textbf{V}\cdot \hat{\textbf{n}})dA\end{equation}$$

Lots of times, the geometry of the control volume is not complicated, so we can specify the integral more succinctly as:

$$Q = AV$$

Conveniently, we can multiply the volumetric flow rate by the fluid's density to obtain the **mass flow rate**:
$$\dot{m} = \int_{\text{surf}}\rho (\textbf{V}\cdot \hat{\textbf{n}})dA$$

<hr style="border: 1px solid black;" />



