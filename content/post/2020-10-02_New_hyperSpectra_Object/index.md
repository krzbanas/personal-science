+++
date = "2020-10-02"
lastmod = "2020-10-02"
draft = false
tags = ["R", "hyperSpec"]
title = "create a new hyperspectral object with the hyperSpec package in R"
summary = """
Create a new hyperspectral object
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

To create a new hyperspectral object with the hyperSpec package in R, you can use the `new` function. Here is an example:

```r
library(hyperSpec)

# create example data matrix with 3 spectra and 4 wavelength channels
data_matrix <- matrix(c(1,2,3,4,5,6,7,8,9,10,11,12), nrow = 3, ncol = 4)

# create a new hyperspectral object with the data matrix
hs_object <- new("hyperSpec", wavelength = 400:700, spc = data_matrix)

# print the hyperspectral object
print(hs_object)

```

In this example, we first create an example data matrix with 3 spectra and 4 wavelength channels. Then we use the `new` function to create a new hyperspectral object called `hs_object`. We specify the wavelength range using the `wavelength` argument and the data matrix using the `spc` argument. Finally, we print the hyperspectral object to see the contents.

You can adjust the number of spectra and wavelength channels, as well as the actual values in the data matrix, to suit your needs.

