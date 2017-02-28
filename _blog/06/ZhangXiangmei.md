---
title: "Functional Programming"
author: "Xiangmei Zhang"
topic: "06"
layout: post
root: ../../../
---




Regard the code below and describe in what way(s) the idea of functional programming makes code easier to write and maintain.

```
x <- 1:10
funs <- list(
  sum = sum,
  mean = mean,
  median = median
)
lapply(funs, function(f) f(x, na.rm=TRUE))
```

The code above uses the "divide and conquer" idea of fucntional programming. With the motivation to clean and summarise the data the code uses a functional "lapply()" which takes a function as an argument to remove NAs, and apply this to a list of summary information including "sum", "mean" and "median", this makes the program more compact and easy to update. It can ensure that all data can be uniformly treated and won't bring in any mistakes. By using closures and functionals we can avoid copy and paste for the same argument in a function and build an efficient functional program by removing redundancy and duplications.
