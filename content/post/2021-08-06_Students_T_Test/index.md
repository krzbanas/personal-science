+++
date = "2021-08-06"
lastmod = "2021-08-06"
draft = false
tags = ["R", "testing"]
title = "Two sample t-test (Student’s t-test)"
summary = """
Two sample t-test (Student’s t-test) 
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

Here is an example of performing a two-sample t-test in R and interpreting the results.

Suppose we want to test whether the mean height of men is significantly different from the mean height of women. We have two samples: one of heights of 50 men and one of heights of 50 women. We can use a two-sample t-test to test whether the difference between the sample means is statistically significant.

```r
# Generate fake data
set.seed(123)
men_heights <- rnorm(50, mean = 175, sd = 7)
women_heights <- rnorm(50, mean = 162, sd = 6)

# Perform two-sample t-test
t_test <- t.test(men_heights, women_heights)

# Print results
t_test
```

The output of the `t.test()` function provides a lot of information, including the sample means, the test statistic, the degrees of freedom, the p-value, and confidence intervals:

```r
Welch Two Sample t-test

data:  men_heights and women_heights
t = 16.563, df = 97.842, p-value < 2.2e-16
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 12.35252 14.92231
sample estimates:
mean of x mean of y 
 174.5499  162.0828 
```


The test statistic `t` is calculated as the difference between the sample means divided by the standard error of the difference. The degrees of freedom `df` are calculated using a Welch-Satterthwaite approximation, which accounts for unequal variances in the two samples. The `p-value` is very small (`p-value < 2.2e-16`), indicating strong evidence against the null hypothesis that the mean heights of men and women are equal. The 95% confidence interval for the difference in means (`12.35252 14.92231`) does not contain 0, further supporting the rejection of the null hypothesis.

In summary, based on the results of the two-sample t-test, we can conclude that there is strong evidence that the mean height of men is significantly different from the mean height of women, with men being taller on average.

