+++
date = "2021-05-07"
lastmod = "2021-05-07"
draft = false
tags = ["R","ggplot2", "export", "pdf", "patchwork"]
title = "How to save ggplot2 plot to pdf with high resolution?"
summary = """
Save ggplot2 to pdf
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

To save a ggplot2 plot to a pdf file with high resolution, you can use the `ggsave()` function.

Here is an example code snippet:

```r
library(ggplot2)

# create a sample plot
my_plot <- ggplot(mtcars, aes(x=wt, y=mpg)) + 
             geom_point() + 
             labs(title="My Plot")

# save the plot to a pdf file with high resolution
ggsave("my_plot.pdf", plot=my_plot, width=10, height=8, dpi=300)
```
In this example, we first create a sample ggplot2 plot called `my_plot`. Then, we use the `ggsave()` function to save the plot to a pdf file called "my_plot.pdf". We also specify the `width`, `height`, and `dpi` arguments to adjust the size and resolution of the saved plot.

How to combine two plots with adding letters a and b to the top right of the subplots?

You can use the `patchwork` package. Here is an example code:

```r
library(ggplot2)
library(patchwork)

# Create two sample plots
p1 <- ggplot(mtcars, aes(x=wt, y=mpg)) + geom_point() + ggtitle("Plot A")
p2 <- ggplot(mtcars, aes(x=wt, y=disp)) + geom_point() + ggtitle("Plot B")

# Combine the plots using patchwork
(p1 + plot_spacer() + p2) + 
  plot_layout(ncol=2, widths=c(1,1), heights=c(1,1), guides = 'collect') + 
  plot_annotation(tag_levels = 'A', tag_suffix = ")")
```

In this example, `p1` and `p2` are the two ggplot2 plots you want to combine. `plot_spacer()` adds a blank space between the two plots. `plot_layout()` specifies the layout of the combined plots. `plot_annotation()` adds the letters "A" and "B" to the top right of each subplot, and the `tag_suffix` argument specifies the closing parenthesis for the letters.


