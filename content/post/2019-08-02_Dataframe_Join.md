
+++
date = "2019-08-02"
lastmod = "2019-08-02"
draft = false
tags = ["R", "dataframe", "join"]
title = "Join multiple dataframes and calculate ratios"
summary = """

"""
math = false
+++



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