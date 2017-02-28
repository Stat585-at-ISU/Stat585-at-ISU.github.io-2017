---
title: "Building Blocks in R: Functional Programming"
author: "Lawrence Hii"
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

Just to reiterate again, gunctional programming does make code easier to write and maintain. I would say functional programming is the building blocks for R programming. By looking at the code above, functional programming makes the code easier by remove the hassle of copy and paste action. My programming mind is that the more you "touch" on the code, the more chances of having mistakes or errors. By reducing the work, you can spend less time in debugging.

Also, functional programming makes the code easy to maintain due to the flexibility or versatility of the programming. As you can see, from the code above, you can create a function or `funs` here. This function not only acts as a function but you can input some preexisting function like `mean`, `sum` or `median` into the function. Basically, it's like nesting, but a cleaner way in functional programming. One thing that I do really like about this is that you do not have to rewrite the whole code if you want to update your code let say instead of `median`, `max` and `min`.
