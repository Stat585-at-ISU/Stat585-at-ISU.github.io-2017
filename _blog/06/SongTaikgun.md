---
title: "Functional Programming"
author: "Taikgun Song"
topic: "06"
layout: post
root: ../../../
---


## Background:

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

Functional programming makes coding easier first because it reduces duplicating codes and redundant processes. For example,
```
x<-1:10
sum = sum(x)
mean = mean(x)
median = median(x)
```
code chunk as above will generate the same output, however, (x) argument is not repeated.  The above codes are fairly short, but functional programming could have time with complicated codes. Also, reducing duplication also means reducing the chance of making mistakes due to copy/pasting or writing similar codes multiple times.  Thus, functional code will help in terms of debugging as well. Moreover, functional program not only because the code chunk looks nice, but because the output is in neat list format as well.

