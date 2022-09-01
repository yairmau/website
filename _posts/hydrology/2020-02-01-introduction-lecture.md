---
toc: true
layout: post
title: Introduction - lecture
categories: [markdown]
toc: true
tags: [hydrology]
---

## Sources

**Sources used**:

{% cite USGS2019howmuchwater %}
{% cite USGS2019waterschool %}
{% cite margulis2019introduction %}


## How much water is there? Where?

<iframe width="560" height="315" src="https://www.youtube.com/embed/2ObMyytxLz8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

{% figure [caption:"Source: [usgs.gov](https://www.usgs.gov/special-topic/water-science-school/science/how-much-water-there-earth)"] %}
![](/website/archive/hydrology/hydrology_figures/all-the-worlds-water.jpg)
{% endfigure %}

{% figure [caption:"Source: [usgs.gov](https://www.usgs.gov/media/images/distribution-water-and-above-earth)"] %}
![](/website/archive/hydrology/hydrology_figures/EarthsWater-BarChart.png)
{% endfigure %}



## The water cycle

![](/website/archive/hydrology/hydrology_figures/water-cycle.jpg "Source: https://www.usgs.gov/media/images/water-cycle-natural-water-cycle")

## Global water distribution

| Water source                         | Volume (km$^3$) | % of freshwater | % of total water |
|:--------------------------------------|-----------------------------------|-----------------------|------------------------|
| Oceans, Seas, & Bays                 | 1,338,000,000                     | --                    | 96.54                  |
| Ice caps, Glaciers,<br>& Permanent Snow | 24,064,000                        | 68.7                  | 1.74                   |
| Groundwater                          | 23,400,000                        | --                    | 1.69                   |
|$\quad$Fresh                            | 10,530,000                        | 30.1                  |   0.76                 |
|$\quad$Saline                           | 12,870,000                        | --                    |   0.93                 |
| Soil Moisture                        | 16,500                            | 0.05                  | 0.001                  |
| Ground Ice<br>& Permafrost              | 300,000                           | 0.86                  | 0.022                  |
| Lakes                                | 176,400                           | --                    | 0.013                  |
|$\quad$Fresh                            | 91,000                            | 0.26                  | 0.007                  |
|$\quad$Saline                           | 85,400                            | --                    | 0.006                  |
| Atmosphere                           | 12,900                            | 0.04                  | 0.001                  |
| Swamp Water                          | 11,470                            | 0.03                  | 0.0008                 |
| Rivers                               | 2,120                             | 0.006                 | 0.0002                 |
| Biological Water                     | 1,120                             | 0.003                 | 0.0001                 |

\* (Percents are rounded, so will not add to 100)  
[https://www.usgs.gov/special-topic/water-science-school/science/fundamentals-water-cycle](https://www.usgs.gov/special-topic/water-science-school/science/fundamentals-water-cycle)

## Energy drives the hydrologic cycle

> A key aspect of the hydrologic cycle is the fact that it is driven by energy inputs (primarily from the sun). At the global scale, the system is essentially closed with respect to water; negligible water is entering or leaving the system. In other words, there is no external forcing in terms of a water flux. Systems with no external forcing will generally eventually come to an equilibrium state. So what makes the hydrologic cycle so dynamic? The solar radiative energy input, which is external to the system, drives the hydrologic cycle. Averaged over the globe, 342 W m$^{-2}$ of solar radiative energy is being continuously input to the system at the top of the atmosphere. This energy input must be dissipated, and this is done, to a large extent, via the hydrologic cycle. Due to this fact, the study of hydrology is not isolated to the study of water storage and movement, but also must often include study of energy storage and movements.

Margulis, 2017, "Introduction to Hydrology"

## Components of the water cycle

### Water storage in oceans

### Evaporation / Sublimation

Evaporation $\longrightarrow$ cooling

{% figure [caption:"Source: [hk-phy.org](http://www.hk-phy.org/contextual/heat/cha/evapo02_e.html)"] %}
![](/website/archive/hydrology/hydrology_figures/evaporation_1.gif)
{% endfigure %}

{% figure [caption:"Source: [courses.lumenlearning.com](https://courses.lumenlearning.com/cheminter/chapter/evaporation/)"] %}
![](/website/archive/hydrology/hydrology_figures/evaporation_2.png)
{% endfigure %}

{% figure [caption:"Source: [engineeringinsider.org](https://engineeringinsider.org/cooling-tower-types/)"] %}
![](/website/archive/hydrology/hydrology_figures/cooling-tower.png)
{% endfigure %}

{% figure [caption:"Source: [slideplayer.com](https://slideplayer.com/slide/7418126/)"] %}
![](/website/archive/hydrology/hydrology_figures/evaporation_slide0.jpg)
{% endfigure %}

{% figure [caption:"Source: [slideplayer.com](https://slideplayer.com/slide/7418126/)"] %}
![](/website/archive/hydrology/hydrology_figures/evaporation_slide1.jpg)
{% endfigure %}

{% figure [caption:"Source: [slideplayer.com](https://slideplayer.com/slide/7418126/)"] %}
![](/website/archive/hydrology/hydrology_figures/evaporation_slide2.jpg)
{% endfigure %}

### Evapotranspiration

{% figure [caption:"Source: [eschooltoday.com/water-cycle](http://www.eschooltoday.com/water-cycle/what-is-transpiration-and-evapotranspiration.html)"] %}
![](/website/archive/hydrology/hydrology_figures/evapotranspiration1.jpg)
{% endfigure %}

### Water storage in the atmosphere

Cumulonimbus cloud over Africa
{% figure [caption:"Source: [Wikimedia](https://commons.wikimedia.org/wiki/File:Cumulonimbus_Cloud_over_Africa_%28color%29.jpg)"] %}
![](/website/archive/hydrology/hydrology_figures/cumulonimbus.jpg)
{% endfigure %}

Picture of cumulonimbus taken from the International Space Station, over western Africa near the Senegal-Mali border.

If all of the water in the atmosphere rained down at once, it would only cover the globe to a depth of 2.5 centimeters.

$$
\begin{align}
\text{amount of water in the atmosphere} & \qquad V = 12\, 900\, \text{km}^3 \\
\text{surface of Earth} & \qquad S = 4 \pi R^2;\quad R=6371\,\text{km}\\
& \qquad V = S \times h \\
\text{height} & \qquad h = \frac{V}{S} \simeq 2.5\,\text{cm}
\end{align}
$$

Try to calculate this yourself, and click on the button below to check how to do it.

{% capture water_code %}
```python
# amount of water in the atmosphere
V = 12900 # km^3
# Earth's radius
R = 6371 # km
# surface of Earth = 4 pi Rˆ2
S = 4 * 3.141592 * R**2
# Volume: V = S * h, therefore
# height
h = V / S # in km
h_cm = h * 1e5 # in cm
print(f"The height would be ~ {h_cm:.1f} cm")
```
{% endcapture %}

<a href="javascript:void(0);"
   onClick="toggle_icon_show_content('water_in_atmosphere',
                                     'water_in_atmosphere_icon')">
   Toggle Code <i class="fas fa-plus-square"
             id='water_in_atmosphere_icon'></i>
