---
title       : Course Project Reproducible Pitch
subtitle    : Body Mass Index (BMI) Calculator
author      : shaf
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

* The body mass index (BMI) is a statistical measurement using a person’s height and weight to determine their “healthy” body weight.

* BMI is controversial, because it does not actually measure a person’s percentage body fat.

* It just displays what a healthy weight range would be for a person’s height.

* Regarding the BMI measure, the World Health Organization (WHO) proposes the following classification:
```
    Starvation : BMI < 14.9
    Underweight : BMI [15-18.4]
    Normal : BMI [18.5-22.9]
    Overweight : BMI [23-27.5]
    Obese : BMI [27.6-40]
    Morbidly Obese : BMI greater than 40
```

--- .class #id 

## How is it calculated?

There is a formula for calculating the BMI measure. The formula is the following:

BMI = weight (kg) / height (meter)2

Example :


```r
    weight = 78
    height = 1.8
    BMI <- weight/height^2
    BMI
```

```
## [1] 24.07407
```

--- .class #id 

## Classification

The function to classify the BMI is the following:


```r
    category_func <- function(weight,height) {
        BMI_value <- weight/(height^2)
        if (BMI_value < 14.9) print("Starvation")
        else if (BMI_value < 18.4) print("Underweight")
        else if (BMI_value < 22.9) print("Normal")
        else if (BMI_value < 22.7) print("Overweight")
        else if (BMI_value < 40) print("Obese")
        else print("Morbidly Obese")
    }
```

Example :

```r
    category_func(78,1.8)
```

```
## [1] "Obese"
```

--- .class #id 

## Conclusion

While BMI is fast and easy to calculate, it should not be the be all end all of determining whether or not someone is at a healthy weight.

However, if someone has a low BMI or a really high BMI, that should signal the potential for health problems and that person should see their doctor to discuss this.
