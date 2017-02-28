
---
title: "Functional Programming"
author: "Dinesh Poddaturi"
topic: "06"
layout: post
root: ../../../
---
Everything in R can be written in the form of a function. R provides a flexible platform to create and manipulate functions. As Hadley mentioned in the book, we can store functions in lists, assign them to variables, pass a function as an argument to another function, create a function within a function and return a function as a result of another function.

For the given example, we could use functional programming in different ways. When I began programming in R, I used to call functions in each line like the following 


{% highlight r %}
x <- 1:10
sum <- sum(x,na.rm=TRUE)
mean <- mean(x,na.rm=TRUE)
median <- median(x,na.rm=TRUE)
{% endhighlight %}
The above code gives proper results without any errors. If we want to use these functions in multiple places, we need to type/copy the same lines wherever we need them, which results in duplicate code which will eventually lead to bugs in the code. We could make these functions general and call them inside a function

{% highlight r %}
x <- 1:10
someStatistics <- function(x){
  sum <- sum(x,na.rm=TRUE)
  mean <- mean(x,na.rm=TRUE)
  median <- median(x,na.rm=TRUE)
  return(c(sum,mean,median))
}
someStatistics(x)
{% endhighlight %}



{% highlight text %}
## [1] 55.0  5.5  5.5
{% endhighlight %}
We can still make the above function more sophisticated by using a nice property of R ; "Storing functions in a list" and using lapply function.
The below code demonstrates how we can store functions in a list and call it whenever we need

{% highlight r %}
x <- 1:10
someStatistics <- list(
  sum = function(x) sum(x, na.rm = TRUE),
  mean = function(x) mean(x, na.rm = TRUE),
  median = function(x) median(x, na.rm = TRUE)
)
lapply(someStatistics, function(f) f(x))
{% endhighlight %}



{% highlight text %}
## $sum
## [1] 55
## 
## $mean
## [1] 5.5
## 
## $median
## [1] 5.5
{% endhighlight %}
The above code has some duplicates (na.rm=TRUE), we can take them out and pass as an argument inside lapply like below


{% highlight r %}
x <- 1:10
someStatistics <- list(
  sum =function(x,...)sum(x,...),
  mean = function(x,...)mean(x,...),
  median = function(x,...)median(x,...)
)
lapply(someStatistics, function(f) f(x, na.rm=TRUE))
{% endhighlight %}



{% highlight text %}
## $sum
## [1] 55
## 
## $mean
## [1] 5.5
## 
## $median
## [1] 5.5
{% endhighlight %}
Finally, we can modify the above function by removing redundent code and make it more general as following


{% highlight r %}
x <- 1:10
someStatistics <- list(
  sum =sum,
  mean = mean,
  median = median
)
lapply(someStatistics, function(f) f(x,na.rm=TRUE))
{% endhighlight %}



{% highlight text %}
## Error in FUN(X[[i]], ...): could not find function "f"
{% endhighlight %}
