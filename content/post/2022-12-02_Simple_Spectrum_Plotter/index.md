+++
date = "2022-12-02"
lastmod = "2022-12-02"
draft = false
tags = ["R", "shiny"]
title = "Simple Spectrum Plotter"
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
```

Run the application
```r
shinyApp(ui = ui, server = server)
```

In this application, the user is prompted to select a CSV file with spectra in the rows. Once a file is selected, the application reads the data and updates the checkbox options with the names of the spectra columns. The user can select one or more spectra to plot and click the `Plot Spectra` button to generate the plot. The plot is rendered using `ggplot2`, with the x-axis set to the first column of the data (presumably wavelength or frequency) and the y-axis set to the selected spectra columns.
