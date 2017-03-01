---
title: "Functional Programming"
author: "Chelsey Legacy"
topic: "06"
layout: post
root: ../../../
---

This code chunk is a great way to show how functional programming can make code more concise and less prone to errors.  Functional programming makes it possible to avoid repeating code. When we avoid repeating code we can make our code shorter and avoid making errors in the code.  For this specific code chunk we could instead write:


{% highlight r %}
x <- 1:10
sum(x, na.rm=TRUE)
{% endhighlight %}



{% highlight text %}
## [1] 55
{% endhighlight %}



{% highlight r %}
mean(x, na.rm=TRUE)
{% endhighlight %}



{% highlight text %}
## [1] 5.5
{% endhighlight %}



{% highlight r %}
median(x, na.rm=TRUE)
{% endhighlight %}



{% highlight text %}
## [1] 5.5
{% endhighlight %}
This code would get us the same summary information, but we can see that we repeated the exact same argument for each desired summary statistics we wanted. In order to avoid this, we can use functional programming. In addition to eliminating the repeated arguments, we can also get the desired information returned in a single vector. We can create a list of functions that we would like to pass our arguments to, and then use lapply() to pass those arguments to that list of functions. If you decided that you wanted to add more summary statistics that take the same arguments, it is easy to just add the functions to the list and then they too would appear in the output from lapply(). I do not make use of lapply() as much as I should, but I hope to do so after reading this article and learning more about how useful it is.
