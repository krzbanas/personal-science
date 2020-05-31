+++
date = "2019-07-05"
lastmod = "2019-07-05"
draft = false
tags = ["R", "knitr", "tables", "reports"]
title = "Packages to print tables in reports"
summary = """
knitr, pander and xtable
"""
math = false
+++

There are a number of packages to correctly display tables in automatically generated reports (html, pdf).
Native `knitr` package function is named `kable`.

```{r kable }
n <- 100
x <- rnorm(n )
y <- 2*x + rnorm (n)
out <- lm(y ~ x)
library(knitr)
kable(summary (out)$ coef, digits=2)
```
Another option comes from  `pander` package http://rapporter.github.io/pander/

```{r pander }
n <- 100
x <- rnorm(n )
y <- 2*x + rnorm (n)
out <- lm(y ~ x)
library(pander)
panderOptions("digits" , 2)
pander(out)
```

Finally there is package called 'xtable' https://cran.r-project.org/web/packages/xtable/index.html and the function `xtable`

```{r xtable, results ="asis"}
n <- 100
x <- rnorm(n )
y <- 2*x + rnorm (n)
out <- lm(y ~ x)
library(xtable)
tab <- xtable (summary(out)$coef , digits=c (0, 2, 2, 1, 2))
print(tab, type ="html")
```
