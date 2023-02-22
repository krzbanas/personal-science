+++
date = "2021-03-05"
lastmod = "2021-03-05"
draft = true
tags = ["R"]
title = "How to remove y-axis labels in ggplot"
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

To remove y-axis labels in a ggplot chart, you can use the `element_blank()` function for the `axis.text.y` parameter. Here's an example code:

```r
library(ggplot2)

# create example data
df <- data.frame(x = 1:10, y = rnorm(10))

# create ggplot chart
ggplot(df, aes(x, y)) +
  geom_point() +
  theme(axis.text.y = element_blank())

```



