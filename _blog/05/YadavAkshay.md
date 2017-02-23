---
title: "The S3 class system"
author: "Akshay Yadav"
topic: "05"
layout: post
root: ../../../
---

####Explain how a user can define a new S3 class with objects and methods at a small example of your choice

Classes are the central to implementation of Object Oriented Programming. These are kind of blue-prints for holding and processing particular types of data.

We will look at S3 class type object-orientation in R. We will create a generic class for holding information on different types of vehicles and define methods for extracting this information.  

First, we will define some instances for the class **vehicle**. This is a little different from the classic object-oriented programming languages like JAVA where we first define the class and then instantiate it


{% highlight r %}
car<-list(wheels=4, steering=TRUE, capacity=4)
bike<-list(wheels=2, steering=FALSE, capacity=2)
trailer<-list(wheels=6, steering=TRUE, capacity=6)
{% endhighlight %}

Assigning the class attribute **vehicle** to all the instances

{% highlight r %}
class(car)<-append(class(car),"vehicle")
class(bike)<-append(class(bike),"vehicle")
class(trailer)<-append(class(trailer),"vehicle")

class(car)
{% endhighlight %}



{% highlight text %}
## [1] "list"    "vehicle"
{% endhighlight %}



{% highlight r %}
class(bike)
{% endhighlight %}



{% highlight text %}
## [1] "list"    "vehicle"
{% endhighlight %}



{% highlight r %}
class(trailer)
{% endhighlight %}



{% highlight text %}
## [1] "list"    "vehicle"
{% endhighlight %}

We will define a method for getting the **number of wheels** for instances of class **vehicle**


{% highlight r %}
getNwheels <- function(x)
{
     UseMethod("getNwheels",x)
}
 getNwheels.vehicle <- function(x)
 {
    return(x$wheels)
 }
{% endhighlight %}

Calling the **vehicle** class function *getNwheels()*

{% highlight r %}
getNwheels(car)
{% endhighlight %}



{% highlight text %}
## [1] 4
{% endhighlight %}



{% highlight r %}
getNwheels(bike)
{% endhighlight %}



{% highlight text %}
## [1] 2
{% endhighlight %}



{% highlight r %}
getNwheels(trailer)
{% endhighlight %}



{% highlight text %}
## [1] 6
{% endhighlight %}


