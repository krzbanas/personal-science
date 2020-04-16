

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
+++



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
