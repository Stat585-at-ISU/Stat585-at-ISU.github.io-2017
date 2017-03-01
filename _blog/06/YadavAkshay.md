---
title: "Functional Programming"
author: "Akshay Yadav"
topic: "06"
layout: post
root: ../../../
---


Functional programming allows functions to be used objects that can be assigned to variables, stored in a list with multiple functions, passed to other functions as arguments and even returned from other functions, just like objects in other datatypes (vectors and dataframes). This property of funtions allows the user to create composite functions which can contain already existing functions.

With reference to example given below, the in-built functions *sum()*, *mean()* and *median()* are applied on the given vector without explicitly passing the vector to each function individually. This is achieved by combining the functions (function names) in a list *funs* and then using *lapply()* to apply each function in the list on the vector *x* through a another function *function(f)*.


```
x <- 1:10
funs <- list(
  sum = sum,
  mean = mean,
  median = median
)
lapply(funs, function(f) f(x, na.rm=TRUE))
```


