+++
date = "2018-11-02"
lastmod = "2018-11-02"
draft = false
tags = ["R", "hyperspec"]
title = "Group names extracted from filenames"
summary = """
Group names extracted from filenames as factors
"""
math = false
+++



```r
explosive<-substr(files, 1, 4)
explosive<-factor(explosive, levels=c ("C_4_", "PETN", "RDX_", "TNT_"), labels=c ("C-4", "PETN","RDX", "TNT"))
d1 = data.frame(files, explosive)
#create hyperSpec object
a1= new ("hyperSpec", wavelength = wavenumber, spc = spc, data=d1)
a1
```
