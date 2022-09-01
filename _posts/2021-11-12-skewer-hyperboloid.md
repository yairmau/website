---
toc: true
layout: post
title: Skewer Hyperboloid
description: When straight lines make a surprisingly pleasant curved surface
categories: [markdown]
toc: false
tags: [art, geek, frontpage]
image: https://lh3.googleusercontent.com/bSIT1Wx9m6EHOE1rEXAfqcg_w7RWkpusE7rFfIxnPCQrziwVkGV51cWHwdvFxaOPh62CP-1bDEqzi0A4rn85lVngaKIgtMp2Oi-TNKDj-fjFggYSwS3VYxR1bpT9NR1sOqYXRBEd3K8=w2400
---


![](https://lh3.googleusercontent.com/bSIT1Wx9m6EHOE1rEXAfqcg_w7RWkpusE7rFfIxnPCQrziwVkGV51cWHwdvFxaOPh62CP-1bDEqzi0A4rn85lVngaKIgtMp2Oi-TNKDj-fjFggYSwS3VYxR1bpT9NR1sOqYXRBEd3K8=w2400)

George Hart is again the hero of this project.
Go check out his [webpage](https://www.georgehart.com/skewers/skewer-hyperboloid.html) to see how to build this beautiful shape.
All you need to make the skewer hyperboloid is a bunch of skewers and thin elastic bands.

This is an easy project, and the end result is so fun to play with!
It is surprising how smoothly this shape morphes when you pull and push the skewers to change the angle, it's hard to explain, so you should definitely try it yourself 😁.
See [Annie Perkins's video](https://arbitrarilyclose.com/2020/05/11/mathartchallenge-day-55-hyperboloid-george-hart/) to get a better idea:

<iframe width="560" height="315" src="https://videopress.com/embed/1GgXbg78" frameborder="0" allowfullscreen></iframe>
<script src="https://videopress.com/videopress-iframe.js"></script>

The one thing I can add to George Hart's page is that after many weeks and months the elastic bands will dry out and break!
I gave a skewer hyperboloid to a friend, and one day he arrived at his office and found out that the whole thing had disintegrated overnight, and the skewers were all over the place.
I'm still looking for a suitable substitute to the elastic bands. It must be something flexible that enables us to play with the construction, and at the same time something durable...
I have not found yet the perfect material, if you have a suggestion please write to me.

I wanted my hyperboloid to last for a long time, so after the construction was done, I used super glue to fix the skewers in a particular angle.
Now I can't play with it, but at least it will not disintegrate overnight in a few months time (hopefully!).

![](https://lh3.googleusercontent.com/JOawpE_90tFO1wExDW7ntL5zuQjUc1MIF18RN-uX9Ll_CtS9Q0j8e0-_fX_tHwULwuRxScTcLljivn_jc-Lyycq9SJftYeEi1_flGS1AOlzu6CbKZJsAFsx0Cvd7oM3_piY26i9vtoY=w2400)

The mathematical name of this shape is "hyperboloid of one sheet", and its equation is


$$
\frac{x^2}{A^2} + \frac{y^2}{B^2} - \frac{z^2}{C^2} = 0.
$$

When $A=B$ the horizontal cross-sections are circles, just like in our construction.
The elastic bands effectively allow us to play with the parameter $C$, which controls how fast the hyperboloid grows sideways.
There is a wonderful widget in the [Interactive Gallery of Quadric Surfaces](https://nmd.pages.math.illinois.edu/quadrics/hyper1.html), its quite fun to play with.

To see how this curved surface can be made entirely out of straight lines, one can define the surface as the set of all [parametric curves](https://mathcurve.com/surfaces.gb/hyperboloid/hyperboloid1.shtml) of the kind

$$
\begin{align}
x &= A (\cos \theta - v \sin \theta)\\
y &= B (\sin \theta + v \cos \theta)\\
z &= C \varepsilon v.
\end{align}
$$

Substitute the parametric equations above into the equation of the paraboloid and see that they satisfy it.

There are actually two families of curves, for $\epsilon=\pm 1$.
I made a Mathematica plot of the two families of lines, in red ($\varepsilon=1$) and in blue ($\varepsilon=-1$), for ten $\theta$ values between 0 and $2\pi$.
It's easy to see that each family of lines swirls in a different direction.

![](/website/archive/blog/one-sheet-hyperboloid.png)

The Mathematica code I wrote is

```
a = 1; b = 1; c = 1; h = 4; n = 10;
p1 = ContourPlot3D[ (*hyperboloid*)   
   x^2/a^2 + y^2/b^2 - z^2/c^2 == 1, {x, -h, h}, {y, -h, h}, {z, -h, 
    h},
   Mesh -> None, ContourStyle -> Opacity[0.4], AxesLabel -> {x, y, z},
    LabelStyle -> Large
   ];
p2 = ParametricPlot3D[ (*red lines*)
   Table[{
     a (Cos[theta] - v Sin[theta]),
     b (Sin[theta] + v Cos[theta]),
     c v
     }, {theta, 0, 2 Pi, 2 Pi/n}],
   {v, -20, 20}, PlotStyle -> {Red}
   ];
p3 = ParametricPlot3D[ (*blue lines*)
   Table[{
     a (Cos[theta] - v Sin[theta]),
     b (Sin[theta] + v Cos[theta]),
     - c v
     }, {theta, 0, 2 Pi, 2 Pi/n}],
   {v, -20, 20}, PlotStyle -> {Blue}
   ];
Show[{p1, p2, p3}]
```

![](https://lh3.googleusercontent.com/AUr9JxSqmlUh-5msmjWsPWkhDfaEu4Bs_sBySuug0RbnIXe0s_pQMQIU8VvTqCnVm28oB1gjxBvMRbn6vRP-Xjj44utw9QyU0Jl9iy1a--cOpYwX_nkCSyCAZhEeXtyQ_VS-Rw_gvjQ=w2400)







