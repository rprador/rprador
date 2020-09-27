---
mathjax: true
title: Differential Relations for Fluid Flow
---
{% include navigation.html %}
{% include mathjax.html %}

# Differential Relations for Fluid Flow

Rather than working with integrals over control volumes and control surfaces, fluid flow can instead be modelled through differential equations.

## A Few Definitions

For a fluid velocity vector $\textbf{V}(\textbf{r}, t) = u\hat{\textbf{x}} + v\hat{\textbf{y}} + w\hat{\textbf{z}}$, the acceleration vector is given by

$$ \textbf{a}(\textbf{r}, t) = \frac{d\textbf{V}}{dt} = \frac{\partial \textbf{V}}{\partial t} + \sum_{i} \frac{\partial \textbf{V}}{\partial x_{i}} =  \frac{\partial \textbf{V}}{\partial t} + (\textbf{V} \cdot \nabla)\textbf{V} $$
