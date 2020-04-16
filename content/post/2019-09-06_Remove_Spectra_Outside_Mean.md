
+++
date = "2019-09-06
lastmod = "2019-09-06"
draft = false
tags = ["R", "hyperspec"]
title = "Removing Spectra outside mean ± n sd"
summary = """

"""
math = false
+++



```r
# define the function
mean_sd_filter <- function (x, n = 5) {
x <- x - mean (x)
s <- n * sd (x)
(x <= s) & (x > -s)
}
# logical matrix
OK <- apply (chondro [[]], 2, mean_sd_filter, n = 4) 
spc.OK <- chondro [apply (OK, 1, all)]
plot (chondro [! apply (OK, 1, all)])
i <- which (! OK, arr.ind = TRUE)
points (wl (chondro) [i [,2]], chondro[[!OK]], pch = 19, col = "red", cex = 0.5)
```





