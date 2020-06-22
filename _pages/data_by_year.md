---
output: html_document
---

```{r, echo=FALSE}
shinyApp(

  ui <- fluidPage(

      titlePanel("Maine Voting Results Map Maker"),

      sidebarLayout(

          sidebarPanel(

              selectInput("dataset", "Year:",
                          choices = c("2012", "2013", "2014", "2015", "2016", "2017")),

              tags$hr(),
              uiOutput("column"),
              hr()
              #,
              #    downloadButton("downloadPlot", "Save PNG")
          ),
          mainPanel(
              plotlyOutput("stateMap"),

              h4("My data", align = "left"),
              tableOutput("contents")
          )



      )
  )
  server <- function(input, output, session) {


      datasetInput <- reactive({
          switch(input$dataset,
                 "2012" = data_2012,
                 "2013" = data_2013,
                 "2014" = data_2014, 
                 "2015" = data_2015, 
                 "2016" = data_2016, 
                 "2017" = data_2017)
      })



      library(dplyr)
      library(tidyverse)
      library(ggplot2)
      library(maps)
      library(plotly)


      output$column <- renderUI({
          df <- datasetInput()
          if (is.null(df)) return(NULL)
          items=names(df) # add back in if you want all columns
          nums <- sapply(df, is.numeric) # keep only number columns
          items=names(nums[nums]) # keep only number columns
          names(items)=items
          selectInput("column", "Choose question", items[3:length(items)])
      })



      output$stateMap <- renderPlotly({

          df <- datasetInput()

          Maine <- map_data("state", region = "Maine")

          p3 <- ggplot() + geom_polygon(data=Maine, aes(x=long, y=lat, group = group),color="white", fill= "grey92") +
              geom_point(data = df, aes_string(x=df$lon, y=df$lat, col = input$column, text = df$city)) + 
              scale_color_gradient2("proportion of yes votes", midpoint = 0.5, low = "red", mid = "grey87", high = "blue", space = "Lab", breaks = seq(0.0,1.0,by=0.1)) +
              theme_void()

          ggplotly(p3, tooltip = c("text", input$column))


      })

  }
)
```

