---
title       : Creating an approachable data product 
subtitle    : R + Shiny
author      : William Surles
job         : Product Data Scientist @ Rally Software
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap, quiz, shiny, interactive]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
ext_widgets : {rCharts: [libraries/nvd3]}
---

<!-- Limit image width and height -->
<style type='text/css'>
img {
    max-height: 400px;
    max-width: 800px;
}
</style>

<!-- Center image on slide -->
<script src="http://ajax.aspnetcdn.com/ajax/jQuery/jquery-1.7.min.js"></script>
<script type='text/javascript'>
$(function() {
    $("p:has(img)").addClass('centered');
});
</script>

## A D3 chart
<iframe src='
assets/fig/unnamed-chunk-1.html
' scrolling='no' seamless class='rChart 
nvd3
 '
id=iframe-
chart1c351715064f
></iframe>
<style>iframe.rChart{ width: 100%; height: 400px;}</style>

--- &radio
## Quiz

How many lines of code did I write to make this chart?

1. _1_
2. 10
3. 100
4. 1000

*** .hint
I used R not javascript/html/css

*** .explanation
```s
n1 <- nPlot(y ~ x, group, type, data)
```

---
## About Me
- Mech Engr -> Building Energy Researcher -> Data Scientist
- Product Data Scientist at Rally Software
- Love exploring tools and techniques

---
## Who is Rally?
![img](assets/img/rally-software.png)

---
## Who is Rally?

- Founded in Boulder
- 11 Years Old
- NYSE: RALY
- Focused on Business Agility 

---
## How I work with teams
- UX team
- Product owners and developer teams
- Data engineers and programmers
- I focus on data analytics to improve product usability 

--- .segue bg:blue

## What

---
## Product Data Hub
![img](assets/img/data_hub.png)

---
## Product Data Hub
- Its a full featured bootstrap webpage
- Built with R and Shiny
- Interactive analysis
- Hub to share all analyses with Product team

--- .segue bg:blue

## Why

---
## Data Product
* Teams can easily slice and dice data as needed
* Don't have to 're-run' analysis. Always updated and available
* One place to see everything that matters
* Web functionality (navigation, modals, styles)

---
## Product Data Hub
![img](assets/img/data_hub.png)

--- .segue bg:blue

## How

---
## Build a simple shiny App
![img](assets/img/histogram_example.png)

---
## ui.R

```r
shinyUI(pageWithSidebar(
  headerPanel("Simple Histogram App"),
  sidebarPanel(
    selectInput(inputId = "n_breaks",
                label = "Number of bins",
                choices = c(10, 20, 25, 30, 50),
                selected = 20
                )
  ),
  mainPanel(
    plotOutput(outputId = "main_plot")
  )
))
```

---
## server.r

```r
shinyServer(function(input,output){

  output$main_plot <- renderPlot({  
    hist(faithful$eruptions,
         breaks = as.numeric(input$n_breaks),
         col = "green",
         xlab = "Duration (minutes)")  
  })
})
```


---
## Add Interactive Charts

<iframe src='
assets/fig/unnamed-chunk-2.html
' scrolling='no' seamless class='rChart 
nvd3
 '
id=iframe-
chart1c355961a45e
></iframe>
<style>iframe.rChart{ width: 100%; height: 400px;}</style>

---
## Add Interactive Charts


```r
require(rCharts)
haireye = as.data.frame(HairEyeColor)
n1 <- nPlot(Freq ~ Hair, 
  group = 'Eye',
  data = subset(haireye, Sex == 'Male'),
  type = 'multiBarChart'
)
n1
```

---
## Explore interactive analysis and chart

![img](assets/img/interactive_analysis.png)

---
## Check out examples
http://shiny.rstudio.com/gallery/kmeans-example.html

![img](assets/img/cluster_example.png)

---
## Add more input options
http://shiny.rstudio.com/gallery/widgets-gallery.html

![img](assets/img/widgets.png)

---
## Add more functionality
http://shiny.rstudio.com/reference/shiny/latest/

![img](assets/img/functions.png)

--- 
## Add navigation
http://shiny.rstudio.com/reference/shiny/latest/

![img](assets/img/nav.png)

---
## Chose a theme
http://bootswatch.com/

![img](assets/img/theme.png)

--- 
## Embed other pages

![img](assets/img/tableau_dashboard.png)

---
## Embed other pages


```r
tabPanel("tableau", includeHTML("tableau_dashboard.html"), align = 'center')
```
- Tableau
- Splunk
- You tube
- Whatever

---
## Resources

Example slide deck http://slidify.github.io/dcmeetup/#1

D3 in slides http://ramnathv.github.io/rCharts/

rCharts http://ramnathv.github.io/rCharts/

Shiny http://shiny.rstudio.com/

My tutorial https://github.com/wsurles/shiny_workshop




