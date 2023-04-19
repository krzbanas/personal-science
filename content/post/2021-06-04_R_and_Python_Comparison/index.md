+++
date = "2021-06-04"
lastmod = "2021-06-04"
draft = false
tags = ["R", "Python"]
title = "R and Python Comparison"
summary = """
R and Python comparison for simple spectral processing
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
Code chunk in R and it's equivalent in Python that reads spectrum from csv, subtracts baseline, perform area normalization and plot the spectrum in high quality.

In R:

```r
library(tidyverse)
library(ggplot2)
library(readr)
library(purrr)
library(scales)

# Read spectrum data from csv
spectrum <- read_csv("spectrum.csv")

# Subtract baseline
spectrum_baseline <- spectrum %>%
  mutate(baseline = min(intensity)) %>%
  mutate(intensity = intensity - baseline)

# Perform area normalization
spectrum_normalized <- spectrum_baseline %>%
  mutate(area = sum(intensity)) %>%
  mutate(intensity = intensity / area)

# Plot spectrum
ggplot(spectrum_normalized, aes(wavelength, intensity)) +
  geom_line(color = "blue") +
  scale_x_continuous(name = "Wavelength (nm)", limits = c(200, 1000)) +
  scale_y_continuous(name = "Intensity (a.u.)") +
  theme_minimal()
```

In Python:

```python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

# Read spectrum data from csv
spectrum = pd.read_csv("spectrum.csv")

# Subtract baseline
baseline = min(spectrum["intensity"])
spectrum["intensity"] = spectrum["intensity"] - baseline

# Perform area normalization
area = sum(spectrum["intensity"])
spectrum["intensity"] = spectrum["intensity"] / area

# Plot spectrum
plt.plot(spectrum["wavelength"], spectrum["intensity"], color="blue")
plt.xlabel("Wavelength (nm)")
plt.ylabel("Intensity (a.u.)")
plt.xlim([200, 1000])
plt.ylim([0, max(spectrum["intensity"])])
plt.ticklabel_format(style='sci', axis='y', scilimits=(0,0))
plt.minorticks_on()
plt.grid(b=True, which='major', color='gray', linestyle='-')
plt.grid(b=True, which='minor', color='gray', linestyle='--')
plt.show()
```