</a>&emsp;
<div id="water_in_atmosphere" style="display:none; font-family:monospace;">
{{ water_code | markdownify }}
</div>


### Condensation

### Precipitation

{% figure [caption:"Source: [usgs.gov](https://www.usgs.gov/special-topic/water-science-school/science/rain-and-precipitation)"] %}
![](/website/archive/hydrology/hydrology_figures/rain-burst1.jpg)
{% endfigure %}

|                   |   Intensity   (cm/h)  |   Median diameter   (mm)  |   Velocity of fall   (m/s)  |   Drops s$^{-1}$ m$^{-2}$  |
|:-------------------|--------------------------|------------------------------------|---------------------------------------|----------------------------------------|
|   Fog             |   0.013                  |   0.01                             |   0.003                               |   67,425,000                           |
|   Mist            |   0.005                  |   0.1                              |   0.21                                |   27,000                               |
|   Drizzle         |   0.025                  |   0.96                             |   4.1                                 |   151                                  |
|   Light rain      |   0.10                   |   1.24                             |   4.8                                 |   280                                  |
|   Moderate rain   |   0.38                   |   1.60                             |   5.7                                 |   495                                  |
|   Heavy rain      |   1.52                   |   2.05                             |   6.7                                 |   495                                  |
|   Excessive rain  |   4.06                   |   2.40                             |   7.3                                 |   818                                  |
|   Cloudburst      |   10.2                   |   2.85                             |   7.9                                 |   1,220                                |


