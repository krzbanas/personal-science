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


