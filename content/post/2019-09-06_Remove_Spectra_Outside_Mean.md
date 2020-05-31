
+++
date = "2019-09-06"
lastmod = "2019-09-06"
draft = false
tags = ["R", "hyperspec", "outlier"]
title = "Removing Spectra outside mean ± n SD"
summary = """

"""
math = false
+++

How to define the fuction to remove spectra outside the mean ± n times SD? Function `mean_sd_filter` first subtracts mean value then sets logical condition for values to be lower than mean plus n times SD or higher than mean minus n times SD. Output of this function is logical matrix. By using `apply` twice one can extract spectra inside the given range.


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





