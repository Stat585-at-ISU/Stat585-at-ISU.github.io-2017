---
title: "Functional Programming"
author: "Amy Crawford"
topic: "06"
layout: post
root: ../../../
---


### Regard the code below and describe in what way(s) the idea of functional programming makes code easier to write and maintain.

```
x <- 1:10
funs <- list(
  sum = sum,
  mean = mean,
  median = median
)
lapply(funs, function(f) f(x, na.rm=TRUE))
```

The idea of functional programming makes code easier to write and maintain because it is a non-repetitive way to write code. With regard to the code above, we see that instead of repeating the functions `sum`, `mean`, and `median` over and over again for any different `x` that we might want to find summary statistics for, we can write this slick function and use lapply. Thus, we don't have to duplicate our summary statistic functions everytime we would like to use them, and our code is much less fragile. Storing the functions as lists further strengthens our code because we only need to type the `na.rm` statement once, and we are able to handle this group of related functions more easily while efficiently removing `NA`s. We have written a "simple function that can be understood in isolation and then composed". This is very powerful and makes it easy for us to adapt to changing requirements.
