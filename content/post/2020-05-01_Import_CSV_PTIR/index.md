+++
date = "2020-05-01"
lastmod = "2020-05-01"
draft = false
tags = ["R", "hyperspec", "import", "o-PTIR"]
title = "Import csv matrix from PTIR Studio"
summary = """
Method for importing to R csv matrix from mIRage device
"""
math = false

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = "Photo by me"
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"


+++

Import csv matrix with wavenumbers in the first column and spectra in the subsequent columns (export from PTIR Studio). Matrix is read by `read.csv` function. Coordinates are rounded to 2 decimal places by function `round`.

```r
f="iNor_BA1_hyper_20191209.csv"
path01<-here::here("DATA",f)
dataset01 <- read.csv(path01)
wavenumbers  <- read.csv(path01, header = FALSE, nrow = 1)
wavenumber<-as.vector(t(wavenumbers[3:length(wavenumbers)]))
spectra<-as.matrix(dataset01[,-c(1:2)])
d1<-as.data.frame(dataset01[,1])

#there is a bug in the export to csv in PTIR Studio 4.1
#causing map being flipped in Y direction
#line below there is a fix for this
#if this is corrected sort should be replaced by non sorted
#d2<-as.data.frame(sort(dataset01[,2]))

d2<-as.data.frame(dataset01[,2])
addata<-cbind(d1,d2)
colnames(addata)<-c("x","y")
addata1<-round(addata,digits=2)
hypspec1<-new("hyperSpec", wavelength = wavenumber,
              spc = spectra, data=addata1)
```
