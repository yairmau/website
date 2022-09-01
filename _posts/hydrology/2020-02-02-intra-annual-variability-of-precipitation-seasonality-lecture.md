---
toc: true
layout: post
title: Intra-annual variability of precipitation
categories: [markdown]
toc: true
tags: [hydrology]
---

![](/website/archive/hydrology/hydrology_figures/monthly_tel_aviv_london_bars.png)

Let's shift the months according the the hydrological year:  
![](/website/archive/hydrology/hydrology_figures/monthly_tel_aviv_london_bars_hydrological_year.png)

![](/website/archive/hydrology/hydrology_figures/radar_chart_tel_aviv_london.png)

## Seasonality Index, Walsh and Lawler (1981)

Source: [leddris.aegean.gr](http://leddris.aegean.gr/ses-parameters/293-rainfall-seasonality.html#:~:text=Rainfall%20seasonality%20index%20is%20a,in%20relation%20to%20water%20availability)

$R=$ mean annual precipitation  
$m_i=$ precipitation mean for month $i$  

$$ SI = \displaystyle \frac{1}{R} \sum_{n=1}^{n=12} \left| m_i - \frac{R}{12} \right| $$

| $SI$ | Precipitation Regime |
| --- | --- |
| <0.19 | Precipitation spread throughout the year |
| 0.20-0.39  | Precipitation spread throughout the year, but with a definite wetter season |
| 0.40-0.59  | Rather seasonal with a short dry season |
| 0.60-0.79  | Seasonal |
| 0.80-0.99  | Marked seasonal with a long dry season |
| 1.00-1.19      | Most precipitation in <3 months |

{% capture code_to_plot %}
```python

# import packages
import numpy as np
import pandas as pd
from calendar import month_abbr

# load data
month_numbers = np.arange(1,13)
month_names = [month_abbr[i] for i in month_numbers]
def monthly_mean(station_name, freq):
    # import daily data
    df = pd.read_csv(station_name + '_' + freq + '.csv', sep=",")
    # make 'DATE' the dataframe index
    df['DATE'] = pd.to_datetime(df['DATE'])
    df = df.set_index('DATE')
    # print(df.index[0], df.index[-1])
    if freq == 'daily':
        # resample data by month
        df_month = df['PRCP'].resample('M').sum()  # sum is labeled at the last day of the month 
        df_month = df_month/10                     # PRCP is given in tens of mm (see readme)
    if freq == 'monthly':
        df_month = df['PRCP']
    # calculate monthly mean
    monthly_mean = np.array([])  # empty array
    for m in month_numbers:      # cycle over months (1, 2, 3, etc)
        this_month_all_indices = (df_month.index.month == m)       # indices in df_month belonging to month m
        this_month_mean = df_month[this_month_all_indices].mean()  # this is the monthly mean
        monthly_mean = np.append(monthly_mean, this_month_mean)    # append
    # make new df and return it
    df_return = pd.DataFrame({'monthly rainfall (mm)':monthly_mean,
                              'month names':month_names,
                              'month number':month_numbers
                            })
    return df_return

# load monthly mean
df_london = monthly_mean("LONDON HEATHROW", 'monthly')
df_telaviv = monthly_mean("TEL AVIV READING", 'monthly')

#collapse-hide

def walsh_index(df):
    m = df["monthly rainfall (mm)"]
    R = df["monthly rainfall (mm)"].sum()
    SI = np.sum(np.abs(m-R/12)) / R
    return SI

london_index = walsh_index(df_london)
telaviv_index = walsh_index(df_telaviv)
print("Seasonality index (Walsh and Lawler, 1981)")
print(f"London: {london_index:.2f}")
print(f"Tel Aviv: {telaviv_index:.2f}")

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


![](/website/archive/hydrology/hydrology_figures/si_walsh_telaviv.png)
![](/website/archive/hydrology/hydrology_figures/si_walsh_london.png)









<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>

<script type="text/javascript">
function toggle_icon_show_content(Show_Hide_Id,Icon_Id) {
    $("#"+Icon_Id).toggleClass('fa-plus-square fa-minus-square')
    $("#"+Show_Hide_Id).slideToggle('slow');
}
</script>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>




