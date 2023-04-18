
+++
date = "2020-08-07"
lastmod = "2020-08-07"
draft = false
tags = ["R", "PCA","FactoMineR","PCAtools","ade4"]
title = "Functions and default settings for PCA in R"
summary = """
Functions and default settings for PCA in R
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

 - `stats` (`princomp`, `prcomp`)
 - `FactoMineR` (`PCA`)
 - `ade4` (`dudi.pca`)
 - `amap` (`acp`)
 - `PCAtools` (`pca`) from Bioconductor
 - `ca` 
 - `MASS`
 - `ExPosition`

Default settings for center and scale are presented in the next table.

| Function 	| Center 	| Scale 	| Remarks                    	|
|----------	|--------	|-------	|----------------------------	|
| princomp 	| FALSE  	| FALSE 	| using SVD                  	|
| prcomp   	| TRUE   	| FALSE 	|                            	|
| PCA      	|        	|       	| FactoMineR                 	|
| dudi.pca 	|        	|       	| ade4                       	|
| pca      	|        	|       	| PCAtools from Bioconductor 	|
|          	|        	|       	|                            	|

```r

code fragment

```

Insert Image
{{< figure library= "true" src="cloud1.png" title="Word Cloud: Company A" >}}


