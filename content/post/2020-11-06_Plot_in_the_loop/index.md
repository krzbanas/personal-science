+++
date = "2020-11-06"
lastmod = "2020-11-06"
draft = false
tags = ["R", "plot", "loop", "automatation"]
title = "Ploting in the loop"
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
To plot in a loop for all elements of a vector in R, you can use a for loop to iterate over each element of the vector and create a separate plot for each element. Here is an example:

```r
# create example data
x <- seq(0, 10, length.out = 100)
y <- sin(x)

# create example vector of values to plot
values_to_plot <- c(1, 5, 8)

# create a loop to plot for all values in the vector
for (value in values_to_plot) {
  # create a subset of the data for the current value
  subset_data <- data.frame(x = x, y = y)
  subset_data <- subset_data[round(subset_data$x) == value, ]
  
  # create a plot for the current value
  plot(subset_data$x, subset_data$y, main = paste("Value =", value))
}

```

In this example, we first create some example data for the plot. We also create an example vector called `values_to_plot` with three values that we want to plot. We then use a `for` loop to iterate over each value in the vector. For each value, we create a subset of the data that only includes the points where the x value is equal to the current value. We then create a plot for the current value using the subsetted data.

You can modify this code to suit your specific needs by changing the data and values to plot.
