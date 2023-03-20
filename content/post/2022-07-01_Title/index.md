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


To perform a chi-square test of independence in R, we can use the `chisq.test()` function. Here's an example:
Let's say we have a dataset called `mydata` with two categorical variables: `gender` and `smoker`. We want to test whether there is an association between these two variables.

```r
# Create a dataset
gender <- c("Male", "Female", "Male", "Male", "Female", "Male", "Female", "Male", "Female", "Female")
smoker <- c("No", "Yes", "No", "No", "Yes", "No", "No", "No", "Yes", "Yes")
mydata <- data.frame(gender, smoker)

# Perform chi-square test of independence
chisq.test(mydata)
```

The output will look like this:

```r
Pearson's Chi-squared test

data:  mydata
X-squared = 0.2, df = 1, p-value = 0.6557

Warning message:
In chisq.test(mydata) : Chi-squared approximation may be incorrect
```

The output shows the test statistic (`X-squared`), the degrees of freedom (`df`), and the `p-value`. The null hypothesis is that there is no association between the two variables, and the alternative hypothesis is that there is an association between the two variables. The `p-value` tells us whether to reject or fail to reject the null hypothesis.

In this example, the `p-value` is 0.6557, which is greater than the significance level of 0.05. Therefore, we fail to reject the null hypothesis and conclude that there is no evidence of an association between gender and smoker. However, we also see a warning message that the chi-squared approximation may be incorrect due to low expected cell counts, so we should interpret the results with caution.
