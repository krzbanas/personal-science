+++
date = "2022-10-07"
lastmod = "2022-10-07"
draft = false
tags = ["R", "Tidyr"]
title = "Order of the Columns"
summary = """
Summary
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

How to remove some columns in tidyr and change the order of columns?
You can use the `select()` function from the `dplyr` package (also part of the `tidyverse`) to select specific columns and change their order. Here's an example:


```r
library(tidyr)
library(dplyr)

# Create sample data
data <- data.frame(
  date = c("2023-03-01", "2023-03-02", "2023-03-03"),
  event = c("West Coast Park parkrun", "East Coast Park parkrun", "Central Park parkrun"),
  distance = c("5km", "10km", "7.5km"),
  participants = c(100, 200, 150)
)

# Select and reorder columns
data %>%
  select(date, participants, event) %>%
  # You can also use drop() to remove columns
  # drop(distance) %>%
  # drop(3) %>%
  # Note that you can use column names or positions to select columns
  # select(1, 4, 2) %>%
  # select(-distance) %>%
  # select(-c(distance, 2)) %>%
  # select(c(date, participants, event)) %>%
  # select(c("date", "participants", "event")) %>%
  # Note that you can chain multiple select() functions to select/reorder multiple times
  select(event, date, participants)
```

This code selects the date, participants, and event columns from the data dataframe and reorders them in that order using `select()`. You can remove columns using the `drop()` function or the negative sign `(-)` to exclude them. You can also use column names or positions to select columns, as shown in the commented-out examples.

Note that you can chain multiple `select()` functions to perform multiple selections and reorderings.
