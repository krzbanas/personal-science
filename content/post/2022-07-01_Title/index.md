+++
date = "2022-07-01"
lastmod = "2022-07-01"
draft = false
tags = ["R", "Tests"]
title = "Chi-square test of independence."
summary = """
Chi-square test of independence to check if there’s an association between two categorical variables
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

If we want to see whether there’s an association between two categorical variables we can use the Pearson’s chi-square test, often called chi-square test of independence. This is an extremely elegant statistic based on the simple idea of comparing the frequencies we observe in certain categories to the frequencies we might expect to get in those categories by chance.
Null hypothesis and alternative hypothesis:
 - There is no association between the two categorical variables (they are independent)
 - There is association between the two categorical variables (they are dependent)

```r
code
```



