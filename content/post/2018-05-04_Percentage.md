+++
date = "2018-05-04"
lastmod = "2018-05-04"
draft = false
tags = ["R", "hyperspec", "Clusters"]
title = "Calculate the number and percentage of spectra in each cluster"
summary = """

"""
math = false
+++



```r
#add cluster membership to hyperSpec object
map01$clusters <- as.factor (cutree (dendrogram, k = 5))
levels (map01$clusters) <- c ("Cl_01", "Cl_02", "Cl_03", "Cl_04", "Cl_05")
map01
hyperSpec object
   4096 spectra
   4 data columns
   1556 data points / spectrum
wavelength: Wavenumber /cm-1 [numeric] 3897.4 3895.5 ... 898.7
data:  (4096 rows x 4 columns)
   1. x:  [numeric] 0.0 2.7 ... 170.1
   2. y:  [numeric] 0 0 ... 170.1
   3. spc: I / a.u. [matrix1556] 0.252 -0.042 ... 0.066
   4. clusters: clusters [factor] Cl_01 Cl_01 ... Cl_01
df01<-as.data.frame(table(map01$clusters))
df01
   Var1 Freq
1 Cl_01 1725
2 Cl_02  785
3 Cl_03  635
4 Cl_04  775
5 Cl_05  176
df01$percent<- prop.table(df01$Freq)
   Var1 Freq    percent
1 Cl_01 1725 0.42114258
2 Cl_02  785 0.19165039
3 Cl_03  635 0.15502930
4 Cl_04  775 0.18920898
5 Cl_05  176 0.04296875
```
