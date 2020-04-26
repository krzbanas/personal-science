+++
date = "2019-11-01"
lastmod = "2019-11-01"
draft = false
tags = ["R", "hyperspec", "ggplot2", "plot"]
title = "Ploting FTIR spectrum with ggplot2 - clean theme"
summary = """

"""
math = false
+++



```r
#setting theme
theme_new <- theme_set (theme_bw())
theme_new <- theme_update (axis.text = element_text(size = 14 ),axis.title = element_text(size = 20,face = "bold"))
#faceting on Resolution variable
ggplot (meansRDX02, aes (x = Wavenumber, y = Absorbance, colour = Resolution)) + geom_line (size =1) +  facet_grid(Resolution ~ . )+ scale_x_reverse()+ guides(colour =FALSE)
#manual colour scheme
ggplot (meansRDX02, aes (x = Wavenumber, y = Absorbance, colour = Resolution)) + geom_line (size =1) +  facet_grid(Resolution ~ . )+ scale_x_reverse()+ guides(colour =FALSE) + scale_colour_manual (values = c("red" ,"blue" , "green" , "black" , "violet" ))
```
{{< figure library= "true" src="FTIR_Spectrum_01.png" title="FTIR spectrum with ggplot2 - clean theme" >}}

```r        
#manual colour scheme defined by external variable
cols5 <- c("R04" = "#08306b", "R08" = "#08519c" ,"R16" = "#2171b5", "R32" = "#4292c6" , "R64" = "#6baed6")
ggplot (meansRDX02, aes (x = Wavenumber, y = Absorbance, colour = Resolution)) + geom_line (size =1) +  facet_grid(Resolution ~ . )+ scale_x_reverse()+ guides(colour =FALSE) + scale_colour_manual (values = cols5)
```

{{< figure library= "true" src="FTIR_Spectrum_02.png" title="FTIR spectrum with ggplot2 - clean theme " >}}
