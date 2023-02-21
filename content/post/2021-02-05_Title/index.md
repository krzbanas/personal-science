+++
date = "2021-02-05"
lastmod = "2021-02-05"
draft = true
tags = ["R"]
title = "Title"
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

Some text `worldcloud` and other.

```r

library(tidyverse)
library(forcats)

# create an example data frame with a factor column
df <- data.frame(
  x = factor(c("A", "B", "C", "A", "B")),
  y = 1:5
)

# create a new order for the factor levels
new_order <- c("C", "B", "A")

# create a mapping of old factor levels to new factor levels
level_mapping <- c("A" = "Alpha", "B" = "Beta", "C" = "Charlie")

# use fct_recode() to recode the factor levels with new names and order
df_new <- df %>%
  mutate(x = fct_recode(x, !!!level_mapping, .ordered = TRUE)) %>%
  mutate(x = fct_relevel(x, new_order))

# print the new data frame
print(df_new)

```



