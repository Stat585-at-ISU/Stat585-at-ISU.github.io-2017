---
title: "Functional Programming"
author: "Joe Papio"
topic: "06"
layout: post
root: ../../../
---


## Regard the code below and describe in what way(s) the idea of functional programming makes code easier to write and maintain.


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
Functional programming makes code easier to write and maintain because it reduces the potential for typos and other common, easy-to-make human errors that occur in repetative tasks. It confers a further benefit of reducing redundancy, which makes implementing changes easier as well, since they need to be made in fewer places.

There's an initial draw back in that you need to maybe spend more time on the front end thinking about what it is you want to do and how you want to accompolish that. But this ends up ultimately being a benefit, as thinking through something like programming prior to starting the task is rarely a bad thing; when things go wrong in programming, the reason is almost never "I planned too much".

In the code above, a *lapply* takes *funs* (the list of functions which are each similar in that they take as their argument a set of numbers and return a single value), and applies each element to a vector of numbers. Despite *sum*, *mean*, and *median* being functions that already exist in base  **R**, this approach is more straightforward and ultimately more convenient than applying each function to *x* individually: 
* the list of numbers, as well as options, such as removal of *NAs*, can be specified only a single time, rather than once for each summary statistic
* results can easily be stored in a single list object whose elements can then be called individually or all at once
* additional summary statistic functions, such as standard deviation, can be easily added to the *funs* list with **sd = sd**

And in addition, if it were necessary to run this set of summary statistics frequently, it would be straight forward to name the function so it could be applied repetatively, and as mentioned at the onset, while minimizing the number of necessary changes and thus, the opportunity for errors:


{% highlight r %}
thing <- function(x){
funs <- list(sum = sum,
             mean = mean,
             median = median,
             sd = sd
)
  lapply(funs, function(f) f(x, na.rm=TRUE))
}

x <- 1:10
thing(x)
{% endhighlight %}



{% highlight text %}
## Error in FUN(X[[i]], ...): could not find function "f"
{% endhighlight %}
