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


To calculate Kendall's correlation coefficient between two numeric variables, X and Y, in R, you can use the `cor()` function with the `method = "kendall"` argument. Here's an example code:

```r
# Create two numeric variables, X and Y
X <- c(5, 10, 15, 20, 25)
Y <- c(15, 25, 35, 45, 55)

# Calculate Kendall's correlation coefficient between X and Y
correlation <- cor(X, Y, method = "kendall")

# Print the correlation coefficient
print(correlation)
```

In this example, we have created two numeric variables, X and Y, with five values each. We then use the `cor()` function to calculate Kendall's correlation coefficient between X and Y, using the `method = "kendall`" argument to specify the type of correlation coefficient we want to calculate. Finally, we print the correlation coefficient using the `print()` function.

