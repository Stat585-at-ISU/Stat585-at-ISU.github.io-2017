---
title: "Functional Programming"
author: "Ben Buzzee"
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


Concepts from functional programming can make code both more succinct and less prone to error.
In the example given, we significantly reduce the amount of repetition and room for human error by
creating a list of functions and then using lapply in combination with the simple anonymous function f. 
The argument of interest is written in just one location, allowing us to easily change or edit just one
argument which will have cascading effect on all the subfunctions of interest. The functional oriented design
also makes understanding the code easier. Any third party that was not involved in writing the code can
simply examine the arguments of lapply and immediately see that we want to pass the arguments of f to all 
the elements of funs. This is in contrast to having many lines of repeated functions and arguments that would
needed to be manually checked for consistency.
