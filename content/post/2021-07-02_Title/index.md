+++
date = "2021-07-02"
lastmod = "2021-07-02"
draft = false
tags = ["R", "ggstatplot"]
title = "Equality of medians with violin plot"
summary = """
Test the equality of two groups medians and plots violin plot using ggstatsplot library with data points jittered
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
Here's an example code in R that performs a statistical test for equality of two group medians and plots a violin plot using the ggstatsplot library with jittered data points:

```r
# load ggstatsplot library
library(ggstatsplot)

# generate example data
set.seed(123)
group1 <- rnorm(50, mean = 10, sd = 2)
group2 <- rnorm(50, mean = 12, sd = 2)

# perform a Wilcoxon rank sum test for medians
wilcox.test(group1, group2)

# plot a violin plot with jittered data points
ggstatsplot::ggsviolin(
  data = data.frame(
    value = c(group1, group2),
    group = c(rep("Group 1", length(group1)), rep("Group 2", length(group2)))
  ),
  x = "group",
  y = "value",
  add = "jitter",
  draw_quantiles = c(0.25, 0.5, 0.75),
  ggtheme = ggplot2::theme_bw()
)
```



