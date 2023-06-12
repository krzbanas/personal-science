+++
date = "2023-06-02"
lastmod = "2023-06-02"
draft = false
tags = ["R","correlation"]
title = "Package correlation - part two of easystats"
summary = """

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

`correlation` is an easystats package focused on correlation analysis. It’s lightweight, easy to use, and allows for the computation of many different kinds of correlations, such as partial correlations, Bayesian correlations, multilevel correlations, polychoric correlations, biweight, percentage bend or Sheperd’s Pi correlations (types of robust correlation), distance correlation (a type of non-linear correlation) and more, also allowing for combinations between them (for instance, Bayesian partial multilevel correlation).

```r
library("correlation")
results <- correlation(iris)
results
## # Correlation Matrix (pearson-method)
## 
## Parameter1   |   Parameter2 |     r |         95% CI | t(148) |         p
## -------------------------------------------------------------------------
## Sepal.Length |  Sepal.Width | -0.12 | [-0.27,  0.04] |  -1.44 | 0.152    
## Sepal.Length | Petal.Length |  0.87 | [ 0.83,  0.91] |  21.65 | < .001***
## Sepal.Length |  Petal.Width |  0.82 | [ 0.76,  0.86] |  17.30 | < .001***
## Sepal.Width  | Petal.Length | -0.43 | [-0.55, -0.29] |  -5.77 | < .001***
## Sepal.Width  |  Petal.Width | -0.37 | [-0.50, -0.22] |  -4.79 | < .001***
## Petal.Length |  Petal.Width |  0.96 | [ 0.95,  0.97] |  43.39 | < .001***
## 
## p-value adjustment method: Holm (1979)
## Observations: 150
```
