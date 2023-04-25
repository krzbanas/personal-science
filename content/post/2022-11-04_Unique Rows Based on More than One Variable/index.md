+++
date = "2022-11-04"
lastmod = "2022-11-04"
draft = false
tags = ["R", "filter"]
title = "Unique rows based on more than one variable"
summary = """
Find the number of unique rows based on more than one variable in the data frame.
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

To find the number of unique rows in R based on two columns, you can use the `unique()` function with the `duplicated()` function.
Assuming you have a data frame called my_data with two columns named column1 and column2, you can use the following code:

```r
unique_rows <- my_data[!duplicated(my_data[, c("column1", "column2")]),]
n_unique_rows <- nrow(unique_rows)
```

The `duplicated()` function returns a logical vector indicating which rows are duplicates based on the specified columns. The `!` operator is used to negate the logical vector, so that `TRUE` values become `FALSE` and *vice versa*. When this logical vector is used to index the data frame using the operator, only the unique rows are returned. Finally, the `nrow()` function is used to count the number of unique rows.

Note that the order of the columns in the `c()` function is important, as the function will consider duplicates based on the order of the columns specified.
