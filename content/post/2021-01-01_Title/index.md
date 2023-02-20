+++
date = "2021-01-01"
lastmod = "2021-01-01"
draft = true
tags = ["R"]
title = "Airports Map"
summary = """
Map with airports location from csv
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

You can use the `ggplot2` and maps packages in R to create a map of airports from a CSV file. Here's an example code to get you started:

```r
library(ggplot2)
library(maps)

# Load the data from the CSV file
airports <- read.csv("your_csv_file.csv")

# Create a base map using the 'maps' package
world_map <- map_data("world")

# Create a scatterplot of the airports on the map
ggplot() +
  # Add the map data as a layer
  geom_polygon(data = world_map, aes(x = long, y = lat, group = group),
               fill = "white", colour = "black") +
  # Add the airport data as a layer with labels
  geom_text(data = airports, aes(x = Longitude, y = Latitude, label = Name),
            size = 2, hjust = 0, vjust = 1) +
  # Add the airport data as a layer without labels
  geom_point(data = airports, aes(x = Longitude, y = Latitude), size = 1) +
  # Set the aspect ratio and axis labels
  coord_fixed() +
  labs(x = "Longitude", y = "Latitude") +
  # Adjust the theme as desired
  theme_minimal()

```

In this code, we first load the CSV data into a data frame called airports. We then create a base map using the `map_data()` function from the `maps` package. We add this map data as a polygon layer to the plot using `geom_polygon()`, and then add the airport data as a scatterplot layer using `geom_point()`. We use `coord_fixed()` to ensure that the aspect ratio of the map is preserved, and `labs()` to set the axis labels. Finally, we adjust the theme of the plot using `theme_minimal()`, but you can use any other theme you prefer.

Note that this code assumes that the CSV file contains columns called "Name", "Longitude", and "Latitude". If your CSV file has different column names, you'll need to adjust the code accordingly.
