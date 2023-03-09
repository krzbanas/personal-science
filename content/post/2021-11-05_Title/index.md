+++
date = "2021-11-05"
lastmod = "2021-11-05"
draft = false
tags = ["R", "tests"]
title = "Wilcoxon Signed-Rank test"
summary = """
Wilcoxon Signed-Rank test (Wilcoxon test): a non-parametric test that can be conducted to compare paired samples when the differences are not normally distributed
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

Wilcoxon Signed-Rank test (Wilcoxon test) is a non-parametric test that can be conducted to compare paired samples when the differences are not normally distributed. It is based on the signs of the differences and the magnitude of the rank of the differences between pairs of measurements, rather than the actual values. The null hypothesis is that there is no tendency for values under each paired variable to be higher or lower. It is often thought of as a test for small samples. However, if the sample is smaller than 6, then statistical significance is impossible.


```r
# Sample data
x <- c(6, 8, 10, 5, 7, 9, 8, 6, 7, 9)
y <- c(5, 7, 8, 4, 6, 8, 7, 5, 6, 8)

# Perform Wilcoxon signed-rank test
wilcox.test(x, y, paired = TRUE)
```


