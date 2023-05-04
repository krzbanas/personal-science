+++
date = "2023-03-03"
lastmod = "2023-03-03"
draft = false
tags = ["R", "datapasta"]
title = "Hidden R gems: package packman"
summary = """
datapasta: Copy-pasting data just got easier! datapasta lets you seamlessly paste data from spreadsheets or tables directly into your R scripts as data frames or tibbles. It's a real time-saver!
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

The `pacman` package is an R package management tool that combines the functionality of base library related functions into intuitively named functions. This package is ideally added to .Rprofile to increase workflow by reducing time recalling obscurely named functions, reducing code and integrating functionality of base functions to simultaneously perform multiple actions.

Function names in the `pacman` package follow the format of p_xxx where 'xxx' is the task the function performs. For instance the `p_load` function allows the user to load one or more packages as a more generic substitute for the library or require functions and if the package isn't available locally it will install it for you.

