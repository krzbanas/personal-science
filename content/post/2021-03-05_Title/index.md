+++
date = "2021-03-05"
lastmod = "2021-03-05"
draft = false
tags = ["R", "plot", "ggplot2]
title = "How to remove y-axis labels in ggplot"
summary = """
How to remove y-axis labels in a ggplot chart
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

This will remove the y-axis labels, but keep the y-axis line and ticks. If you also want to remove the ticks, you can use the `element_blank()` function for the `axis.ticks.y` parameter:


```r
ggplot(df, aes(x, y)) +
  geom_point() +
  theme(axis.text.y = element_blank(), 
        axis.ticks.y = element_blank())
```

This will remove both the y-axis labels and ticks.
