+++
date = "2019-03-01"
lastmod = "2019-03-01"
draft = false
tags = ["R", "hyperspec", "MCA", "XRF"]
title = "Import MCA data from Amptek detector (SRIXE)"
summary = """
Function to import MCA data to R Environment
"""
math = false
+++
How to define user function `getmca` to import multiple spectra from MCA Amptek detector files. List of files is read by `list.files` function. `ldply` from package `plyr` is used to `read.table`. Dataset is `split` into subsequent column, some cleaning is done: extracted column name with `substr`, other parameters from MCA file are extracted to separate dataset. Finally matrix with channels in the first column and spectra in the following are exported to file with `write.table`. All this is wrapped into function with one parameter: directory name.

```r
getmca <- function(directory ) {
library(plyr)
  file_list <- list.files ()
  dataset <- ldply (file_list, read.table, header=TRUE, sep= "\t")
  l=length (file_list)
  r=rep (file_list, each=2060)
  d1 = as.data.frame (split(dataset, r))
  d2 = data.frame (c( 1:2048 ),d1[ 12:2059 ,1 :l])
  d3= as.matrix (d2)
  # some magic
  class( d3) <- "numeric"
  name=substr (file_list,1 ,nchar (file_list)-4)
  colnames(d3) = c ("Channel", name )
  lt=as.numeric (substr( t(d1 [7,]), 12, 20))
  rt= as.numeric(substr (t( d1[8,]) ,12 ,20 ))
  sd= substr(t (d1[ 9, ]),14 ,32 )
  dead= 100*(rt -lt)/ lt
  sums=colSums (d3[ ,2 :(l+ 1)])
  rate=sums /600
  maxi=apply (d3[ ,2 :(l+ 1)], 2, max)
  description = data.frame (row.names=NULL,name,lt,rt ,sd ,dead,sums,maxi,rate)
  colnames(description) = c ("Name", "LT", "RT" , "Date" , "Dead" , "CS" , "Max" , "Rate")
  write.table (d3, "D:/MCA/data.txt", col.names=F, row.names=F ) 
  }
  
```
