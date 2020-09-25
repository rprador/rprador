---
mathjax: true
title: Applications of Reynold's Transport Theorem
---
{% include navigation.html %}
{% include mathjax.html %}

# Applications of Reynold's Transport Theorem

The usefulness of the transport theorem is in its ability to find relations between the control volume and relevant properties. Below show such relations for various properties.

## Conservation of Mass

Recall that Reynold's transport theorem stated for an extensive property $B$ and its intensive form, $\beta = dB/dm$:

\begin{equation} \frac{dB}{dt} = \frac{d}{dt}\left( \int_{CV} \beta \rho d\mathcal{V} \right) + \int_{\text{CS}} \beta \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation}

Our choice for $B$ is the mass, so $B=m$ and $\beta=dm/dm=1$. Thus,

$$ \begin{align*} \left(\frac{dm}{dt}\right)_{\text{sys}} &= \frac{d}{dt}\left( \int_{CV} (1) \rho d\mathcal{V} \right) + \int_{\text{CS}} (1) \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \frac{d}{dt}\left( \int_{CV} \rho d\mathcal{V} \right) + \int_{\text{CS}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \int_{CV} \frac{\partial\rho}{\partial t} d\mathcal{V} + \int_{\text{CS}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{align*} $$

Mass conservation states explicitly that $dm/dt$ of the system is zero. Therefore:

\begin{equation} 0 = \int_{CV} \frac{\partial\rho}{\partial t} d\mathcal{V} + \int_{\text{CS}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation}

This is the most general form of the **conservation of mass** for a control volume. However, a few simplifications can be made with the right assumptions.

### Steady Flow

In the case of steady flow, the time dependence of the Reynold's transport theorem is taken to be zero. In other words, every time derivative vanishes. Hence, $\partial \rho /\partial t = 0$, and so:

$$ \int_{\text{CS}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA = 0 \;\;\;\; \text{(Steady flow)} $$

In the case that inlet/outlet surfaces are one-dimensional, the integral reduces to individual contributions $\rho_{i}A_{i}V_{i}$. This leads to the very simple relation:

$$ \sum_{i} (\dot{m}_{i})_{\text{in}} = \sum_{i} (\dot{m}_{i})_{\text{out}} \;\;\;\; \text{(1D Steady flow)} $$

However, if not then we have to calculated an integral for each inlet/outlet:

$$\dot{m} = \int_{\text{CS}} \rho (\textbf{V} \cdot \hat{\textbf{n}}) $$

### Incompressible Flow

By incompressible, we mean the change in density (time derivative here) is negligible. In other words, $\rho \approx$ constant. It is useful to know that although it is not general true that most fluids are incompressible, it is true that all liquids are ***nearly*** incompressible. Like from the case of steady flow, we therefore have:

$$ \begin{align*} 0 &= \int_{\text{CS}} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \rho \int_{\text{CS}} (\textbf{V}\cdot \hat{\textbf{n}})dA \\
&= \int_{\text{CS}} (\textbf{V}\cdot \hat{\textbf{n}})dA \end{align*} $$

For a general control surface, we have that the volumetric flow rate must be zero:

$$Q_{\text{CS}} = \int_{\text{CS}} (\textbf{V}\cdot \hat{\textbf{n}})dA = 0 \;\;\;\; \text{(Incompressible flow)}$$

If the inlets/outlets are one-dimensional:

$$ \sum Q_{\text{in}} = \sum Q_{\text{out}} \;\;\;\; \text{(1D Incompressible flow)}$$

where $Q = A_{i}V_{i}$.

## Newton's Second Law

The next extensive property that can be worked with is momentum. Then $\textbf{B} = \textbf{p}$ and $\beta = d\textbf{p}/dm = \textbf{V} $, where we are keeping track of the vector components. Substituting this into the general Reynold's transport theorem:

$$ \begin{equation}  \left(\frac{d\textbf{p}}{dt}\right)_{\text{sys}} = \sum_{i}\textbf{F}_{i} = \frac{d}{dt} \int_{\text{CV}} \textbf{V} \rho d\mathcal{V} + \int_{\text{CS}}\textbf{V} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation} $$

where Newton's second law has been used on the LHS. Since Newton's law was used, it should be noted that the reference frame of the control volume must be inertial, i.e. it is not accelerating. This equation is called the **linear momentum equation**.

In the case of one dimensional inlets/outlets, we have:

$$ \sum_{i}\textbf{F}_{i} = \frac{d}{dt} \int_{\text{CV}} \textbf{V} \rho d\mathcal{V} + \sum(\dot{m}_{i}\textbf{V}_{i})_{\text{out}} - \sum(\dot{m}_{i}\textbf{V}_{i})_{\text{in}} \;\;\;\; (\text{1D momentum flux}) $$

The label ***momentum flux*** refers to the momentum analogue for the mass flow rate:

$$ \dot{\textbf{M}}_{\text{CS}} = \int \textbf{V} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA $$

which in the one dimensional case with constant density is:

$$ \dot{\textbf{M}} = \dot{m}_{i}\textbf{V}_{i} $$

### Noninertial Frames

#### Time derivatives in rotating frames

Suppose we have a fixed inertial frame $S_{0}$ with coordinates $(x_{0}, y_{0}, z_{0})$. Let there be another frame $S$ with coordinates $(x, y, z)$ that shares an origin with $S_{0}$ and is rotating with angular velocity $\boldsymbol{\Omega}$. Let $Q$ be an arbitrary vector:

$$ \textbf{Q} = Q_{1}\hat{\textbf{e}}_{1} + Q_{2}\hat{\textbf{e}}_{2} + Q_{3}\hat{\textbf{e}}_{3} $$

where $\hat{\textbf{e}}\_{i}$ are unit vectors. The time derivative of $\textbf{Q}$ relative to the inertial fram $S_{0}$ is:

$$ \left(\frac{d\textbf{Q}}{dt}\right)_{S_{0}} $$

and the time derivative of $\textbf{Q}$ relative to the noninertial frame $S$ is:

$$ \left(\frac{d\textbf{Q}}{dt}\right)_{S} $$

Within the noninertial frame $S$, the unit vectors $\hat{\textbf{e}}_{i}$ are stationary, so that the time derivative is simply:

$$ \left(\frac{d\textbf{Q}}{dt}\right)_{S} = \sum_{i} \frac{dQ_{i}}{dt}\hat{\textbf{e}}_{i} $$

However, in the fixed inertial frame $S_{0}$, the unit vectors are rotating, so they undergo a change:

$$ \left(\frac{d\textbf{Q}}{dt}\right)_{S_{0}} = \sum_{i} \frac{dQ_{i}}{dt}\hat{\textbf{e}}_{i} + \sum_{i}Q_{i} \left( \frac{d\hat{\textbf{e}_{i}}}{dt} \right)_{S_{0}} $$

The second term on the RHS can be evaluated as (need to find proof somewhere of this):

$$ \frac{d\hat{\textbf{e}}}{dt} = \boldsymbol{\Omega} \times \hat{\textbf{e}} $$

Hence:

$$ \begin{align*} \left(\frac{d\textbf{Q}}{dt}\right)_{S_{0}} &= \sum_{i} \frac{dQ_{i}}{dt}\hat{\textbf{e}}_{i} + \sum_{i}Q_{i} (\boldsymbol{\Omega} \times \hat{\textbf{e}}) \\ 
&= \sum_{i} \frac{dQ_{i}}{dt}\hat{\textbf{e}}_{i} + \boldsymbol{\Omega} \times \sum_{i}Q_{i}\hat{\textbf{e}}_{i} \\
&= \sum_{i} \frac{dQ_{i}}{dt}\hat{\textbf{e}}_{i}  + \boldsymbol{\Omega} \times \textbf{Q} \end{align*} $$

Therefore, any time derivative of a vector within an inertial frame is equal to a time derivative in the noninterial frame plus a rotational effect $\boldsymbol{\Omega} \times \textbf{Q}$:

$$ \left(\frac{d\textbf{Q}}{dt}\right)_{S_{0}} = \left( \frac{d\textbf{Q}}{dt} \right)_{S}  + \boldsymbol{\Omega} \times \textbf{Q} $$

### Newton's second law in a rotating frame

With the results from above, we can easily derive the velocity and acceleration vectors in a rotating frame. Let the position of a fluid particle be $\textbf{r}$. The time derivative is:

$$ \left(\frac{d\textbf{r}}{dt}\right)_{S_{0}} = \left( \frac{d\textbf{r}}{dt} \right)_{S}  + \boldsymbol{\Omega} \times \textbf{r} $$

A second differentiation yields:

$$ \begin{align*} \left(\frac{d^{2}\textbf{r}}{dt^{2}} \right)_{S_{0}} &= \frac{d}{dt}\left[ \left( \frac{d\textbf{r}}{dt} \right)_{S}  + \boldsymbol{\Omega} \times \textbf{r} \right]_{S_{0}} \\
&= \frac{d}{dt}\left[ \left( \frac{d\textbf{r}}{dt} \right)_{S}  + \boldsymbol{\Omega} \times \textbf{r} \right]_{S} + \boldsymbol{\Omega}\times\left[ \left( \frac{d\textbf{r}}{dt} \right)_{S}  + \boldsymbol{\Omega} \times \textbf{r} \right] \\ 
&= \left( \frac{d^{2}\textbf{r}}{dt^{2}} \right)_{S} + \frac{d}{dt}\left[ \boldsymbol{\Omega}\times \textbf{r} \right]_{S} + \left\{ \boldsymbol{\Omega}\times \left( \frac{d\textbf{r}}{dt} \right)_{S} \right\} + \boldsymbol{\Omega}\times (\boldsymbol{\Omega} \times \textbf{r}) \\
&= \left( \frac{d^{2}\textbf{r}}{dt^{2}} \right)_{S} + \left( \frac{d\boldsymbol{\Omega}}{dt} \right)_{S} \times \textbf{r} + \boldsymbol{\Omega} \times \left( \frac{d\textbf{r}}{dt} \right)_{S} + \left\{ \boldsymbol{\Omega}\times \left( \frac{d\textbf{r}}{dt} \right)_{S} \right\} + \boldsymbol{\Omega}\times (\boldsymbol{\Omega} \times \textbf{r}) \end{align*} $$

where the second line is obtained from 

$$\left(\frac{d\textbf{Q}}{dt}\right)_{S_{0}} = \left( \frac{d\textbf{Q}}{dt} \right)_{S}  + \boldsymbol{\Omega} \times \textbf{Q} $$

Introducing the dot notation:

$$ \dot{\textbf{Q}} \equiv \left( \frac{d\textbf{Q}}{dt} \right)_{S} $$

We get:

$$ \left(\frac{d^{2}\textbf{r}}{dt^{2}} \right)_{S_{0}} = \ddot{\textbf{r}} + (\dot{\boldsymbol{\Omega}} \times \textbf{r}) + (\boldsymbol{\Omega} \times \dot{\textbf{r}}) + (\boldsymbol{\Omega}\times \dot{\textbf{r}}) + \boldsymbol{\Omega}\times (\boldsymbol{\Omega} \times \textbf{r}) $$

Or:

$$ \left(\frac{d^{2}\textbf{r}}{dt^{2}} \right)_{S_{0}} = \ddot{\textbf{r}} + (\dot{\boldsymbol{\Omega}} \times \textbf{r}) + 2(\boldsymbol{\Omega} \times \dot{\textbf{r}}) + \boldsymbol{\Omega}\times (\boldsymbol{\Omega} \times \textbf{r}) $$

In the inertial frame, therefore, Newton's second law reads:

$$ \begin{align*} \sum \textbf{F} &= m\left( \frac{d^{2}\textbf{r}}{dt^{2}} \right)_{S_{0}} \\
&= m\ddot{\textbf{r}} +  m(\dot{\boldsymbol{\Omega}} \times \textbf{r}) + 2m(\boldsymbol{\Omega} \times \dot{\textbf{r}}) + m\boldsymbol{\Omega}\times (\boldsymbol{\Omega} \times \textbf{r}) \end{align*} $$

Rearrangine and keeping in mind the antisymmetric property of cross products ($\textbf{a}\times\textbf{b} = -\textbf{b}\times \textbf{a}$):

$$ m\ddot{\textbf{r}} = \sum \textbf{F} + m(\textbf{r} \times \dot{\boldsymbol{\Omega}}) + 2m(\boldsymbol{\dot{\textbf{r}} \times \Omega}) + m(\boldsymbol{\Omega} \times \textbf{r})\times\boldsymbol{\Omega} \;\;\;\;  (\text{N.S.L Rotating Frame}) $$

Each term constitutes a "ficticious" force:

$$ \begin{align*} \text{Euler Force} &= m(\textbf{r} \times \dot{\boldsymbol{\Omega}}) \\
\text{Coriolis force} &= 2m(\boldsymbol{\dot{\textbf{r}} \times \Omega}) \\
\text{Centrifugal force} &= m(\boldsymbol{\Omega} \times \textbf{r})\times\boldsymbol{\Omega} \\ \end{align*} $$

Modifying equation (3) by subtracting the acceleration terms that show up above:

$$ \begin{equation} \sum \textbf{F} - \int_{\text{CV}}\textbf{a}_{\text{rel}} dm =  \frac{d}{dt} \int_{\text{CV}} \textbf{V} \rho d\mathcal{V} + \int_{\text{CS}}\textbf{V} \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation} $$

where $\textbf{a}\_{\text{rel}}$ are the accelerations from the Euler, Corioilis, and Centrifugal forces.

## Conservation of Energy

For this application, let $B = E$, the total energy, and $\beta = dE/dm \equiv e$ which is the energy per unit mass (or specific energy). We will assume the control volume is fixed and non-deformable.

$$ \frac{dE}{dt} = \frac{d}{dt}\left( \int_{CV} e \rho d\mathcal{V} \right) + \int_{\text{CS}} e \rho (\textbf{V}\cdot \hat{\textbf{n}})dA $$

From the first law of thermodynamics, $\dot{Q} - \dot{W} = \dot{E}$, where $\dot{Q}$ is the heat per unit time and $\dot{W}$ is the work per unit time. Therefore,

$$\dot{Q} - \dot{W} = \frac{d}{dt}\left( \int_{CV} e \rho d\mathcal{V} \right) + \int_{\text{CS}} e \rho (\textbf{V}\cdot \hat{\textbf{n}})dA $$ 

Note that the sign convention taken here is the physics/engineering one where heat added to the system is positive and work done by the system is also positive. From a chemistry perspective, the convention for work is flipped: work done by the system is negative, leading to $\dot{Q} + \dot{W}$. Just keep this in mind when referencing other sources.

Now, the (specific) energy can come from a variety of sources. For this discussion, we will only consider energy contributions from internal energy $u$, kinetic energy $\frac{1}{2}V^{2}$, and potential energy $gz$.

$$ e = u +\frac{1}{2}V^{2} + gz $$

Depending on the problem, it is possible to split up the heat and work into components:

$$ \dot{Q} = \begin{cases} \text{Convection} \\ \text{Conduction} \\ \text{Radiation} \end{cases}$$

and

$$ \dot{W} = \begin{cases} \text{Shaft}, \dot{W}_{s} \\ \text{Pressure}, \dot{W}_{p} \\ \text{Viscous Stress}, \dot{W}_{v} \\ \text{Other} \end{cases}$$

Other types of work, such as electromagnetic work, can be done as well but are ignored here. We will also consider the heat as a single quantity without splitting it. 

The rate of work done by the fluid on a shaft protruding from the control volume is called the **rate of shaft work** and is typically given within a problem, so we will leave it alone. The sign for this depends on the mechanism, i.e. positive for turbine, negative for a fan. 

The rate of work done by pressure forces at the surface is called the **rate of pressure work**. Recall that the power can is related to the force acting on an object with velocity $\textbf{V}$ as $\dot{W} = \textbf{F} \cdot \textbf{V}$. In the case of pressure forces, there is a normal stress due to pressure, $\sigma = p$. Hence:

$$ d\dot{W}_{p} = d\textbf{F}_{p} \cdot \textbf{V} = (\boldsymbol{\sigma} dA) \cdot \textbf{V} = p (\textbf{V} \cdot \hat{\textbf{n}}) dA $$

Integrating, we get the rate of work due to pressure forces (sometimes called **flow work**):

$$ \dot{W}_{p} = \int_{\text{CS}} p (\textbf{V} \cdot \hat{\textbf{n}}) dA $$

Similarly, the rate of work due to viscous stresses is:

$$ \dot{W}_{v} = -\int_{\text{CS}} \boldsymbol{\tau} \cdot \textbf{V} dA $$

where $\boldsymbol{\tau}$ is the stress on the surface. Depending on the problem, we have a few cases for this time of work:

$$ \begin{cases} \text{No-slip condition at surface} (\textbf{V}=0), &\dot{W}_{v} = 0 \\
\text{At inlet/outlet},  &\dot{W}_{v} \approx 0 \\ 
\text{At machine surface}, &\dot{W}_{\text{m. surf}} \rightarrow \dot{W}_{s} (\text{absorbed into term}) \end{cases} $$

The rate of work then is:

$$ \dot{W} = \dot{W}_{s} + \dot{W}_{p} + \dot{W}_{v} = \dot{W}_{s} + \int_{\text{CS}} p (\textbf{V} \cdot \hat{\textbf{n}}) dA - \int_{\text{CS}} \boldsymbol{\tau} \cdot \textbf{V} dA $$ 

The energy equation is:

$$ \begin{align*} \dot{Q} - \dot{W}_{s} - \dot{W}_{p} - \dot{W}_{v} &=  \frac{d}{dt}\left( \int_{CV} e \rho d\mathcal{V} \right) + \int_{\text{CS}} e \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \\ 
\dot{Q} - \dot{W}_{s} - \int_{\text{CS}} p (\textbf{V} \cdot \hat{\textbf{n}}) dA - \dot{W}_{v} &=  \frac{d}{dt}\left( \int_{CV} e \rho d\mathcal{V} \right) + \int_{\text{CS}} e \rho (\textbf{V}\cdot \hat{\textbf{n}})dA \\ 
\dot{Q} - \dot{W}_{s} - \dot{W}_{v} &=  \frac{d}{dt}\left( \int_{CV} e \rho d\mathcal{V} \right) + \int_{\text{CS}} e \rho (\textbf{V}\cdot \hat{\textbf{n}})dA + \int_{\text{CS}} p (\textbf{V} \cdot \hat{\textbf{n}}) dA \\ 
&=  \frac{d}{dt}\left( \int_{CV} e \rho d\mathcal{V} \right) + \int_{\text{CS}} (e \rho + p)(\textbf{V}\cdot \hat{\textbf{n}})dA \\
&=  \frac{d}{dt}\left( \int_{CV} e \rho d\mathcal{V} \right) + \int_{\text{CS}} (e + \frac{p}{\rho})\rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{align*} $$

Plugging in the energy terms, and noting that in the surface integral that: 

$$ e + \frac{p}{\rho} = u + \frac{1}{2}V^{2} + gz + \frac{p}{\rho} = (u + \frac{p}{\rho}) + \frac{1}{2}V^{2} + gz = h + \frac{1}{2}V^{2} + gz  $$

where $h$ is the (specific) enthalpy, we get:

$$  \begin{equation} \dot{Q} - \dot{W}_{s} - \dot{W}_{v} = \frac{d}{dt}\left( \int_{CV} (u + \frac{1}{2}V^{2} + gz) \rho d\mathcal{V} \right) + \int_{\text{CS}} (h + \frac{1}{2}V^{2} + gz)\rho (\textbf{V}\cdot \hat{\textbf{n}})dA \end{equation} $$

### Steady State

In steady state, the volume integral derivative vanishes, leaving

$$ \dot{Q} - \dot{W}_{s} - \dot{W}_{v} = \int_{\text{CS}} (h + \frac{1}{2}V^{2} + gz)\rho (\textbf{V}\cdot \hat{\textbf{n}})dA $$

#### Steady State + 1D Inlet/Outlet

The surface integral reduces to a sum over the number of inlets./outlets. In particular,

$$ \dot{Q} - \dot{W}_{s} - \dot{W}_{v} = \int_{\text{CS}} (h + \frac{1}{2}V^{2} + gz)\rho (\textbf{V}\cdot \hat{\textbf{n}})dA = \sum\left( h + \frac{1}{2}V^{2} + gz \right)_{\text{out}}\dot{m}_{\text{out}} -  \sum\left( h + \frac{1}{2}V^{2} + gz \right)_{\text{in}} \dot{m}_{\text{in}} $$

Note: it is possible to relate the mass flow rates using the conservation of mass continuity equation.

#### Steady State + 1D Inlet/Outlet + One Inlet, One Outlet

In this case, we have:

$$ \dot{Q} - \dot{W}_{s} - \dot{W}_{v} = \int_{\text{CS}} (h + \frac{1}{2}V^{2} + gz)\rho (\textbf{V}\cdot \hat{\textbf{n}})dA =  (h_{2} + \frac{1}{2}V_{2}^{2} + gz_{2}) \dot{m}_{2} -  (h_{1} + \frac{1}{2}V_{1}^{2} + gz_{1}) \dot{m}_{1} $$

From the continuity equation, the mass flow rates are equal, so $\dot{m}_{1} = \dot{m}_{1} = \dot{m} $. Therefore:

$$ \dot{Q} - \dot{W}_{s} - \dot{W}_{v} = \int_{\text{CS}} (h + \frac{1}{2}V^{2} + gz)\rho (\textbf{V}\cdot \hat{\textbf{n}})dA =  \left[ (h_{2} + \frac{1}{2}V_{2}^{2} + gz_{2}) -  (h_{1} + \frac{1}{2}V_{1}^{2} + gz_{1})\right] \dot{m} $$

Dividing through by $\dot{m}$ and denoting the (specific) heat and (specific) work as $q = \dot{Q}/\dot{m} = dQ/dm$ and $w = \dot{W}/\dot{m} = dW/dm$, respectively:

$$ q - w_{s} - w_{v} = \Delta\left( h + \frac{1}{2}V^{2} + gz \right)$$

where the $\Delta$ is the difference in values. Note: the dot notation is gone because unit-wise, the time dependence has been cancelled.

#### Steady State + 1D Inlet/Outlet + One Inlet, One Outlet (Head version)

As the steady state, 1D energy equation has units of energy per unit mass for each of its terms, dividing through by $g$ converts them all into units of length. These terms are termed ***heads***.

$$ \mathcal{h}_q - \mathcal{h}_{s} - \mathcal{h}_{v} = \Delta\left( \frac{u}{g} + \frac{p}{\rho g} + \frac{V^{2}}{2g} + z \right) $$ 

where $\mathcal{h}\_{q} = q/g, \mathcal{h}\_{s} = w\_{s}/g, \mathcal{h}\_{v} = w\_{s}/g$ are the head forms of the heat and work, $V^{2}/2g$ is the velocity head, and $p/\rho g$ is the pressure head. For clarity, the enthalpy was split back into its internal energy and pressure terms. Sometimes, the pressure head is written using the specific weight $\gamma = \rho g$ instead. 
