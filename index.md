---
title       : Data Visualization of mtcars DataSet
subtitle    : 
author      : godwinls
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Intro

THis is a visualization of two variables relationship in mtcars dataset

--- .class #id 

## Dataset

The data was extracted from the 1974 Motor Trend US magazine, and comprises fuel consumption and 10 aspects of automobile design and performance for 32 automobiles (1973-74 models).

```r
library(datasets)
head(mtcars, 5)
```

```
##                    mpg cyl disp  hp drat    wt  qsec vs am gear carb
## Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
## Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
## Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
## Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
## Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
```

---

## Format

A data frame with 32 observations on 11 variables.

[, 1]         mpg	 Miles/(US) gallon

[, 2]	 cyl	 Number of cylinders

[, 3]	 disp	 Displacement (cu.in.)

[, 4]	 hp	 Gross horsepower

[, 5]	 drat	 Rear axle ratio

[, 6]	 wt	 Weight (lb/1000)

[, 7]	 qsec	 1/4 mile time

[, 8]	 vs	 V/S

[, 9]	 am	 Transmission (0 = automatic, 1 = manual)

[,10]	 gear	 Number of forward gears

[,11]	 carb	 Number of carburetors

---

## linear regression code


```r
regout <- reactive({
                lm(as.formula(paste(input$yaxis, " ~ ",paste(input$xaxis))), data = mtcars)
        })
```

