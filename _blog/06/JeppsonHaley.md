---
title: "Functional Programming"
author: "Haley Jeppson"
topic: "06"
layout: post
root: ../../../
---


***



The underlying theme for [Functional Programming](http://adv-r.had.co.nz/Functional-programming.html) is similar to the underlying themes of a couple past blog posts. That is, when tackling a large problem, it is advantageous to attack it in smaller, more manageable pieces. In other words, we can use simple functions as the building blocks for programming a complex structure. Doing so benefits us on many fronts - it *reduces* the room for human error by reducing code duplication and *increases* the versatility of the programming while making the code more compact.

Duplicating any action creates an opportunity for human error and makes the code more rigid, difficult to debug, and difficult to adapt to new data. By utilizing functional programming, we can reduce duplication and are therefore better suited to adopt the DRY (Don't Repeat Yourself) principle. Take the following code, for example.

```
x <- 1:10
funs <- list(
  sum = sum,
  mean = mean,
  median = median
)
lapply(funs, function(f) f(x, na.rm=TRUE))
```

In this code, we have a list of functions that can all be called simultaneously using `lapply()` and an anonymous function, another useful functional programming tool. Working with a list of functions allows you to do the work only once and makes it easier to work with groups of related functions. In addition, each of the three functions can still be called individually.

By reducing the number of times you have to write out a function, or write out the function's arguments, you are working to prevent mistakes that can occur while doing copy-and-paste while simultaneously writing stronger, more versatile code. 

