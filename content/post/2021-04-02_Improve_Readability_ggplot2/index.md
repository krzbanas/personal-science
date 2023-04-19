+++
date = "2021-04-02"
lastmod = "2021-04-02"
draft = false
tags = ["R","ggplot2","readability","theme"]
title = "How to change default ggplot2 settings to improve readability of the plot?"
summary = """
Improving readability of the ggplot2 
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

To change the default ggplot2 settings and improve the readability of the plot, you can use the `theme()` function to modify various elements such as the font size, font family, axis text, legend text, and background color. Here are some common modifications you can make:

- Increase the font size: `theme(text = element_text(size = 14))`
- Change the font family: `theme(text = element_text(family = "Arial"))`
- Change the axis text color: `theme(axis.text = element_text(color = "black"))`
- Change the legend text color: `theme(legend.text = element_text(color = "black"))`
- Change the background color: `theme(panel.background = element_rect(fill = "white"))`
- Remove the grid lines: `theme(panel.grid = element_blank())`
- Increase the size of the legend text: `theme(legend.text = element_text(size = 12))`
- Increase the size of the axis labels: `theme(axis.title = element_text(size = 14))`

You can modify any number of elements using the `theme()` function. Just make sure to add it at the end of your ggplot code, like here: 

```r
ggplot(data, aes(x, y)) + geom_point() + theme(...).
```



