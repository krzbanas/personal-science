
+++
date = "2019-08-02"
lastmod = "2019-08-02"
draft = false
tags = ["R", "dataframe", "join", "plyr", "dplyr"]
title = "Join multiple dataframes and calculate ratios"
summary = """
Combining multiple dataframes into one and calculating new variables
"""
math = false
+++

There is a function in `plyr` package called `join_all` that allows for combining mutliple dataframes into one by using particular columns (variables). Function `mutate` from `dplyr` helps to calculatate new variables from existing ones (ratios from intensities in this case).

```r
library(plyr) #join_all
library(dplyr)

togeth01<-join_all(list(longmat1038, longmat1260,longmat1535,longmat1450,longmat1642,longmat1678),
                   by=c("x","y"), type = 'full')
togeth01 <-
  mutate(togeth01,
         ratio1038to1260 = I1038/I1260,
         ratio1038to1450 = I1038/I1450,
         ratio1038to1535 = I1038/I1535,
         ratio1038to1642 = I1038/I1642,
         ratio1038to1678 = I1038/I1678,
         ratio1260to1450 = I1260/I1450,
         )

```
