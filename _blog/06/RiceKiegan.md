---
title: "Decreasing the chances of messing up while coding"
author: "Kiegan Rice"
topic: "06"
layout: post
root: ../../../
---

## Regard the code below and describe in what way(s) the idea of functional programming makes code easier to write and maintain.

```
x <- 1:10
funs <- list(
  sum = sum,
  mean = mean,
  median = median
)
lapply(funs, function(f) f(x, na.rm=TRUE))
```

The idea of functional programming makes code easier to write and maintain by creating smaller pieces and combining those small pieces into a larger, more powerful action. In the example code above, it allows us to apply three functions that help us summarize our data at once, instead of having to call three functions separately. It also allows us to add in the `na.rm = TRUE` statement to each when we actually call the function, and know that it will call exactly that, instead of having to specify that statement for each function. As the chapter from Advanced R Programming mentions quite a bit, it is very easy to make mistakes using copy-and-paste or applying functions to an object separately when you could much more easily apply them all at the same time. The ease of writing comes from the fact that you don't have to call a function for each specific event you want to apply it to -- you can instead have a function that does what you want it to, and apply it to all scenarios at once. The ease of maintenance comes from the fact that you are using sets of smaller functions that allow you to go back and assess whether each small piece is doing what you desire, and fix a small piece rather than having to hunt through one huge function or a bunch of applications of a function to find where you messed up. Essentially, functional programming will decrease the chances of screwing up when coding (especially when you get into complicated functions), as well as make it easier to go back and fix a mistake if you do make one. 
