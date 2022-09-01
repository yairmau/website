---
toc: true
layout: post
title: Infiltration - lecture
categories: [markdown]
toc: true
tags: [hydrology]
---

## Sources

**Sources used**:

{% cite hillel2003environmental %}
{% cite dingman2015physical %}
{% cite ward2003environmental %}


## Definitions

{% cite hillel2003environmental %}, figure 14.6, page 400
![](/website/archive/hydrology/hydrology_figures/hillel-introduction-to-environmental-soil-physics-figure14.6.png)

{% cite dingman2015physical %}, figure 8.13, page 360
![](/website/archive/hydrology/hydrology_figures/dingman-figure8.13.png)

{% cite dingman2015physical %}, figure 8.14, page 360
![](/website/archive/hydrology/hydrology_figures/dingman-figure8.14.png)

{% cite hillel2003environmental %}, figure 14.3, page 390
![](/website/archive/hydrology/hydrology_figures/hillel_introduction_soil_physics_figure14.3.png)


{% cite dingman2015physical %}, page 355
* The **water-input rate**, $w(t)$ [L T$^{-1}$], is the rate at which water arrives at the surface due to rain, snowmelt, or irrigation. A water-input event begins at time $t=0$ and ends at $t=T_w$.
* The **infiltration rate**, $f(t)$ [L T$^{-1}$], is the rate at which water enters the soil from the surface.
* The **infiltrability**, also called **infiltration capacity**, $f^*(t)$ [L T$^{-1}$], is the maximum rate at which infiltration could occur at any time; note that this changes during the infiltration event.
* The **depth of ponding**, $H(t)$ [L], is the depth of water standing on the surface.  


{% cite ward2003environmental %}, page 63, 64

Infiltration capacity of absorbent paper is low, there is much runoff
![](/website/archive/hydrology/hydrology_figures/ward_and_trimble_infiltration_capacity1.png)

Infiltration capacity of sponge is high, there is little runoff
![](/website/archive/hydrology/hydrology_figures/ward_and_trimble_infiltration_capacity2.png)

Infiltration capacity of the sponge is limited by the overlying layer with low permeability
![](/website/archive/hydrology/hydrology_figures/ward_and_trimble_infiltration_capacity3.png)

Infiltration capacity of the sponge is limited by the underlying layer
![](/website/archive/hydrology/hydrology_figures/ward_and_trimble_infiltration_capacity4.png)

<iframe width="560" height="315" src="https://www.youtube.com/embed/ego2FkuQwxc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

{% cite ward2003environmental %}, page 65
![](/website/archive/hydrology/hydrology_figures/ward-and-trimble-figure3.17-page65.png)

<br>
<hr class="my_hr">

## Darcy

Darcy's equation for vertical flow

$$
q = -K \frac{\partial H_\text{total}}{\partial z}
$$

where the total head $H_\text{total}=-H_\text{suction}-z_\text{depth}$, and
* $H_\text{suction}$ is the suction head (negative pressure head)
* $z_\text{depth}$ is the depth, points *downward*.

Substituting:

$$
q = K \frac{\partial H_\text{suction}}{\partial z} + K
$$

Substituting the above into the continuity equation

$$
\frac{\partial \theta}{\partial t} = \frac{\partial q}{\partial z}
$$

yields the Richards equation.

<br>
<hr class="my_hr">

## Richards

Richards equation:

$$
\frac{\partial \theta}{\partial t} = \frac{\partial}{\partial z}
\left[
K(\theta)
\frac{\partial H_\text{total}}{\partial z}
\right]
$$

Substituting $H_\text{total}=-H_\text{suction}-z_\text{depth}$ yields:

$$
\frac{\partial \theta}{\partial t} = \frac{\partial}{\partial z}
\left[
K(\theta)
\left(
\frac{\partial(-H_\text{suction} - z)}{\partial z}
\right)
\right]
$$


$$
\frac{\partial \theta}{\partial t} =
-
\underbrace{
\frac{\partial}{\partial z}
\left(
K(\theta)
\frac{\partial H_\text{suction}}{\partial z}
\right)
}
_{\text{matric}}
-
\underbrace{
\frac{\partial K(\theta)}{\partial z}
}
_{\text{gravitational}}
$$

### Short times

As the water starts to enter the relatively dry soil, the pressure differences in the water at the surface and in the soil are quite large and, as a result, the second term on the right is practically negligible compared to the first one.

$$
\frac{\partial \theta}{\partial t} =
-
\frac{\partial}{\partial z}
\left(
K(\theta)
\frac{\partial H}{\partial z}
\right)
$$

