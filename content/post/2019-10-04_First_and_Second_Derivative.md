+++
date = "2019-10-04"
lastmod = "2019-10-04"
draft = false
tags = ["R", "derivatives", "S-G filter"]
title = "First and Second Derivative"
summary = """

"""
math = false
+++

One of the methods to numerically calculate first and second derivative is to use Savitzy-Golay filter function. It is available in R in `signal` package. Function `sgolayfilt` may be used on all spectra with `apply` function. Order is set by `m` parameter (`m=1` is the first derivative, `m=2` is the second derivative etc.)


```r
library(signal )
# first derivative by S-G filter
deriv1<-apply (a1,1 ,sgolayfilt,p=2 ,n=3,m= 1)
qplotspc(aggregate (deriv1, deriv1$explorder, mean) , mapping = aes (x =.wavelength, y = spc, colour= explorder ))+ scale_x_reverse()+ facet_grid(order ~ expl)
# second derivative by S-G filter
deriv2<-apply (a1,1 ,sgolayfilt,p=2 ,n=3,m= 2)
qplotspc(aggregate (deriv2, deriv2$explorder, mean) , mapping = aes (x =.wavelength, y = spc, colour= explorder ))+ scale_x_reverse()+ facet_grid(order ~ expl)

```
