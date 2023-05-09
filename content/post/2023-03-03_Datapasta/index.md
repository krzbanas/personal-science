+++
date = "2023-03-03"
lastmod = "2023-03-03"
draft = false
tags = ["R", "datapasta", "paste"]
title = "Hidden R gems: package datapasta"
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

`datapasta` is about reducing resistance associated with copying and pasting data to and from R. It is a response to the realisation that I often found myself using intermediate programs like Sublime to munge text into suitable formats. Addins and functions in datapasta support a wide variety of input and output situations, so it (probably) "just works". Hopefully tools in this package will remove such intermediate steps and associated frustrations from our data slinging workflows.

At the moment this package contains these RStudio addins that paste data to the cursor:

`tribble_paste` which pastes a table as a nicely formatted call to `tibble::tribble()`
Recommend Ctrl + Shift + t as shortcut. Table can be delimited with tab, comma, pipe or semicolon.

`vector_paste` which will paste delimited data as a vector definition, e.g. c("a", "b") etc.
Recommend Ctrl + Alt + Shift + v as shortcut.

`vector_paste_vertical` which will paste delimited data as a vertically formatted vector definition.
Recommend Ctrl + Shift + v as shortcut

example output:
c("Mint",
  "Fedora",
  "Debian",
  "Ubuntu",
  "OpenSUSE")
 
 `df_paste` which pastes a table on the clipboard as a standard data.frame definition rather than a tribble call. This has certain advantages in the context of reproducible examples and educational posts. Many thanks to Jonathan Carroll for getting this rolling and coding the bulk of the feature.
Recommend Ctrl + Alt + Shift + d as shortcut.
`dt_paste` which is the same as `df_paste`, but for data.table.
