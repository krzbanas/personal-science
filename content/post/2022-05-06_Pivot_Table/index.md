+++
date = "2022-05-06"
lastmod = "2018-02-02"
draft = false
tags = ["R", "pivot"]
title = "Pivot Table"
summary = """
Pivot Table
"""
math = false
+++


Here's an example of how to create a pivot table in R using the dplyr and tidyr packages:

```r
library(dplyr)
library(tidyr)

# Create sample data
df <- data.frame(
  category = c("A", "A", "B", "B", "C", "C"),
  subcategory = c("X", "Y", "X", "Y", "X", "Y"),
  value = c(1, 2, 3, 4, 5, 6)
)

# Create pivot table
pivot_table <- df %>%
  pivot_wider(names_from = subcategory, values_from = value)

# Output pivot table
pivot_table
```

- The dplyr library is loaded to use the %>% operator to chain operations together
- The tidyr library is loaded to use the pivot_wider function to create the pivot table
- A sample data frame df is created with three columns: category, subcategory, and value
- The pivot_wider function is used to create the pivot table, with the names_from argument indicating the column to use as the new column names, and the values_from argument indicating the column to use as the values in the pivot table.
- The pivot table is outputted by calling the pivot_table object.
