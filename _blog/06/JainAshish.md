---
title: "Functional Programming"
author: "Ashish Jain"
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

**R** is a perfect example functional programming language. Not only it provides flexibility to write code in modules/functions but also provides many tools to operate and play with functions similar to a vector including storing them in lists, assigning them to a variable, creating functions insides functions. Having some working experience in the software industry has helped me adapt to functional programming. It helps in eliminating code duplication and redundancy. This also helps in preventing any mistakes while doing copy-and-paste. The code above is a very good example of functional programming. The function prints the sum, mean, and median of a numeric vector. There are many different approaches one can use to do the same thing. For example, one can simply call the sum, mean, and median base functions in R and apply it on to the list.

```
x <- 1:10
y <- 20:30
sum(x)
median(x)
mean(x)

sum(y)
median(y)
mean(y)
```

As you can see that this will result in code duplication which in turn leads to some mistake if we have to do this for a large set of vectors. We can also use a second approach in which we can make a function combining all the three methods and then calling it. 
```
x <- 1:10
funs1 <- function(x){
  c(sum(x, na.rm = TRUE),
  mean(x, na.rm = TRUE),
  median(x, na.rm = TRUE))
}
funs1(x)
```

There is also some redundancy in this code, for example, the repetition of x and na.rm which can become a cause of a bug. So, in order to make the code free from duplication, we can use the concept of functional programming i.e. storing the functions in a list as done in the given code.
