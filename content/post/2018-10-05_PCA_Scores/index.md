

+++
date = "2018-10-05"
lastmod = "2018-10-05"
draft = false
tags = ["R", "PCA"]
title = "PCA Scores ploted with ggplot2"
summary = """
PCA Scores ploted with ggplot2
"""
math = false


# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = "First Principal Component Map"
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"

+++

Calculating principal components of spectra matrix with function `prcomp`. Function `decomposition` is used to re-import results of the analysis to `hyperspec` object. Then first three principal components are visualised as false colour maps (`matlab.palette`) with `qplotmap` function.

```r
pca <- prcomp(spc1sa[[]], scale. = TRUE, rank. = 10)
scores <- decomposition (spc1sa, pca$x, label.wavelength = "PC", label.spc = "score / a.u.")
#PC1
qplotmap (scores[,,1]) + scale_fill_gradientn (colours = matlab.palette ())
#PC2
qplotmap (scores[,,2]) + scale_fill_gradientn (colours = matlab.palette ())
#PC3
qplotmap (scores[,,3]) + scale_fill_gradientn (colours = matlab.palette ())
```

{{< figure library= "true" src="PCA_Score.png" title="First Principal Component" >}}
