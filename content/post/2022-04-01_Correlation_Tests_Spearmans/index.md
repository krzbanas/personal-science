+++
date = "2022-04-01"
lastmod = "2022-04-01"
draft = false
tags = ["R","Tests",]
title = "Correlation Tests: Spearmans"
summary = """
Correlation Test to assess a possible association between two numeric variables, X and Y: Spearman’s coefficient
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


To calculate the  Spearman’s  correlation coefficient between two numeric variables, X and Y, in R, you can use the `cor()` function. Here's an example code:

```r
# Create two numeric variables, X and Y
X <- c(5, 10, 15, 20, 25)
Y <- c(15, 25, 35, 45, 55)

# Calculate the Pearson correlation coefficient between X and Y
correlation <- cor(X, Y, method = "pearson")

# Print the correlation coefficient
print(correlation)
```

The interpretation of the correlation coefficient depends on its value:

- If the correlation coefficient is close to 1, it indicates a strong positive correlation between the two variables, meaning that when one variable increases, the other variable also tends to increase.
- If the correlation coefficient is close to -1, it indicates a strong negative correlation between the two variables, meaning that when one variable increases, the other variable tends to decrease.
- If the correlation coefficient is close to 0, it indicates no or weak correlation between the two variables, meaning that there is no clear relationship between them.

It is also important to note that correlation **does not imply causation**. Even if two variables are strongly correlated, it does not necessarily mean that one variable causes the other.

