+++
date = "2019-12-06"
lastmod = "2019-12-06"
draft = false
tags = ["R", "calculations", "derivatives"]
title = "Derivatives Calculation with diff function"
summary = """

"""
math = false
+++

Here is code to calculate derivatives of the spectra in a different way by using `diff` function. For this operation you should have equal distances between data points (it may be achieved by function `spc.loess`). Function `t` in this code chunk transpose the results in order to put them back to hyperSpec object. Derivatives


```r
#first derivative
#calculate first derivatives of spectra - slot a2$spc - by function diff

der1 <- t(diff (t( a2$spc), differences = 1 )) # first derivative
#number of spectral points is smaller by 1 so wavenumber must be cut
ad1= new ("hyperSpec", wavelength = (a2@wavelength[-1]-1), spc = der1, data=d1 )
#again you can check the result (mean value of first derivative aggregated over variable explorder)
means3 <- aggregate ( ad1, by = ad1 $explorder, mean_pm_sd)
plot ( means3, stacked = ".aggregate", fill = ".aggregate")

```
