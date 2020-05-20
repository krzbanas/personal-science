
+++
date = "2019-01-04"
lastmod = "2019-01-04"
draft = false
tags = ["R", "tricks"]
title = "Two functions with the same name in two different packages"
summary = """
How can I access always the function from chron package ?
"""
math = false
+++

We have two functions with the same name in two different packages. For example: 
do you need to load two R packages : tseries and chron?
They both have a function named is.weekend
I always have in my environment the function from the second package I loaded.
How can I access always the function from, let say, chron?

You have probably already noticed that the order of loading the packages makes a difference, i.e. the package that gets loaded last will mask the functions in packages loaded earlier.

To specify the package that you want to use, the syntax is:

```r
chron::is.weekend()
tseries::is.weekend()

#In other words, use 
packagename::functionname()
#In addition, if you know that you will always want to use the function in chron, #you can define your own function as follows:
is.weekend <- chron::is.weekend #EDIT

library(chron)
is.weekend.chron <- is.weekend
library(tseries)
# then you can call is.weekend for the tseries version or is.weekend.chron for the chron version

```
