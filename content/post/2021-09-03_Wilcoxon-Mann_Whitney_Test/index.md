+++
date = "2021-09-03"
lastmod = "2021-09-03"
draft = false
tags = ["R", "testing"]
title = "Wilcoxon-Mann-Whitney (WMW) test"
summary = """
Wilcoxon-Mann-Whitney (WMW) test to compare two independent samples 
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

The Wilcoxon-Mann-Whitney (WMW) test (AKA Mann-Whitney U test or Wilcoxon Rank Sum test) is used to compare two independent samples and is considered the non-parametric alternative to the Student’s t-test when there is violation of normality or for small sample sizes. 

 The researchers used = 0.05 significance level to test if the distribution of urinary thromboglobulin (b_TG) differs in the two groups.
  
 Null hypothesis and alternative hypothesis
H0 thromboglobulin is the same in the two groups
H1 the distribution of urinary thromboglobulin is different in the two groups
```r

```
NOTE: The null hypothesis is that the observations from one group do not tend to have a higher or lower ranking than observations from the other group. This test does not test the medians of the data as is commonly thought, it tests the whole distribution. In practice, however, we use the medians to present the results. Statistical speaking, if the distributions of the two groups have similar shapes, the Wilcoxon-Mann-Whitney test can be used to determine whether there are differences in the medians between the two groups.


The output of the `t.test()` function provides a lot of information, including the sample means, the test statistic, the degrees of freedom, the p-value, and confidence intervals:

```r

```

 If the samples are very small (both smaller than four observations) then statistical significance is impossible.
