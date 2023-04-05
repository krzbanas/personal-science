+++
date = "2018-02-02"
lastmod = "2018-02-02"
draft = false
tags = ["R", "hyperSpec", "Normalization"]
title = "Vector Normalization"
summary = """
Vector normalization of all spectra
"""
math = false
+++



Vector normalization of all spectra from hyperSpec object ad1, first calculating and subtracting mean spectrum (functions: `apply` and `sweep` and then dividing by variance. In order to compute variance `rowSums` function is used.
```r
#vector normalization
#subtract mean
means4 <- apply (ad1, 1, mean)
ad1VN <- sweep(ad1, 1, means4, "-")
#divide by variance 
ad2VN <- ad1VN /sqrt(rowSums(ad1VN ^2))
```
