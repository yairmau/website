---
toc: true
layout: post
title: Streamflow - lecture
categories: [markdown]
toc: true
tags: [hydrology]
---

## Sources

**Sources used**:

{% cite dingman2015physical %}  
{% cite ward2003environmental %}

## Watershed - אגן היקוות

{% cite dingman2015physical %}
![](/website/archive/hydrology/hydrology_figures/dingman-figure10.3.png)

![](/website/archive/hydrology/hydrology_figures/watershed-boundaries.jpg)

{% cite dingman2015physical %}
![](/website/archive/hydrology/hydrology_figures/dingman-figure10.5.png)

Watershed response:
* The volume of water appearing in the apparent response hydrograph for a given event is usually only a fraction (often a very small fraction) of the total input. The remainder of the water input ultimately leaves the watershed as: (1) evapotranspiration; (2) streamflow that occurs so long after the event that it cannot be associated with that event; or (3) ground-water outflow from the watershed.
* The water identified as the response to a given event may originate on only a fraction of the watershed; this fraction is called the contributing area.
* The extent of the contributing area may vary from event to event and during an event.
* At least some of the water identified as the response to a given event may be “old water” that entered the watershed in a previous event.

## Base flow separation

{% cite ward2003environmental %}
![](/website/archive/hydrology/hydrology_figures/ward-figure5.11.png)

### Base flow
Base flow is the portion of streamflow that is presumed to have entered the watershed in previous events and to be derived from persistent, slowly varying sources. (Ground water is usually assumed to be the main, if not the only, such source.)
### Event flow
Event flow (also called direct runoff, storm runoff, quick flow, or storm flow) is considered to be the direct response to a given water-input event.

### Total flow

Total flow rate at any instant $q(t)$ is the sum of event-flow rate $q^*(t)$ and base-flow rate $q_{BF}$(t):

$$
q(t) = q^*(t) + q_{BF}(t)
$$

### Attention!
Graphical flow separation techniques are heuristic
and have no direct scientific basis.

## Urbana, IL

![](/website/archive/hydrology/hydrology_figures/urbana-IL-map.png)

### Hyetograph, Hydrograph
![](/website/archive/hydrology/hydrology_figures/urbana_pq.png)

### Notation
![](/website/archive/hydrology/hydrology_figures/dingman-box10.1.png)

### Base flow separation
![](/website/archive/hydrology/hydrology_figures/urbana_q_qstar.png)

### Effective precipitation = effective discharge

$$
P^* = Q^*
$$

![](/website/archive/hydrology/hydrology_figures/urbana_pstar_qstar.png)
![](/website/archive/hydrology/hydrology_figures/dingman-figure10.49.png)

### Time lags
![](/website/archive/hydrology/hydrology_figures/dingman-figure10.12.png)
![](/website/archive/hydrology/hydrology_figures/dingman-table10.2.png)
![](/website/archive/hydrology/hydrology_figures/urbana_lags.png)

It is commonly assumed that $T_{LPC} \simeq 0.60 \cdot T_c$, where $T_c$ is the time of concentration, i.e., the time it takes water to travel from the hydraulically most distant part of the contributing area to the outlet.

<!-- ### response time and centroid lag

Dingman, page 474

Watershed Size: Larger watersheds have larger T*, other things equal. Analyses of large floods by Holtan and Overton (1963) indicated that T* is strongly related to drainage area; however, the relationship varies from region to region, presumably largely because of differences in watershed geology, soils, and topography.
Soils and Geology: Water moves fastest toward streams as overland flow and slowest as subsurface flow (as discussed more fully later in this chapter). Thus watersheds with low surface hydraulic conductivities (e.g., clay soils), where less infiltration and more overland flow occur, should have smaller T* than those with higher conductivities (e.g., sandy soils). If flow paths are predominantly in the subsurface, watersheds with higher hydraulic conductivities will have smaller values of T*.
Slope: Steeper slopes should be associated with faster surface and subsurface water movement and hence smaller T*.
Land Use: In general, watersheds with heavy vegetation, especially forests, have permeable surface soils that allow rapid infiltration and subsurface flow to streams, resulting in larger T*. In contrast, sparsely vegetated watersheds tend to have lower T* because their lower surface permeability makes
Figure 10.16 Response, q*, of linear watershed with T*=5hrto1unitofinput, P*, in 1 hr. Input rate
p* = 1 unit/hr.
overland flow more common. Watersheds with intensive urbanization (more impermeable areas and storm sewers) generally have faster water movement and smaller T*.
Watershed Wetness: As seen in section 10.2.3.2, the wetness of the watershed at the time of a rainfall event (antecedent condition) usually has a significant influence on the connectivity of surface and subsurface flow paths and the extent of the contributing area, so that a given watershed will have a smaller T* when wet than when drier. The physical relations underlying this are discussed in section 10.4.
In the linear-watershed model the centroid lag, TLC, is equal to T*, regardless of the timing of inputs. Thus if the timing and amounts of effective water input and output can be determined, average TLC would appear to be the best estimate of the characteristic response time for a given watershed.

-->

The centroid is a weighted-average time, each time instant is multiplied by the amount of flow in that instant.

Time of precipitation centroid:

$$
t_{pc} = \frac{\displaystyle \sum_{i=1}^n p_i^* \cdot t_i}{P^*}
$$

Time of streamflow centroid:

$$
t_{qc} = \frac{\displaystyle \sum_{i=1}^n q_i^* \cdot t_i}{Q^*}
$$

## References

{% bibliography --cited %}