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
Here's a simple Shiny application that reads a CSV file with spectra in the rows and plots one or more of them based on user selection:

```r
library(shiny)
library(ggplot2)

# Define UI
ui <- fluidPage(
  titlePanel("Spectrum Plotter"),
  sidebarLayout(
    sidebarPanel(
      fileInput("file", "Choose CSV file",
                accept = c(".csv")
      ),
      checkboxGroupInput("spectra", "Select spectra to plot:",
                         choices = NULL
      ),
      actionButton("plot", "Plot Spectra")
    ),
    mainPanel(
      plotOutput("plot")
    )
  )
)

# Define server
server <- function(input, output) {
  
  # Read CSV file
  data <- reactive({
    req(input$file)
    read.csv(input$file$datapath)
  })
  
  # Update checkbox choices based on data
  observeEvent(data(), {
    updateCheckboxGroupInput(session, "spectra", choices = names(data()))
  })
  
  # Plot selected spectra
  output$plot <- renderPlot({
    req(input$plot)
    ggplot(data(), aes_string(x = names(data())[1], y = input$spectra)) +
      geom_line()
  })
  
}
```r

Run the application
```r
shinyApp(ui = ui, server = server)
```

In this application, the user is prompted to select a CSV file with spectra in the rows. Once a file is selected, the application reads the data and updates the checkbox options with the names of the spectra columns. The user can select one or more spectra to plot and click the `Plot Spectra` button to generate the plot. The plot is rendered using `ggplot2`, with the x-axis set to the first column of the data (presumably wavelength or frequency) and the y-axis set to the selected spectra columns.



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

In this code, we first install and load the colorfindr package. Then we load an image from the web using the load.image() function. We use the extract_colors() function to extract the five dominant colors from the image. We then use show_colors() to display the dominant colors with their color names.

Next, we use the generate_palette() function to generate a palette of eight colors that match the dominant colors. Finally, we use show_colors() to display the matching palette.

The colorfindr package offers many other functions and options for color extraction and matching. This example demonstrates just a few of the possibilities.
