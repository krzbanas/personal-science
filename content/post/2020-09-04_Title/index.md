+++
date = "2020-09-04"
lastmod = "2020-09-04"
draft = true
tags = ["R", "]
title = "Title"
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
Sometimes we need to convert our hyperspectral object into data.frame. And for some visualization methods we need to have this data.frame in a long (one column with wavenumbers another with the intesities and third with spectrum description (in the code chunk below with cluster number: CL1 or Cl2 or Cl3)Convert wide to long with library(tidyr) function pivot_longer
Some text `worldcloud` and other.

```r

mean_cl3 <- as.t.df(mean_clusters3)
colnames(mean_cl3)<-c("Wavenumber", "Cl1","Cl2","Cl3")
mean_cl3_long<-mean_cl3 %>%pivot_longer(!Wavenumber, names_to = "Cluster", values_to = "mean")

```

Insert Image
{{< figure library= "true" src="cloud1.png" title="Word Cloud: Company A" >}}
