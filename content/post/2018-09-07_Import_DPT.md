+++
date = "2018-09-07"
lastmod = "2018-09-07"
draft = false
tags = ["R", "hyperspec", "Import", "Opus", "dpt"]
title = "Import DPT  Opus (FTIR Imaging) FPA"
summary = """
Import DPT (data point table) Opus (FTIR Imaging) FPA
"""
math = false
+++



```r
file <- read.table ("6m_600_256scans_03.dpt", header = FALSE, dec = ".",
                    sep = ",")
# Single shot FTIR map has 64 by 64 spectra, pixel size is equal 2.7
# by 2.7 microns
# number of rows
x1 = 64
# number of colums 
y1 = 64 
x = rep (seq(from=0, to=2.7*(y1-1), by=2.7), times=x1)
y = rep (seq(from=0, to=2.7*(x1-1), by=2.7), each=y1)
d = data.frame(x,y)
# defining hyperSpec object
map01 <- new ("hyperSpec", wavelength = file [,1], spc = t (file [, -1]),
              data = d,label = list(.wavelength = "Wavenumber /cm-1",spc = "I / a.u."))
#check
map01
```
