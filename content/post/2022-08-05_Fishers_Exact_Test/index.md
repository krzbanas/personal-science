+++
date = "2022-08-05"
lastmod = "2022-08-05"
draft = false
tags = ["R", "Tests"]
title = "Fisher’s exact test"
summary = """
Fisher’s exact test
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

If we want to see whether there’s an association between two categorical variables and the assumption for the expected frequencies in the contingency table is not fulfilled, an alternative test to the chi-square test can be used.

Fisher came up with a method for computing the exact probability of the chi-square statistic that is accurate when sample sizes are small. This method is called Fisher’s exact test even though it’s not so much a test as a way of computing the exact probability of the chi-square statistic. This procedure is normally used on 2 by 2 contingency tables and with small samples. However, it can be used on larger contingency tables and with large samples, but in this case it becomes computationally intensive.


```r
code
```

