---
title       : Old Faitful Waiting Time App
subtitle    : Data Products Class Project
author      : Thomas Hartshorne
job         : Coursera Signature Track
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

Are you interested in seeing the most things possible during your time at Yellowstone National Park? Then you wont want to waste any of that valuable time waiting around Old Faithful, with no clue as to when it will erupt again. With this app, you can get an estimate of the time until the next eruption so you can be sure to see all the park has to offer without worrying about missing an eruption. 

---

## How to use the app

#### It's simple! All you have to do is 

1. Input the two digit time (in minutes) of the previous eruption
2. Click Submit!
3. The estimated time until the next eruption is shown

---

## How it works 

The app uses data from the faithful dataset in the datasets package of R. The app:

1. Takes the two digit time inputted by the user, 

2. Finds all eruption times that match that input from the eruption feature of faithful,

3. Calculates the median time until the next eruption of those points. 


--- 

## The function (fake example)

Say the user inputs a time of 3.5. Then the app's function would run like so:

```r
library(datasets)
waitTime = function (time) {
  median(faithful$waiting[round(faithful$eruptions, digits = 2) == time])
}
time = 3.5
waitTime(time = time)
```

```
## [1] 76.5
```

And you can see the output is the resulting median wait time. 

---

## Bugs (and possible solutions)

There are some values that can be inputted for which there is no matching data in the faithful dataset. This could be easily solved with just more recorded data of the Old Faithful eruptions. 






