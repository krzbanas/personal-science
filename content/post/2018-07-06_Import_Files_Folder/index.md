+++
date = "2018-07-06"
lastmod = "2018-07-06"
draft = false
tags = ["R", "hyperSpec", "import", "csv"]
title = "Import multiple txt files (folder) to single hyperSpec object"
summary = """
Import multiple txt files to single hyperSpec object with timestamps extracted from filenames
"""
math = false
+++
Import multiple text files from one folder by using `read.table` function. Remember about setting proper column separator. In `for` loop spectrum from the first file in the list is write to the first row of spc `matrix`. In this example additional `data.frame` is created from the part of the filenames to add time stamps. Function `strptime` is used to convert characters to time format, function `diff` to calculate the differences between subsequent experimental points  and function `cumsum` to calculated cumulative time elapsed from the beginning of the experiment.

```r
# full path to the data files
dataTR <- file.path ("L:/2015_05_SNR_FTIR/MODEL_MIR/TR")
#load data
#read list of files in the folder
files <- list.files (path = dataTR)
#read first spectrum to buffor, column separator is comma here
#IMPORTANT check what is the separator in your data file
#and change accordingly in row with command read.table
#typical values are space " " coma "," or tab "\t" - below coma
buffer <- read.table (file.path(dataTR,files [1 ]), sep= "," )
#allocate matrix number of columns is equal the number of rows
#in spectrum file number of rows is equal the number of spectra files
spc <- matrix ( ncol = nrow (buffer), nrow = length (files))
#write to first row spectrum number 1
spc [1 , ] <- buffer [, 2 ]
# then rest of the data
for ( f in seq (along = files)[- 1]) {
  buffer <- read.table (file.path(dataTR,files [f ]), sep= ",")
  spc [f, ] <- buffer[, 2]
}
# X-axis vector
wavenumber = buffer [, 1 ]
#vector with additional data
#could be a data frame with filenames
#d = data.frame(files)
#or time of the experiment
t1 = as.numeric (substring(files,7,12))
#or time difference between  the points
z1 <- strptime(t1, "%H%M%S")
dif1=diff (z1)
#cumulative difference in seconds, 0 added at the beginning
dif2=data.frame (c( 0, cumsum(as.numeric (dif1))))
colnames(dif2 )=c( "time")
#make hyperSpec object
tr= new ("hyperSpec", wavelength = wavenumber, spc = spc, data= dif2)
#check if everything is OK
tr
```
