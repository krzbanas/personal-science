
+++
date = "2020-08-07"
lastmod = "2020-08-07"
draft = false
tags = ["R", "PCA"]
title = "Functions and default settings for PCA in R"
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

There is a number of packages available in R that may be used for calculating principal components. Generally, there are two methods for classical PCA:
Different packages are using these two functions but with different default settings for data pre-processing (namely: centering and scalling).
One can also use simply `prcomp` and `princomp` functions. Following table shows most popular R packages used for this purpose

`stats` ( princomp, prcomp)
`FactoMineR` (PCA)
`ade4` (dudi.pca)
`amap` (acp)

Testing the appearance:

 1.  single tick `FactoMineR` and some more text
 2.  triple tick ```FactoMineR ``` and some more text
 3.  triple tick with r letter ```r FactoMineR ``` and some more text

```r

code fragment

```

Insert Image
{{< figure library= "true" src="cloud1.png" title="Word Cloud: Company A" >}}


