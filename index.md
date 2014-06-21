---
title       : Visualizing Correlation
subtitle    : Coursera Developing Data Products 2014
author      : Brent Cohn
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

### Overview

Understanding the relationship between correlation and linear regression is a key step to getting a better undersatnding of introductory statistics.

This basic tool aims to give students the ability to 

* Visualize "what correlation looks like" on a two dimension plane
* Grasp the difference between negative and positive correlation
* Examine the relationship between correlation and absolute value of residuals 

--- 
### Motivation

Shiny allows you to build dynamic apps using only R. This is perfect to construct interactive tools that allow kids to learn about statistics.

This app demos several key statistical ideas: 
* Linear Regression
* Sample from a normal distribution (generating the random data)
* Correlation
* Residuals

---

### Correlation 

Correlation refers to a broad class of situations where one variable is 'dependent' on another. 

The code below one the following slide generates  two data frames: one with highly correlated variables (dat) and one with almost uncorrelated variables (udat)


---
### R Code


```r
library(mvtnorm)
number <- 10
ymean <- 50
xmean <- 1000
correlation <- 0.9
dat <- rmvnorm(n = number, mean = c(ymean, xmean), sigma = matrix(c(5, correlation * 
    sqrt(50), correlation * sqrt(50), 10), 2, 2))
dat <- data.frame(dat)

correlation <- 0.01
udat <- rmvnorm(n = number, mean = c(ymean, xmean), sigma = matrix(c(5, correlation * 
    sqrt(50), correlation * sqrt(50), 10), 2, 2))
udat <- data.frame(udat)
```


---

### Check it out

To see what correlated and uncorrelated variables look like when plotted, check out: 
[The Shiny App!](https://bcohn.shinyapps.io/CourseraShiny/)

and of course

[The code](https://github.com/Bcohn/DataProductsShiny)


