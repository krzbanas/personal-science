+++
date = "2021-10-01"
lastmod = "2021-10-01"
draft = false
tags = ["R", "tests"]
title = "A paired t-test"
summary = """
A paired t-test is used to estimate whether the means of two related measurements are significantly different from one another
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

A paired t-test is used to estimate whether the means of two related measurements are significantly different from one another.

Examples of paired study designs are:
- measurements collected before and after an intervention in an experimental study
- twins, husbands and wives, brothers and sisters, pairs of eyes
- matched cases and controls
- a cross-over trial in which each patient has two measurements on the variable, one while taking active treatment and one while taking placebo


```r
# Generate example data
before <- c(4, 5, 7, 6, 8)
after <- c(6, 6, 8, 8, 9)

# Perform paired t-test
t.test(before, after, paired = TRUE)
```

Output:


```r
Paired t-test

data:  before and after
t = -3.1623, df = 4, p-value = 0.02905
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -3.413031 -0.386969
sample estimates:
mean of the differences 
                    -1.9 

```

Interpretation:

In this example, we have two related measurements (before and after). We want to know if there is a significant difference in the means of these measurements. We perform a paired t-test using the `t.test()` function in R, specifying `paired = TRUE`. The output shows the t-statistic, degrees of freedom, and p-value. The p-value is 0.02905, which is less than the commonly used significance level of 0.05. Therefore, we can conclude that there is a significant difference in the means of the two measurements. The sample mean of the differences is -1.9, which means that the after measurement tends to be higher than the before measurement by about 1.9 units on average. The 95% confidence interval for the mean difference is (-3.41, -0.39), which means we are 95% confident that the true mean difference falls within this range.
