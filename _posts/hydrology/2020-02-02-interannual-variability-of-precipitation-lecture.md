---
toc: true
layout: post
title: Interannual variability of precipitation
categories: [markdown]
toc: true
tags: [hydrology]
---


![](/website/archive/hydrology/hydrology_figures/monthly_tel_aviv_1940-1999.png)

## hydrological year

A time period of 12 months for which precipitation totals are measured. The hydrological year is designated by the calendar year in which it **ends**.  
Let's define the hydrological year for Tel Aviv from 1 October to 30 September.

האם אקלים הגשם שלנו משתנה
<iframe width="560" height="315" src="https://www.youtube.com/embed/v0uNpj03Rk4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

![](/website/archive/hydrology/hydrology_figures/annual_tel_aviv_with_mean.png)

![](/website/archive/hydrology/hydrology_figures/histogram_tel_aviv_with_mean_and_std.png)

## coefficient of variation

$\langle{P}\rangle=$ average precipitation  
$\sigma=$ standard deviation

$$CV = \frac{\sigma}{\langle{P}\rangle}$$

Assuming that the inter-annual distribution is a gaussian: 67% of the time, rainfall will vary +/- 30% from its long term average in Tel Aviv.

Precipitation averages are [usually calculated for time intervals of 30 years](https://www.ncdc.noaa.gov/news/defining-climate-normals-new-ways).

![](/website/archive/hydrology/hydrology_figures/mean_tel_aviv_2_windows.png)

![](/website/archive/hydrology/hydrology_figures/mean_tel_aviv_4_windows.png)

{% capture code_to_plot %}
```python
import altair as alt
import pandas as pd

df = pd.read_csv("TEL AVIV READING_monthly.csv", sep=",")
# make 'DATE' the dataframe index
df['DATE'] = pd.to_datetime(df['DATE'])
df = df.set_index('DATE')

df_year_all = df['PRCP'].resample('A-SEP').sum().to_frame()  # annual frequency, anchored end of September
df_year_all.columns = ['rain (mm)'] # rename 'PRCP' column to 'rain (mm)'
df_year = df_year_all.iloc[:-1]  # exclude last row

# Altair only recognizes column data; it ignores index values.
# You can plot the index data by first resetting the index
# I know that I've just made 'DATE' the index, but I want to have this here nonetheless so I can refer to this in the future
source = df_year.reset_index()
brush = alt.selection(type='interval', encodings=['x'])

# T: temporal, a time or date value
# Q: quantitative, a continuous real-valued quantity
# https://altair-viz.github.io/user_guide/encoding.html#encoding-data-types
bars = alt.Chart().mark_bar().encode(
    x=alt.X('DATE:T', axis=alt.Axis(title='date')),
    y=alt.Y('rain (mm):Q',  axis=alt.Axis(title='annual precipitation (mm) and average')),
    opacity=alt.condition(brush, alt.OpacityValue(1), alt.OpacityValue(0.2)),
).add_selection(
    brush
).properties(
    title='Select year range and drag for rolling average of annual precipitation in Tel Aviv'
).properties(
    width=600,
    height=400
)

line = alt.Chart().mark_rule(color='orange').encode(
    y='mean(rain (mm)):Q',
    size=alt.SizeValue(3)
).transform_filter(
    brush
)

alt.layer(bars, line, data=source)
```
{% endcapture %}

<a href="javascript:void(0);"
   onClick="toggle_icon_show_content('code_to_plot',
                                     'code_to_plot_icon')">
   Toggle Code <i class="fas fa-plus-square"
             id='code_to_plot_icon'></i>
</a>&emsp;
<div id="code_to_plot" style="display:none; font-family:monospace;">
{{ code_to_plot | markdownify }}
</div>




![](/website/archive/hydrology/hydrology_figures/rolling_average_tel_aviv.png)



<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>

<script type="text/javascript">
function toggle_icon_show_content(Show_Hide_Id,Icon_Id) {
    $("#"+Icon_Id).toggleClass('fa-plus-square fa-minus-square')
    $("#"+Show_Hide_Id).slideToggle('slow');
}
</script>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>

























