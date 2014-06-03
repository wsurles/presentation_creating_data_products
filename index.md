---
title       : Interactive Documents with R
subtitle    : Slidify + Shiny
author      : Ramnath Vaidyanathan
job         : R Hacker
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap, quiz, shiny, interactive]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
ext_widgets : {rCharts: [libraries/nvd3]}
---

## Slide 2

--- &radio
## Question 1

How many lines of code did I write to make this quiz?

1. 1
2. _10_
3. 100
4. 1000

*** .hint
I used R not javascript/html/css

*** .explanation
```S
Question 1

How many lines of code did I ...
write to make this quiz?

1. 1
2. _10_
3. 100
4. 1000

'*** .hint'
I used R not javascript/html/css

'*** .explanation'
This text went here
```

---
## Interactive Chart

<iframe src='
assets/fig/unnamed-chunk-1.html
' scrolling='no' seamless class='rChart 
nvd3
 '
id=iframe-
chart1c351715064f
></iframe>
<style>iframe.rChart{ width: 100%; height: 400px;}</style>

--- &interactive
## Interactive Console

<textarea class='interactive' id='interactive{{slide.num}}' data-cell='{{slide.num}}' data-results='asis' style='display:none'>require(googleVis)
M1 <- gvisMotionChart(Fruits, idvar = 'Fruit', timevar = 'Year')
print(M1, tag = 'chart')</textarea>

--- 

<div class="row-fluid">
  <div class="span4">
    <form class="well">
      <label class="control-label" for="sex">Choose Sex</label>
      <select id="sex"><option value="Male" selected>Male</option>
<option value="Female">Female</option></select>
      <script type="application/json" data-for="sex" data-nonempty="">{}</script>
      <label class="control-label" for="type">Choose Type</label>
      <select id="type"><option value="multiBarChart" selected>multiBarChart</option>
<option value="multiBarHorizontalChart">multiBarHorizontalChart</option></select>
      <script type="application/json" data-for="type" data-nonempty="">{}</script>
    </form>
  </div>
  <div class="span8">
    <div id="nvd3plot" class="shiny-html-output nvd3 rChart"></div>
  </div>
</div>

---
## Resources

http://slidify.github.io/dcmeetup/#1'


