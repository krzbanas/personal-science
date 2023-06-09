+++
date = "2023-05-05"
lastmod = "2023-05-05"
draft = false
tags = ["R","report"]
title = "Package report - part one of easystats"
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
`report`’s primary goal is to bridge the gap between R’s output and the formatted results contained in your manuscript. It automatically produces reports of models and data frames according to best practices guidelines (e.g., APA’s style), ensuring standardization and quality in results reporting.


library(report)

model <- lm(Sepal.Length ~ Species, data = iris)
report(model)
# We fitted a linear model (estimated using OLS) to predict Sepal.Length with
# Species (formula: Sepal.Length ~ Species). The model explains a statistically
# significant and substantial proportion of variance (R2 = 0.62, F(2, 147) =
# 119.26, p < .001, adj. R2 = 0.61). The model's intercept, corresponding to
# Species = setosa, is at 5.01 (95% CI [4.86, 5.15], t(147) = 68.76, p < .001).
# Within this model:
# 
#   - The effect of Species [versicolor] is statistically significant and positive
# (beta = 0.93, 95% CI [0.73, 1.13], t(147) = 9.03, p < .001; Std. beta = 1.12,
# 95% CI [0.88, 1.37])
#   - The effect of Species [virginica] is statistically significant and positive
# (beta = 1.58, 95% CI [1.38, 1.79], t(147) = 15.37, p < .001; Std. beta = 1.91,
# 95% CI [1.66, 2.16])
# 
# Standardized parameters were obtained by fitting the model on a standardized
# version of the dataset. 95% Confidence Intervals (CIs) and p-values were
# computed using a Wald t-distribution approximation.
