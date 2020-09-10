---
title: Plotting Complex Functions with GNU Plot
description: Example of GNU Plot to create a mandelbrot set
published: true
date: 2020-09-10T01:05:33.714Z
tags: 
editor: markdown
---

# ![one.svg](/one.svg){.align-right}Visualising the Mandelbrot set as a 3D surface
Plot

``` gnuplot
complex(x,y) = x*{1,0}+y*{0,1}
mandelbrot(x,y,z,n) = (abs(z)>2.0 || n>=200) ? \
                  n : mandelbrot(x,y,z*z+complex(x,y),n+1)

set xrange [-2:2]
set yrange [-2:2]
set logscale z
set isosample 240
set hidden3d
set contour
splot mandel(x,y,{0,0},0) notitle
```

</div>

![](one.svg)
