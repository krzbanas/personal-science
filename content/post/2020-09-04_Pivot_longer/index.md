+++
date = "2020-09-04"
lastmod = "2020-09-04"
draft = false
tags = ["R", "]
title = "Convert wide to long with the function `tidyr::pivot_longer`"
summary = """
Summary
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
Sometimes we need to convert our hyperspectral object into data.frame. And for some visualization methods we need to have this data.frame in a long format (one column with wavenumbers another with the intesities and third with spectrum description: in the code chunk below with cluster number: Cl1 or Cl2 or Cl3) not in a wide format (first column with wavenumbers and subsequent columns with the spectra and their intensities). Function `hyperSpec::as.t.df` gives wide version as the output. We could use `tidyr::pivot_longer` function to convert it to long format. First argument tells which columns should be converted (here all except Wavenumber), `names_to` defines the name of the variable describing the spectrum,`values_to` define what should be the values for this variable.



```r
library(tidyr)
mean_cl3 <- as.t.df(mean_clusters3)
colnames(mean_cl3)<-c("Wavenumber", "Cl1","Cl2","Cl3")
mean_cl3_long<-mean_cl3 %>%pivot_longer(!Wavenumber, names_to = "Cluster", values_to = "mean")
```

Insert Image
{{< figure library= "true" src="cloud1.png" title="Word Cloud: Company A" >}}
