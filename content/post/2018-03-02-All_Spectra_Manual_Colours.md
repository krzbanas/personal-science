+++
date = "2018-03-02"
lastmod = "2018-03-02"
draft = false
tags = ["R", "hyperspec"]
title = "All Spectra with manual colours"
summary = """

"""
math = false
+++


Plot all spectra from the hyperSpec object with manually set colours
```r
nspectra<-nrow(object01)
pal01<-colorRampPalette(brewer.pal(nspectra, "Set1")) 
 
all01<-ggplot(object02, aes (x = .wavelength, y = spc, colour = Sample))+ geom_line (size =lsize1) +
  scale_x_reverse()+
  scale_color_manual(values = pal01(nspectra))+
  labs(x=expression(bold(paste ("Wavenumber", " [",cm ^-1, "]"))), y = "mIRage Amplitude [a.u.]" )
all01
```
