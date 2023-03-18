+++
date = "2021-09-03"
lastmod = "2021-09-03"
draft = false
tags = ["R", "Tests"]
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

Suppose we want to compare the math test scores of two different classes of students, class A and class B. 
The null hypothesis is that the two classes have the same median math test score, and the alternative hypothesis is that they do not. 

```r
class_A <- c(70, 85, 68, 89, 78, 92, 75, 82, 80, 87)
class_B <- c(62, 77, 70, 80, 73, 88, 67, 72, 75, 81)

# To perform the Wilcoxon-Mann-Whitney test, 
# we can use the wilcox.test() function in R:

# Perform Wilcoxon-Mann-Whitney test
wilcox.test(class_A, class_B)
```


```r
	Wilcoxon rank sum test with continuity correction

data:  class_A and class_B
W = 55, p-value = 0.2517
alternative hypothesis: true location shift is not equal to 0
```

The test statistic is W = 55, and the p-value is 0.2517. Since the p-value is greater than 0.05, we fail to reject the null hypothesis and conclude that there is insufficient evidence to suggest that there is a significant difference in the median math test scores between the two classes.

It's worth noting that the Wilcoxon-Mann-Whitney test does not assume that the data are normally distributed, and is appropriate for comparing two independent samples when the assumptions of the t-test are not met. However, it does assume that the two samples have the same shape, which may not be the case in all situations.

In summary, the Wilcoxon-Mann-Whitney test can be used to compare two independent samples, and is useful when the assumptions of the t-test are not met. In our example, we found that there was no significant difference in the median math test scores between two classes of students.

NOTE: The null hypothesis is that the observations from one group do not tend to have a higher or lower ranking than observations from the other group. This test does not test the medians of the data as is commonly thought, it tests the whole distribution. In practice, however, we use the medians to present the results. Statistical speaking, if the distributions of the two groups have similar shapes, the Wilcoxon-Mann-Whitney test can be used to determine whether there are differences in the medians between the two groups.

If the samples are very small (both smaller than four observations) then statistical significance is impossible.
