+++
date = "2022-02-04"
lastmod = "2022-12-04"
draft = false
tags = ["R", "Tests"]
title = "Post-hoc multiple comparisons using Tukey test and Dunn's test"
summary = """
Post-hoc multiple comparisons using Tukey test and Dunn's test in R
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

Perform Tukey test for multiple comparisons:

```r
library(multcomp)
tukey <- glht(kruskal.test(value ~ group, data=data), linfct=mcp(group="Tukey"))
summary(tukey)
```

Perform Dunn's test for multiple comparisons

```r
library(dunn.test)
dunn <- dunn.test(data$value, data$group, method="holm")
print(dunn$comparison)
print(dunn$adjusted)
```
