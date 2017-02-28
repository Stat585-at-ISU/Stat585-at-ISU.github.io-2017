---
title: "Functional Programming"
author: "Yue Zhang"
topic: "06"
layout: post
root: ../../../
---

R is a functional programming (FP) language. We can do anything with functions that we can do with vectors: we can assign them to variables, store them in lists and pass them as arguments to other functions. Especially for the “lapply” function, before I only knew that I can pass a dataframe (a list essentially) to one function specified. However, Hadley’s tutorial reminds me that the reverse is also possible, I can pass a list of functions to my data. Sometimes this will greatly improve the readability and maintenance of the R code. 

The following R code is used to calculate the statistics of a vector.


{% highlight r %}
x <- 1:10
funs <- list(
  sum = sum,
  mean = mean,
  median = median
)
lapply(funs, function(f) f(x, na.rm=TRUE))
{% endhighlight %}



{% highlight text %}
## Error in FUN(X[[i]], ...): could not find function "f"
{% endhighlight %}

Unlike we have many vectors in a dataframe as inputs for one function, here we have a vector as input for several functions. Following the "passing dataframe to one function" scheme, of course it can be programmed using three “lapply” statements. However, in this way, it doesn’t improve the coding compared to writing three individual  statements for sum, mean and median.

But, we can do it in the reverse way, by passing the three functions to the data vector. This will result in just one single “lapply” function and therefore greatly simplify the code. As a result, coding in this way will significantly reduce the chance to include bugs in the code. Moreover, on one hand, it's convenient to set/change the options such as if missing values will be considered in the statistics. On the other hand, if we need to add or drop any function in the summary of statistics, we just need to modify the list of the functions, so it simplifies the maintenance of the code too.

