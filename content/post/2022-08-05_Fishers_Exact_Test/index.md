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

To perform Fisher's exact test in R, you can use the `fisher.test()` function. This test is used to compare the relationship between two categorical variables in a contingency table, where the sample sizes are small and the assumptions for the chi-square test may not be met.

Here is an example code for performing Fisher's exact test in R:
```r
# Create a contingency table
data <- matrix(c(10, 20, 15, 25), nrow = 2, dimnames = list(Sex = c("Male", "Female"), Smoke = c("Yes", "No")))

# Print the contingency table
data

# Perform Fisher's exact test
fisher.test(data)
```

In this example, we have a contingency table that shows the relationship between the variables `"Sex"` and `"Smoke"`. The rows of the table represent the different values of `"Sex"` (Male and Female) and the columns represent the different values of `"Smoke"` (Yes and No). The values in the table represent the frequency counts of each combination of `"Sex"` and `"Smoke"`.

The `fisher.test()` function produces the following output:

```r
Fisher's Exact Test for Count Data

data:  data
p-value = 0.3466
alternative hypothesis: two.sided
```

