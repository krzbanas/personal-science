+++
date = "2018-08-03"
lastmod = "2018-08-03"
draft = false
tags = ["R", "hyperspec", "Import", "csv"]
title = "Import spectra from text matrix"
summary = """
Import csv matrix with wavenumbers in the first column.
"""
math = false
+++



```r
# import csv matrix with wavenumbers in the first column
# and the spectra in following columns
# first row is a header
# extra data are taken from column names (header row) - first k characters
k=6
path01<-"D:/New_Zealand_20190815/C_4/C_4_both.csv"
library(hyperSpec)
dataset01 <- read.csv(path01)
addata<-as.data.frame(substring(colnames(dataset01[,-1]), 1,k))
colnames(addata)<-c("Sample")
wavenumber<-as.vector(t(dataset01[,1]))
spectra<-t(as.matrix(dataset01[,-1]))
#make hyperSpec object
object01<-new("hyperSpec", wavelength = wavenumber,
              spc = spectra, data=addata)
#check
object01
```
