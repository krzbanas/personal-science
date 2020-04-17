+++
date = "2019-10-04"
lastmod = "2019-10-04"
draft = false
tags = ["R", "derivatives", "S-G filter"]
title = "Title"
summary = """

"""
math = false
+++



```r
library(signal )
# first derivative by S-G filter
deriv1<-apply (a1,1 ,sgolayfilt,p=2 ,n=3,m= 1)
qplotspc(aggregate (deriv1, deriv1$explorder, mean) , mapping = aes (x =.wavelength, y = spc, colour= explorder ))+ scale_x_reverse()+ facet_grid(order ~ expl)
# second derivative by S-G filter
deriv2<-apply (a1,1 ,sgolayfilt,p=2 ,n=3,m= 2)
qplotspc(aggregate (deriv2, deriv2$explorder, mean) , mapping = aes (x =.wavelength, y = spc, colour= explorder ))+ scale_x_reverse()+ facet_grid(order ~ expl)

```
