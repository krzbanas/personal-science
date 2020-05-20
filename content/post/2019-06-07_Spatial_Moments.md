+++
date = "2019-06-07"
lastmod = "2019-06-07"
draft = false
tags = ["R", "hyperspec", "spatial moments"]
title = "Interpretation of spatial moments"
summary = """
Variance, skewness, kurtosis and others
"""
math = false
+++

Spatial moments are a very simple and powerful way to describe the spatial distribution of values, provided they have a sufficiently strong central tendency, that is, a tendency to cluster around some particular value. This implies that "background" pixel values (e.g. zones where the quantity of interest, such as concentration, is zero), are small. Conversely, zones of high concentration (density, etc.) should also have a high pixel values. This can lead to meaningless results, for example, in the case of uncalibrated images, where (white) background pixels are equal to 255 (for an 8-bit greyscale image).

** Interpretation of spatial moments **

* order 0 = TOTAL MASS [units: concentration, density, etc.]
* order 1 = location of CENTRE OF MASS in x and y from 0,0 [units: L]
* order 2 = VARIANCE around centroid in x and y [units: L^2]
* order 3 = coeff. of SKEWNESS (symmetry) in x and y [units: n/a]
--> =0 : SYMMETRIC distribution
--> <0 : Distribution asymmetric to the LEFT
(tail extends left of centre of mass)
--> >0 : Distribution asymmetric to the RIGHT
(tail extends right of centre of mass)
* order 4 = KURTOSIS (flatness) in x and y [units: n/a]
--> =0 : Gaussian (NORMAL) distribution
--> <0 : Distribution FLATTER than normal
--> >0 : Distribution MORE PEAKED than normal
--> <-1.2: BIMODAL (or multimodal) distribution
** Parameters derived from 2nd moments ** (from Awcock (1995)
"Applied Image Processing")

* ELONGATION (ECCENTRICITY) = Ratio of longest to shortest
distance vectors from the object's centroid to its boundaries
* ORIENTATION = For elongated objects, describes the
orientation (in degrees) of the "long" direction with
respect to horizontal (x axis)
