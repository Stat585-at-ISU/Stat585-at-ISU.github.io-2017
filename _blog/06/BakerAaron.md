---
title: "Functional Programming"
author: "Aaron Baker"
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

Functional programming has the same end goal as such packages as purrr and dplyr-to create functions in such a way that they are easy to use and can be built component by component in a methodical and clear, concise, way. The more actual characters one has to type, the more mistake prone that code is, and the harder it is to find that code.

I will never forget the 10000+ line code behemoth I wrote for an internship. It works. Forbid anyond try to debug it! Some simple uses of the principal of functional programming could have easily save 1000 or more lines of that code. 

In the above function, we see that we have combined some very common functions used to summarize data into one function that can be used multiple times over, together, all at once. This is nice because we don't have to call these functions again and again and again. If there IS a problem with the code, then it will be caught quickly and fixed quickly because it will exist within everything we use that function to work with.

Further, using lapply allows us to pass along an extra argument all at once to all of the functions, allowing more succinct and easier to debug coding once again. 

