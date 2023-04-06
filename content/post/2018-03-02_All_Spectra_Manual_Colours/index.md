+++
date = "2018-03-02"
lastmod = "2018-03-02"
draft = false
tags = ["R", "hyperSpec", "palette"]
title = "All Spectra with manual colours"
summary = """
Ploting all spectra from one hyperSpec object with colours set manually
"""
math = false
+++


Plot all spectra from the hyperSpec object with manually set colours. Palette define by `brewer.pal` and `colorRampPalette` functions.
Manual selection of palette is applied by `scale_color_manual` parameter.
```r
nspectra<-nrow(object01)
pal01<-colorRampPalette(brewer.pal(nspectra, "Set1")) 
 
all01<-ggplot(object02, aes (x = .wavelength, y = spc, colour = Sample))+ geom_line (size =lsize1) +
  scale_x_reverse()+
  scale_color_manual(values = pal01(nspectra))+
  labs(x=expression(bold(paste ("Wavenumber", " [",cm ^-1, "]"))), y = "mIRage Amplitude [a.u.]" )
all01
```