Source: [usgs.gov](https://www.usgs.gov/special-topic/water-science-school/science/precipitation-and-water-cycle)

### Water storage in ice and snow

{% figure [caption:"Source: [usgs.gov](https://www.usgs.gov/special-topic/water-science-school/science/ice-snow-and-glaciers-and-water-cycle)"] %}
![](/website/archive/hydrology/hydrology_figures/iceland-summer.jpg)
{% endfigure %}

{% figure [caption:"Source: [usgs.gov](https://www.usgs.gov/special-topic/water-science-school/science/ice-snow-and-glaciers-and-water-cycle)"] %}
![](/website/archive/hydrology/hydrology_figures/iceland-winter.jpg)
{% endfigure %}

### Snowmelt runoff to streams

### Surface runoff

{% figure [caption:"Source: [phys.org](https://phys.org/news/2016-08-choices-effects-runoff-productivity.html)"] %}
![](/website/archive/hydrology/hydrology_figures/runoff-field.jpg)
{% endfigure %}

{% figure [caption:"Source: [melabes.co.il](https://www.melabes.co.il/news/51773)"] %}
![](/website/archive/hydrology/hydrology_figures/runoff-city.jpg)
{% endfigure %}

### Streamflow

The Mississippi river basin is very large
{% figure [caption:"Source: [images.app.goo.gl](https://images.app.goo.gl/N9N4MsoNUy39dzCb6)"] %}
![](/website/archive/hydrology/hydrology_figures/mississippi-watershed.gif)
{% endfigure %}

The Amazon river basin is **Huge**
{% figure [caption:"Source: [amazonwaters.org](https://amazonwaters.org/basins/)"] %}
![](/website/archive/hydrology/hydrology_figures/amazon-basin.jpg)
{% endfigure %}

{% figure [] %}
![](/website/archive/hydrology/hydrology_figures/amazon-basin-us.png)
{% endfigure %}

### Lakes and rivers

{% figure [caption:"Source: [dreamstime.com](https://www.dreamstime.com/world-map-africa-egypt-libya-ethiopia-arabia-mauritania-nigeria-somalia-namibia-tanzania-madagascar-geographic-xxl-chart-image154799901)"] %}
![](/website/archive/hydrology/hydrology_figures/rivers-africa.png)
{% endfigure %}

Lake Malawi
{% figure [caption:"Source: [images.app.goo.gl](https://images.app.goo.gl/8f4ikUgp4DnLAw1w6)"] %}
![](/website/archive/hydrology/hydrology_figures/lake-malawi.jpg)
{% endfigure %}


{% figure [caption:"Source: [telegraph.co.uk](https://www.telegraph.co.uk/travel/destinations/africa/malawi/articles/A-family-holiday-in-Lake-Malawi-zen-and-the-art-of-paddleboarding/)"] %}
![](/website/archive/hydrology/hydrology_figures/lake-malawi2.jpg)
{% endfigure %}

### Infiltration

{% figure [caption:"Source: [sumagroulx.com](http://sumagroulx.com/water-infiltration/)"] %}
![](/website/archive/hydrology/hydrology_figures/infiltration.jpg)
{% endfigure %}

### Groundwater storage

{% figure [caption:"Source: [usgs.gov](https://www.usgs.gov/media/images/groundwater-area-underground-where-openings-are-full-water)"] %}
![](/website/archive/hydrology/hydrology_figures/groundwater.jpg)
{% endfigure %}

{% figure [caption:"Source: [modernfarmer.com](https://modernfarmer.com/2015/07/ogallala-aquifer-depletion/)"] %}
![](/website/archive/hydrology/hydrology_figures/ogallala_aquifer_usgs.jpg)
{% endfigure %}

{% figure [caption:"Source: [Wikimedia](https://commons.wikimedia.org/wiki/File:High_plains_fresh_groundwater_usage_2000.svg)"] %}
![](/website/archive/hydrology/hydrology_figures/ogallala_aquifer_wiki.png)
{% endfigure %}

Center Pivot irrigation in Nebraska taps the Ogallala Aquifer.
{% figure [caption:"Source: [nebraskaeducationonlocation.org](https://nebraskaeducationonlocation.org/natural-attractions/ogallala-aquifer/)"] %}
![](/website/archive/hydrology/hydrology_figures/groundwater-ogallala-aquifer.jpg)
{% endfigure %}

### Groundwater flow and discharge

{% figure [caption:"Source: [usgs.gov](https://www.usgs.gov/media/images/conceptual-groundwater-flow-diagram)"] %}
![](/website/archive/hydrology/hydrology_figures/groundwater-flow-diagram.jpg)
{% endfigure %}

{% figure [caption:"Source: [wellwater.oregonstate.edu](http://wellwater.oregonstate.edu/groundwater-movement)"] %}
![](/website/archive/hydrology/hydrology_figures/groundwater-discharge.gif)
{% endfigure %}

{% figure [caption:"Source: [researchgate.net](https://www.researchgate.net/figure/Principal-pathways-for-submarine-groundwater-discharge-to-the-coastal-ocean-including_fig1_274590439)"] %}
![](/website/archive/hydrology/hydrology_figures/groundwater-discharge-submarine.png )
{% endfigure %}

### Spring

Ein Gedi
{% figure [caption:"Source: [haaretz.com](https://www.haaretz.com/israel-news/travel/seven-cool-natural-springs-of-israel-1.5388627)"] %}
![](/website/archive/hydrology/hydrology_figures/spring-ein-gedi.png)
{% endfigure %}

{% figure [caption:"Source: [usgs.gov](https://www.usgs.gov/media/images/water-flowing-underground-can-find-openings-back-land-surface)"] %}
![](/website/archive/hydrology/hydrology_figures/spring-Thousand-Springs-Idaho.png)
{% endfigure %}

## References

{% bibliography --cited %}


<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>

<script type="text/javascript">
function toggle_icon_show_content(Show_Hide_Id,Icon_Id) {
    $("#"+Icon_Id).toggleClass('fa-plus-square fa-minus-square')
    $("#"+Show_Hide_Id).slideToggle('slow');
}
</script>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>


