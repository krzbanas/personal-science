+++
date = "2021-12-03"
lastmod = "2021-12-03"
draft = false
tags = ["R", "tests"]
title = "One-way analysis of variance"
summary = """
One-way analysis of variance is a statistical test used when we want to compare several means.
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

One-way analysis of variance (one-way ANOVA) is a statistical test used when we want to compare several means. We may think of it as an extension of Student’s t-test to the case of more than two independent samples.

Although, this test can detect a difference between several groups it does not inform us about which groups are different from the others. At first glance, we might think to compare all groups in pairs with multiple t-tests. However, this procedure may lead to incorrect conclusions (known as multiple comparisons problem) because each comparison increases the likelihood of committing at least one Type I error within a set of comparisons (familly-wise Type I error rate).

This is the reason why, after an ANOVA test concluding on a significant difference between group means, we should not just compare all possible pairs of groups with t-tests. Instead we perform statistical tests that take into account the number of planned comparisons (post hoc tests) and make the necessary adjustments to ensure that Type I error is not inflated.


```r
# Load the dataset
data(mtcars)

# Run the ANOVA
model <- lm(mpg ~ cyl, data = mtcars)
anova(model)
```

This will produce an output like the following:

```r
Analysis of Variance Table

Response: mpg
          Df Sum Sq Mean Sq F value    Pr(>F)    
cyl        1  817.7  817.71  79.561 6.113e-10 ***
Residuals 30 1474.2   49.14                      
---
Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

Interpretation:

The ANOVA table shows two sources of variation in the data: the variation between groups (the `cyl` variable in this case) and the variation within groups. The F-statistic measures the ratio of the variability between groups to the variability within groups.

The `p-value` for the `cyl` variable is less than 0.05, which indicates that there is a significant difference in mean `mpg` across different values of `cyl`. Therefore, we can reject the null hypothesis that there is no difference in mean `mpg` across different values of `cyl`.

The R output also includes a `Sum Sq` column, which represents the sum of squares for each source of variation, and a `Mean Sq` column, which represents the mean sum of squares for each source of variation. The `Residuals` row represents the remaining unexplained variation after accounting for the effect of `cyl`.

