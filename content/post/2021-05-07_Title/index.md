+++
date = "2021-05-07"
lastmod = "2021-05-07"
draft = true
tags = ["R"]
title = "Title"
summary = """
Summary
"""
math = false

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = "Caption"
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"

+++

To save a ggplot2 plot to a pdf file with high resolution, you can use the `ggsave()` function.

Here is an example code snippet:

```r
library(ggplot2)

# create a sample plot
my_plot <- ggplot(mtcars, aes(x=wt, y=mpg)) + 
             geom_point() + 
             labs(title="My Plot")

# save the plot to a pdf file with high resolution
ggsave("my_plot.pdf", plot=my_plot, width=10, height=8, dpi=300)
```
or this

