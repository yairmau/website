---
layout: page-no-title-toc
title: Colors
address: '[home](/)/[more](/more)/colors'
before: <i class="fas fa-palette fa-fw svv" aria-hidden="true"></i>
toc: true
---

## Default Matplotlib colormaps

[Click Here](https://matplotlib.org/2.0.2/users/colormaps.html)  
[Colormap Reference](https://matplotlib.org/stable/gallery/color/colormap_reference.html?highlight=colormaps)

![](https://matplotlib.org/2.0.2/_images/lightness_01.png)

## Matplotlib colormap tricks

[Click Here](https://matplotlib.org/stable/tutorials/colors/colormapnorms.html?highlight=colormaps)

![](https://matplotlib.org/stable/_images/sphx_glr_colormapnorms_002_2_0x.png)

## Lightning Design System

[Click Here](https://www.lightningdesignsystem.com/guidelines/charts/#Chart-Color)

<table style="border:0;">
  <tr>
    <td><img src="https://www.lightningdesignsystem.com/assets/images/guidelines/charts/586-image1.png"></td>
    <td><img src="https://www.lightningdesignsystem.com/assets/images/guidelines/charts/586-image2.png"></td>
  </tr>
</table>

<!-- ![](https://www.lightningdesignsystem.com/assets/images/guidelines/charts/586-image1.png) ![](https://www.lightningdesignsystem.com/assets/images/guidelines/charts/586-image2.png) -->


## Hayk An’s color scale generator

Make your colormap in **seconds**  
[Click Here](https://hihayk.github.io/scale/#4/6/50/80/-51/67/20/14/1D9A6C/29/154/108/white)

![](/website/archive/colors/Hayk-An-generator.png)

## Coolors

Color palette generator. Copy #hex color in seconds.  
[Gradient](https://coolors.co/palettes/popular/gradient), [Monochromatic](https://coolors.co/palettes/popular/monochromatic),
[Click Here](https://coolors.co)

![](/website/archive/colors/coolors.png)

## Color Pals

Roni Kaufman's extremely pleasing palettes.  
[Click Here](https://ronikaufman.github.io/color_pals/)

![](/website/archive/colors/base-palette.png)

## Wes Anderson Palettes

[Click Here](https://wesandersonpalettes.tumblr.com)

![](https://64.media.tumblr.com/300310dd5e503f51b0b875e05db79791/tumblr_o6r7oiHYiI1tvvqeko1_500.jpg)

## Palettable

Color palettes for Python.  
[Click Here](https://jiffyclub.github.io/palettable/)

![](https://jiffyclub.github.io/palettable/colorbrewer/diverging/img/BrBG_11_continuous.png)  
![](https://jiffyclub.github.io/palettable/colorbrewer/diverging/img/BrBG_11_discrete.png)

```python
# how to import colormap
from palettable.colorbrewer.qualitative import Dark2_7
# how to retrieve color list
Dark2_7.hex_colors
```

## Image Color Picker

[Click Here](https://imagecolorpicker.com/en)  
Upload your own image, use a picture from the internet, load a whole website!

![](/website/archive/colors/imagecolorpicker.png)

## ColorBrewer 2.0

[Click Here](https://colorbrewer2.org/)

![](/website/archive/colors/colorbrewer2.png)

## Specifying Matplotlib Colors

xkcd, tableau, css  
[Click Here](https://matplotlib.org/stable/tutorials/colors/colors.html).
[List of named colors](https://matplotlib.org/stable/gallery/color/named_colors.html)

![](https://matplotlib.org/stable/_images/sphx_glr_colors_003_2_0x.png)

## Changing Lightness of Matplotlib Color

```python
import matplotlib.colors
import colorsys
import numpy as np
def add_lightness(color_name, L):
    """
    Receives a color name ("red", "tab:blue", "xkcd:green", etc),
    Returns RGB values of same color with lightness L added to it (can be negative too)
    """
    color_hls = colorsys.rgb_to_hls(*matplotlib.colors.to_rgb(color_name))
    new_color_hls = np.array(color_hls)
    new_color_hls[1] = new_color_hls[1] + L
    if new_color_hls[1] > 1.0: new_color_hls[1] = 1.0
    if new_color_hls[1] < 0.0: new_color_hls[1] = 0.0
    new_shade_rgb = colorsys.hls_to_rgb(*new_color_hls)
    return new_shade_rgb

add_lightness("gold", 0.1)
```


