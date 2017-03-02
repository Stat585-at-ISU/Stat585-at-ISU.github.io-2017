---
title: "Functional Programming"
author: "Xiangzhen Li"
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
Several ideas of functional programming are discussed in this chapter.

Repeating applying function on a dataset is really common when we analyze data. The more we copy-paste, there is more chance to make mistakes. Also, if the value we are dealing with changes, we have to change them one by one again. Functional programming could help to reduce duplication.

Another useful idea is to store the function in lists. It makes it easier to work with groups of related functions. In the above examples, function **mean**, **sum**, **median** are stored as a list.

Anonymous function will be created if the function does not have a name. In the example above, **function(f) f(x, na.rm=TRUE)** is used as anonymous function. 

To call each function in the list above, it use **lapply()**. For above example, **function(f) f(x, na.rm=TRUE)** is applied to every function which is stored in the list.
