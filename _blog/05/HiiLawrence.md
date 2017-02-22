---
title: "The S3 class system"
author: "Lawrence Hii"
topic: "05"
layout: post
root: ../../../
---


## How S3 class interacts with functions/methods/approaches with class or classes?

In R programming, most of the functions or packages we used are built based on S3 objects or S4 objects. These functions are build based on a couple things like classes, objects, methods, generic functions and other arguments. In general, generic function is like traffic officer. It checks on the class that was called in the function and see if it can match with the methods in the function. I will give couple example.

Example1
`x <- rnorm(10)`
`mean(x)`

Here mean is the generic function. And the class for the x is `numeric` but there is no mean method in the `rnorm` or the objects. Also, looking at mean, it can not take on all classes. There are `mean.default`, `mean.Date`, `mean.difftime`, `mean.difftime`, `mean.POSIXct` and `mean.POSIXlt`. However, if you use `mean.default(x)` will not work. `mean` is the generic function.

Example2
`x<- data.frame(x= runif(10,0,1), y=rnorm(10))`
`apply(x,2,mean)`

Here `data.frame` is the class and each column is objects. When we use `apply` here, we are calling generic functon `mean` and check if the class and methods match each other on each column so it can dispatch an appropriate methods or `mean` which is what we are looking here.

Example3
`x<- data.frame(x= runif(10,0,1), y=rnorm(10))`
`f <- function (a){for (i in 1:length(10){if (a[i]<0.5){a[i]=10} else {a[i] = 5}};print(a)}`
`f(x)`

Here `x` class is `data.frame`. However, the function `f` is not working here because, the `f` functions are looking for a vector or data frame with one column class. We will get an error here.

It is just fasinating me that for most packages there are a couple generic functions that almost always exist in a package like `summary`, `plot`, `print` etc. 
