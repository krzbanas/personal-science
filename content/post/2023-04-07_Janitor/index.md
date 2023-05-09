+++
date = "2023-04-07"
lastmod = "2023-04-07"
draft = false
tags = ["R", "janitor", "cleaning"]
title = "Hidden R gems: package janitor"
summary = """
janitor: Data cleaning made easy! janitor helps you clean up messy data in a flash, with functions to remove special characters, whitespace, and more. Say hello to tidy data!
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


`janitor` has simple functions for examining and cleaning dirty data. It was built with beginning and intermediate R users in mind and is optimized for user-friendliness. Advanced R users can perform many of these tasks already, but with `janitor` they can do it faster and save their thinking for the fun stuff.

The main `janitor` functions:

- perfectly format `data.frame` column names;
- create and format frequency tables of one, two, or three variables - think an improved `table()`;
- provide other tools for cleaning and examining `data.frames`.
The tabulate-and-report functions approximate popular features of SPSS and Microsoft Excel.

`janitor` is a #tidyverse-oriented package. Specifically, it plays nicely with the %>% pipe and is optimized for cleaning data brought in with the `readr` and `readxl` packages.


