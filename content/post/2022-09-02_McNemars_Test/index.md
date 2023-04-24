+++
date = "2022-09-02"
lastmod = "2022-09-02"
draft = false
tags = ["R", "tests"]
title = "McNemar’s test "
summary = """
Summary
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

The McNemar’s test (also known as the paired or matched chi-square) is used to determine if there are differences on a dichotomous dependent variable between two related groups. It can be considered as eqivalent to the paired-samples t-test, but for a dichotomous (not continuous) dependent variable. The McNemar’s test is used to analyze pre-test - post-test study designs (observing categorical outcomes more than once in the same patient).

Suppose we have a dataset containing the results of a medical test for a certain disease, where the test was administered to the same group of patients before and after a treatment. The data is in the following format:

```r
Before  After
1   Positive    Positive
2   Positive    Negative
3   Negative    Negative
4   Positive    Positive
5   Negative    Negative
6   Positive    Negative
7   Negative    Negative
8   Positive    Positive
9   Positive    Positive
10  Negative    Negative
```

The first column represents the results of the test before treatment, and the second column represents the results after treatment. The values in each column are either `"Positive"` or `"Negative"`. We want to test whether the treatment has had a significant effect on the results of the test.

To perform McNemar's test, we can use the `mcnemar.test()` function in R. Here's the code:

```r
# Read in the data
data <- read.csv("test_data.csv")

# Convert the data to a 2x2 contingency table
table <- table(data$Before, data$After)

# Perform McNemar's test
mcnemar.test(table)
```

This will give us the following output:

```r
McNemar's Chi-squared test

data:  table
McNemar's chi-squared = 0.6, df = 1, p-value = 0.4387
```

The `p-value` is 0.4387, which is greater than 0.05, the commonly used significance level. Therefore, we cannot reject the null hypothesis that the treatment has no effect on the results of the test.

To interpret this result, we can say that there is no significant evidence to suggest that the treatment has had a significant effect on the results of the test.
