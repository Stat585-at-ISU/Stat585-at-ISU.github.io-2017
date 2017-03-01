---
title: "Functional Programming"
author: "Gaurav Kandoi"
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

Whenever I'm writing a code to get some analysis done, I'm always thinking about getting the *task done*. Although, I'm able to complete the task in hand, but this then creates problems for the future me. When I revisit the code in few months, I keep guessing about what I did and how I did? *Functional Programming* is something that I should start incorporating more. This will help me make my code much more readable and reusable. Because I'll be defining functions and lists which can then be called to perform multiple computations at once, this will also allow me to make my code compact. I usually copy paste a chunk of code and change the dataframes and perform computation. This unnecessarily copy-pasting of the code makes it much more error prone and harder to debug.

Having a compact, readable and reusable code will not only make my life easier, but also of other people who wish to use my code and perform similar analysis. When people are able to understand your code better, this will also allow for better collaboration. The example above is only a very basic one and we may not see the benefits of functional programming. But, consider a project where you are working with multiple data frames, and would like to perform the same analysis on all of these. Isn't it frustrating to simply copy and paste the entire analysis code for each data frame separately? Wouldn't it be much easier if we can combine all the analysis steps in a list/function and then just call that function for all data frames. This will also allow us the flexibility to define exceptions like `na.rm = TRUE` to make our code more efficient.
