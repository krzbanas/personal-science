+++
date = "2018-04-06"
lastmod = "2018-04-06"
draft = false
tags = ["R", "hyperspec", "subset"]
title = "Subsetting hyperspectral object"
summary = """
Subsetting hyperspectral object: partial spectral range, spectra selected by indices, spectra from one group (name based selection) etc.
"""
math = false
+++
Subsetting of hyperspectral object may be done with specifying spectral range or spectra indices, but also with `subset` function. Combining this with `grepl` function allows for selecting groups with particular names.

```r
a3
hyperSpec object
   22 spectra
   3 data columns
   3101 data points / spectrum
wavelength:  [numeric] 700 701 ... 3800
data:  (22 rows x 3 columns)
   1. files:  [factor] DP_Br_n_1_20170717_1702_0.txt DP_Br_n_1_20170717_1705_0.txt ... DP_I_n_4_20170717_1623_0.txt
   2. group:  [factor] Br_n_1 Br_n_1 ... I_n_4_
   3. spc:  [matrix3101] -0.0010941127 -0.0009799145 ... 0.01204381
  
#partial spectral range
a3range<-a3[,,1000~1500]
a3range
hyperSpec object
   22 spectra
   3 data columns
   501 data points / spectrum
wavelength:  [numeric] 1000 1001 ... 1500
data:  (22 rows x 3 columns)
   1. files:  [factor] DP_Br_n_1_20170717_1702_0.txt DP_Br_n_1_20170717_1705_0.txt ... DP_I_n_4_20170717_1623_0.txt
   2. group:  [factor] Br_n_1 Br_n_1 ... I_n_4_
   3. spc:  [matrix501] 0.05538213 0.04516893 ... 0.1254986

# some spectra
a3some<-a3[2:19,,]
a3some
hyperSpec object
   18 spectra
   3 data columns
   3101 data points / spectrum
wavelength:  [numeric] 700 701 ... 3800
data:  (18 rows x 3 columns)
   1. files:  [factor] DP_Br_n_1_20170717_1705_0.txt DP_Br_n_1_20170717_1707_0.txt ... DP_I_n_3_20170717_1601_0.txt
   2. group:  [factor] Br_n_1 Br_n_1 ... I_n_3_
   3. spc:  [matrix3101] -0.0009799145 -0.0035743618 ... 0.0122932

# some groups (names in vector select01)
select01<-c("Br_n_1","Cl_n_1","I_n_1_")
a3groups01<-subset(a3, group %in% select01)
a3groups01
hyperSpec object
   13 spectra
   3 data columns
   3101 data points / spectrum
wavelength:  [numeric] 700 701 ... 3800
data:  (13 rows x 3 columns)
   1. files:  [factor] DP_Br_n_1_20170717_1702_0.txt DP_Br_n_1_20170717_1705_0.txt ... DP_I_n_1_20170717_1505_0.txt
   2. group:  [factor] Br_n_1 Br_n_1 ... I_n_1_
   3. spc:  [matrix3101] -0.0010941127 -0.0009799145 ... 0.02612447

# some groups (group name include I)
p1 <- "I"
a3groups02<-subset(a3, grepl(p1, group))
# or
a3groups02<-subset(a3, grepl("I", group))
a3groups02
hyperSpec object
   12 spectra
   3 data columns
   3101 data points / spectrum
wavelength:  [numeric] 700 701 ... 3800
data:  (12 rows x 3 columns)
   1. files:  [factor] DP_I_n_1_20170717_1456_0.txt DP_I_n_1_20170717_1504_0.txt ... DP_I_n_4_20170717_1623_0.txt
   2. group:  [factor] I_n_1_ I_n_1_ ... I_n_4_
   3. spc:  [matrix3101] -0.002799757 -0.002894319 ... 0.012043
```
