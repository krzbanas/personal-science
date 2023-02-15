+++
date = "2022-03-04"
lastmod = "2022-03-04"
draft = true
tags = ["R","tidyr","long data"]
title = "Test"
summary = """
Test
"""
math = false

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = "Caption"
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"

+++
Description



```r
library(tidyr)
mean_cl3 <- as.t.df(mean_clusters3)
colnames(mean_cl3)<-c("Wavenumber", "Cl1","Cl2","Cl3")
mean_cl3_long<-mean_cl3 %>%pivot_longer(!Wavenumber, names_to = "Cluster", values_to = "mean")
```

