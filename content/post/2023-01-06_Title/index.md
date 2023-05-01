+++
date = "2023-01-06"
lastmod = "2023-01-06"
draft = false
tags = ["R", "colorfindr"]
title = "Hidden R gems: package colorfindr"
summary = """
Summary
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

Example of code with `colorfindr` package in R showing the posibilities

```r

# Install and load the colorfindr package
install.packages("colorfindr")
library(colorfindr)

# Load an image to analyze
img <- load.image("https://images.unsplash.com/photo-1621949014695-c2dd07ff54ed")

# Extract dominant colors from the image
dominant_colors <- extract_colors(img, n = 5)

# Display the dominant colors with their color names
show_colors(dominant_colors)

# Generate a palette of colors that match the dominant colors
matching_palette <- generate_palette(dominant_colors, n = 8)

# Display the matching palette
show_colors(matching_palette)
```

In this code, we first install and load the `colorfindr` package. Then we load an image from the web using the `load.image()` function. We use the `extract_colors()` function to extract the five dominant colors from the image. We then use `show_colors()` to display the dominant colors with their color names.

Next, we use the `generate_palette()` function to generate a palette of eight colors that match the dominant colors. Finally, we use `show_colors()` to display the matching palette.

The `colorfindr` package offers many other functions and options for color extraction and matching. This example demonstrates just a few of the possibilities.
