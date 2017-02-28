---
title: "Functional Programming: Blog 6"
author: "Ryan Morgan"
topic: "06"
layout: post
root: ../../../
---


## Background:

Read through the chapter on [Functional Programming](http://adv-r.had.co.nz/Functional-programming.html) of Hadley Wickham's book on *Advanced R Programming*.

Write a blog post discussing the question:

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

The idea of functional programming is definitely something I should try and implement when writing code. The big idea I took away from the “Functional Programming” article is trying to use functional programming to follow the “Do not repeat yourself” principle. While reading through this article, I thought of how messy my code can look at times when I copy and paste a command several times. Using functional programming provides several advantages over simply copying and pasting parts of your code over and over again. If you use functional programming, your code will be much more compact, making it easier to change if edits need to be made. It also makes it easier to avoid making mistakes, and especially makes it easier to go back and fix mistakes. I can think of several times when I made a mistake in a piece of code I copied and pasted several times, and I had to go back and make one tiny change in every place I pasted the code. 

We see the usefulness of functional programming in the above example. Instead of using sum(x, na.rm=TRUE), mean(x, na.rm=TRUE), and median(x, na.rm=TRUE), we can place the three functions in a list of functions, and then input our list x only once by using lapply. 
It may not seem this example is any easier than calling the sum(), mean(), and median() function separately, but the usefulness of functional programming can be seen if we had several different lists. Suppose we had y <- 10:20 and z <- 1:20. Instead of running the sum, mean, and median function separately for each list, you could simply use lapply on the three lists.


