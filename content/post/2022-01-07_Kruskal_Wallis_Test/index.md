+++
date = "2022-01-07"
lastmod = "2022-01-07"
draft = false
tags = ["R", "Tests"]
title = "Kruskal-Wallis test"
summary = """
The Kruskal-Wallis test is a rank-based non-parametric alternative to the one-way ANOVA and an extension of the Wilcoxon-Mann-Whitney test to allow the comparison of more than two independent groups.
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

The Kruskal-Wallis test is a rank-based non-parametric alternative to the one-way ANOVA and an extension of the Wilcoxon-Mann-Whitney test to allow the comparison of more than two independent groups. It’s usually recommended when the assumptions of one-way ANOVA test are not met (non-normal distributions) or with small samples.


```r
# Example data
group1 <- c(10, 20, 30, 40, 50)
group2 <- c(15, 25, 35, 45, 55)
group3 <- c(5, 10, 15, 20, 25)
data <- data.frame(value=c(group1, group2, group3),
                   group=rep(c("Group 1", "Group 2", "Group 3"), each=5))

# Perform Kruskal-Wallis test
kruskal.test(value ~ group, data=data)
```

The output of the `kruskal.test()` function should look something like this:

```r
Kruskal-Wallis rank sum test

data:  value by group
Kruskal-Wallis chi-squared = 7.8, df = 2, p-value = 0.02
```