### Long times

As illustrated in the figure below (Davidson et al., 1963), after longer times of infiltration, the water content profile near the surface gradually becomes more uniform and it eventually assumes the satiation value, or $\theta\rightarrow \theta_0$; similarly, the pressure in the upper layers of the soil becomes gradually atmospheric, or $H \rightarrow 0$. Hence, their vertical gradients
<!-- ∂ θ /∂ z and ∂ H /∂ z both approach -->

$$
\frac{\partial\theta}{\partial z} \text{ and } \frac{\partial H_\text{suction}}{\partial z} \longrightarrow 0
$$

From Darcy's equation we have that

$$
q = K(\theta_0) = K_\text{sat}
$$

![](/website/archive/hydrology/hydrology_figures/davidson-1963-figure19.png)

<br>
<hr class="my_hr">

## Rainfall infiltration

Infiltration rate is equal to rainfal rate, at least at first.
If rainfall rate $w$ is lower than $K_\text{sat}$, than everything enters the soil, i.e., $f=K_\text{sat}$.
However, if $w>K_\text{sat}$, water content $\theta$ will increase at the surface, until it reaches $\theta_0$, and at that moment, called ponding time $t_p$,  water will begin to accumulate at the surface.

{% cite hillel2003environmental %}, figure 14.1, page 386
![](/website/archive/hydrology/hydrology_figures/hillel_introduction_soil_physics_figure14.1.png)

{% cite hillel2003environmental %}, figure 14.2, page 388
![](/website/archive/hydrology/hydrology_figures/hillel_introduction_soil_physics_figure14.2.png)

<br>
<hr class="my_hr">

## Horton equation

One of the most widely used models, developed by R.E. Horton (1939), considered to be the father of modern hydrology.

$$
f = f_c+(f_0-f_c)e^{-\beta t}
$$

* $f$: infiltration rate
* $f_c$: infiltration capacity at large $t$
* $f_0$: initial infiltration capacity
* $\beta$: best fit empirical parameter

**Advantages**  
* Simple equation
* Usually gives good fit to measured data because it is dependent on three parameters

**Disadvantages**
* This method has no physical significance, it is not based on any water transport mechanism
* Does not describe infiltration prior to ponding

<br>
<hr class="my_hr">

## Green & Ampt

{% cite dingman2015physical %}, figure 8.11, page 357
![](/website/archive/hydrology/hydrology_figures/dingman-figure8.11.png)


Assumptions:
* homogeneous soil, infinite depth (no water table)
* horizontal surface
* constant water head equal to zero is maintained at the surface
* uniform water content prior to wetting, $\theta(t=0,z)=\theta_0$
* moving front is characterized by a constant matric suction, $\psi_f$


{% cite dingman2015physical %}, page 370

This equation was developed under the scenario of constant rainfall or irrigation on an initially dry soil as a sharp wetting front (such as piston flow). Water penetrates a dry soil with a certain initial moisture content, and wets the layer to a saturated moisture content as it traverses deeper. The connection between soil moisture and infiltration rate is modeled in the Green-Ampt equation:

$$
f(t) = K_\text{sat}
\left[
1 + \frac{|\psi_f|\cdot \left( \phi - \theta_0 \right)}{F(t)}
\right]
$$

* $f(t)$: infiltration rate
* $F(t)$: cumulative infiltration rate, $F=\int f \text{ d}t$
* $\psi_f$: effective wetting-front suction
* $\phi$: soil porosity
* $\theta_0$:  initial soil water content

The same equation can be simply be rewritten as

$$f = \frac{A}{F} + B$$

where

$$
\begin{align}
A &= K_\text{sat}\cdot|\psi_f|\cdot \left( \phi - \theta_0 \right)\\
B &= K_\text{sat}
\end{align}
$$



The porosity $\phi$ and the saturated hydraulic conductivity $K_\text{sat}$ can be estimated from the soil texture. The wetting-front suction $\psi_f$ can be estimated using the Brooks-Corey parameters:
<!-- Dingman, page 371 -->

$$
|\psi_f| = \frac{2b+3}{2b+6}\cdot |\psi_{ae}|,
$$

where $\psi_{ae}$ is the air-entry pressure head.
Values for the parameters above can be found in this table:

![](/website/archive/hydrology/hydrology_figures/dingman_table7.4.png)

<br>
<hr class="my_hr">

## Best Fit, Least Squares Method

![](https://yairmau.com/images/python_figures/least-squares.png)

## References

{% bibliography --cited %}