---
title: "Functional Programming"
author: "Haiyang Zhang"
topic: "06"
layout: post
root: ../../../
---


##Regard the code below and describe in what way(s) the idea of functional programming makes code easier to write and maintain.

```
x <- 1:10
funs <- list(
  sum = sum,
  mean = mean,
  median = median
)
lapply(funs, function(f) f(x, na.rm=TRUE))
```
Since R is a functional language, where it maps to mathematical functions rather than objects as in imperative languages, it is trivial to implement higher order functions such as lapply, which is able to takes other functions as arguments, to take collection of data (in this case, funs) and applying the input function (in this case f) to every element of the collection. This eliminate many repeated copy and pastes, and not only make the code cleaner/more efficient, it also reduces human error. Since functional languages typically operate on immutable data, and output value of higher order functions such as lapply depends only on the function(f), this makes it much easier to understand and predict the behavior of a program. As in the example, all you really need to think about is the type of data you have as your input, the function you want to apply to each element, and the data structure you want as the output. I have personally heard the argument that functional languages makes it harder for humans to read than say Java or C++, because it maps to mathematical functions so the sytax of functional language isn’t apparent to everyday programmers but for mathematically intensive applications functional languages clearly has an advantage. 


