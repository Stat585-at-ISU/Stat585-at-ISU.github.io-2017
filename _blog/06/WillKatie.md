---
title: "DRY - Don't Repeat Yourself"
author: "Katie Will"
topic: "06"
layout: post
root: ../../../
---


```
x <- 1:10
funs <- list(
  sum = sum,
  mean = mean,
  median = median
)
lapply(funs, function(f) f(x, na.rm=TRUE))
```


I know that code I have written in the past is not the most efficient. This is simply due to the fact that functional programming is something that I struggle with. It is not that I don't like or don't understand how to write functions. It's that I always think it will take me so much more time to write a function than to copy, paste, and alter the code I already have. Not too surprisingly, I am finding out that this is not the case in most instances. Simply speaking, functional programming can make coding easier. It tends to get really tedious "command c-ing"" and "command p-ing" each line of code, to then go through to alter just a few names or numbers. Not only is it annoying, but it is very time consuming and not worth the risk of making a frustrating mistake. Writing a function that can perform a task/function saves you so much time and effort. It also significantly decreases the length of the code, making it easier to read. With the code above, it may not look like it is fewer lines than if you were to do the same think with no function. However, if *x* was a data frame with multiple variables, we could easily apply *funs* to the data frame with one line of code and get the sum, mean, and median of each column. And lastly, functional programming makes it easy to re-use code from project to project. If I was working with new data, say *y*, I could just copy the function and change the input to *y* instead of *x* making the function so versatile and efficient.  


