+++
date = "2021-08-06"
lastmod = "2021-08-06"
draft = false
tags = ["R", "testing"]
title = "Equality of medians with violin plot"
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



