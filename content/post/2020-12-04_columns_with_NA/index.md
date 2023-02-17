+++
date = "2020-12-04"
lastmod = "2020-12-04"
draft = false
tags = ["R", "NA", "incomplete observations"]
title = "Find columns that include missing values (NA)"
summary = """
find which columns in an R data frame include missing values (NA)
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

To find which columns in an R data frame include missing values (NA), you can use the `colSums()` function, which calculates the sum of each column. If you apply this function to a data frame with missing values, the resulting vector will include a count of the number of missing values in each column.

Here's an example of how to use `colSums()` to identify columns with missing values:

```r
# Create a sample data frame with missing values
df <- data.frame(x = c(1, 2, NA, 4), y = c(NA, 2, 3, 4), z = c(1, 2, 3, NA))

# Use colSums() to count the number of NAs in each column
na_counts <- colSums(is.na(df))

# Print the result
na_counts
```

In this example, `na_counts` will be a vector with three elements, indicating the number of missing values in each column of `df`. Columns with at least one missing value will have a count greater than zero. You can also use logical indexing to extract the column names with missing values:


```r
# Extract column names with missing values
na_cols <- names(na_counts)[na_counts > 0]

# Print the result
na_cols
```
