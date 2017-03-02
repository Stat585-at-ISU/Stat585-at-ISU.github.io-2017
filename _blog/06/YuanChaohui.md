---
title: "Functional Programming"
author: "Chaohui Yuan"
topic: "06"
layout: post
root: ../../../
---

Put the related functions together in a list would make it analysis easier. First of all, no specific function name is needed if using `lapply` especially it is not necessary to define a function just use once. More specifically, use an anonymous function when it’s not worth the effort to give it a name. 


Also suppose x is data frame or matrix rather than a vector in this example,
if we want to calculate the summary statistics, say sum, mean and median for each 
column (or row), it would be very painfull to write each summary statistics for each column (or row) seperately and repeat this process one by one (or even just simple copy-paste work). It also makes the R 
code looks like arguly, not neat at all. By `lapply`, putting related function together, and it will reduce such repeating work as much as possible.  


What's more, in the above example, it takes the identical argument in each function 
out and put it as the extra argument when we use lapply. Again, this also
reduces the duplicates typing and makes the code more readable and more tidy and clean.


{% highlight r %}
x <- 1:100
funs <- list(
  sum = sum,
  mean = mean,
  median = median
)
system.time(lapply(funs, function(f) f(x, na.rm=TRUE)))
{% endhighlight %}



{% highlight text %}
## Error in FUN(X[[i]], ...): could not find function "f"
{% endhighlight %}



{% highlight text %}
## Timing stopped at: 0.009 0.007 0.024
{% endhighlight %}



{% highlight r %}
lapply(funs, function(f) system.time(f(x)))
{% endhighlight %}



{% highlight text %}
## Error in system.time(f(x)): could not find function "f"
{% endhighlight %}



{% highlight text %}
## Timing stopped at: 0.001 0 0
{% endhighlight %}


