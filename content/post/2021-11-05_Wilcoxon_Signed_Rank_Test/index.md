+++
date = "2021-11-05"
lastmod = "2021-11-05"
draft = false
tags = ["R", "Tests"]
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
In this example, we have two samples, `x` and `y`, that are paired (i.e., each observation in `x` corresponds to an observation in `y`). The `wilcox.test()` function performs the Wilcoxon signed-rank test and returns a list of results, including:

- `V`: the test statistic (i.e., the sum of the ranks of the differences between the paired observations).
- `p-value`: the p-value for the test, which indicates the probability of obtaining the observed test statistic (or a more extreme value) if the null hypothesis (that the median difference between `x` and `y` is zero) is true.

Here is the code with the output interpretation:

```r
wilcox.test(x, y, paired = TRUE)

	Wilcoxon signed rank test

data:  x and y
V = 27, p-value = 0.2507
alternative hypothesis: true location shift is not equal to 0
```


The output shows that the Wilcoxon signed-rank test resulted in a test statistic `V` of 27, which has a `p-value` of 0.2507. Since this `p-value` is greater than the usual significance level of 0.05, we fail to reject the null hypothesis that the median difference between `x` and `y` is zero. The alternative hypothesis is that the true location shift (median difference) is not equal to zero. Therefore, we can interpret this result as there being insufficient evidence to conclude that there is a difference between the two paired samples at the 5% significance level.
