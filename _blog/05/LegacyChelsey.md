---
title: "The S3 class system"
author: "Chelsey Legacy"
topic: "05"
layout: post
root: ../../../
---
Below is the code to explain how a user can define a new S3 class with objects and methods as a small example.  Say we have a race run by 5 men and we record the outcome in a list.  We can then append the class of that list to make it of class "Athlete".

{% highlight r %}
#Create an object

runners <- list(first = "Bob", second = "Steve", third = "Chris", fourth = "Matt", fifth = "Jim")
class(runners)
{% endhighlight %}



{% highlight text %}
## [1] "list"
{% endhighlight %}



{% highlight r %}
#Assign the object groceries to class "food"
class(runners) <- append(class(runners),"Athlete")
class(runners)
{% endhighlight %}



{% highlight text %}
## [1] "list"    "Athlete"
{% endhighlight %}

Next, we can define the method for this mini example. Suppose we want to know who the top three runners are for the men that ran this race. We can define a new method topThree() to give us that information from the vector of runners.

{% highlight r %}
topThree <- function(x)
 {
     UseMethod("topThree",x)
 }

 topThree <- function(x)
 {
    return(c(x$first, x$second, x$third))
 }

 topThree(runners)
{% endhighlight %}



{% highlight text %}
## [1] "Bob"   "Steve" "Chris"
{% endhighlight %}
