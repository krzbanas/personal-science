+++
date = "2018-01-05"
lastmod = "2018-01-05"
draft = false
tags = ["R", "hyperspec", "import", "Opus", "ENVI"]
title = "Import ENVI file to R"
summary = """
Import ENVI file (exported chemical map from Bruker Opus) to hyperSpec object
"""
math = false
+++



Following code is used to import ENVI file to hyperSpec object. 
```r
wavenumbers1 <- unlist(read.table(pathtofiles1, quote="\"", comment.char=""))
spc1 <- read.ENVI (pathtofiles2, wavelength = wavenumbers1)
spc1sa$x<-as.numeric(spc1sa$x)
spc1sa$y<-as.numeric(spc1sa$y)

```
It uses `read.ENVI` function from the package hyperSpec, and converts x and y coordinates to numbers by using `as.numeric` function. 
