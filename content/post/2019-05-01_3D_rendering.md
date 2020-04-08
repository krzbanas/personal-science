+++
date = "2019-05-01"
lastmod = "2019-05-01"
draft = false
tags = ["R", "3D", "ggplot2"]
title = "3D rendering of ggplot2"
summary = """

"""
math = false
+++



```r
#testing 3D
library(rayshader)
intensity_full_map2
plot_gg(intensity_full_map2, multicore = TRUE, width = 8, height = 8, scale = 300,
        zoom = 0.6, phi = 60, background = "#afceff",shadowcolor = "#3a4f70")
#or
par(mfrow = c(1, 1))
plot_gg(intensity_full_map2, width = 5, height = 4, scale = 300, multicore = TRUE, windowsize = c(1200, 960),
        fov = 70, zoom = 0.4, theta = 330, phi = 40)
render_depth(focus = 0.68, focallength = 200)
#movie
render_movie("intensity_full_map2.mp4", frames = 480)

```
{{< figure library= "true" src="3D_plot.png" title="Rendering of ggplot2 to 3D" >}}
