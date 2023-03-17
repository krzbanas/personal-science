+++
date = "2022-06-03"
lastmod = "2022-06-03"
draft = false
tags = ["R","Tests"]
title = "Correlation Tests: Kendall’s"
summary = """
Correlation Test to assess a possible association between two numeric variables, X and Y: Kendall’s coefficient
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
Correlation is a statistical method used to assess a possible association between two numeric variables, X and Y. 
There are several statistical coefficients that we can use to quantify correlation depending on the underlying relation of the data:

- Pearson’s 
- Spearman’s 
- Kendall’s


To calculate the Spearman's rank correlation coefficient between two numeric variables, X and Y, in R, you can use the `cor()` function with the `method = "spearman"` argument. Here's an example code:

```r
# Create two numeric variables, X and Y
X <- c(5, 10, 15, 20, 25)
Y <- c(15, 25, 35, 45, 55)

# Calculate the Spearman's rank correlation coefficient between X and Y
correlation <- cor(X, Y, method = "spearman")

# Print the correlation coefficient
print(correlation)
```

The `print(correlation)` output will be a single value, which represents the Spearman's rank correlation coefficient between the two variables. The value ranges from -1 to 1, where -1 indicates a perfect negative correlation, 0 indicates no correlation, and 1 indicates a perfect positive correlation.

The interpretation of the Spearman's rank correlation coefficient is similar to the Pearson correlation coefficient. Here's a breakdown of how to interpret different values:

- If the correlation coefficient is close to 1, it indicates a strong positive correlation between the two variables, meaning that when one variable increases, the other variable tends to increase.
- If the correlation coefficient is close to -1, it indicates a strong negative correlation between the two variables, meaning that when one variable increases, the other variable tends to decrease.
- If the correlation coefficient is close to 0, it indicates no or weak correlation between the two variables, meaning that there is no clear relationship between them.

It is important to note that the Spearman's rank correlation coefficient measures the strength and direction of the **monotonic relationship** between the two variables, which means it measures how well the relationship can be described using a monotonic function (i.e., a function that either always increases or always decreases). It is less sensitive to outliers and does not assume a linear relationship between the variables, unlike the Pearson correlation coefficient.

