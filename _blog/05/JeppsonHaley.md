---
title: "The S3 class system"
author: "Haley Jeppson"
topic: "05"
layout: post
root: ../../../
---


## Defining an S3 class with objects and methods

A **class** is an attribute associated with an object and an **S3 object** is an R object with an additional 'class' attribute

One way to set the class attribute is to use the `class` command. Multiple classes can be declared with a vector decribing the the classes from most to least specific. For example, we can create a object called `obj` and assign it the class `'example'`.

Create object:

{% highlight r %}
obj <- list()
{% endhighlight %}



{% highlight r %}
# object is a list
class(obj)
{% endhighlight %}



{% highlight text %}
## [1] "list"
{% endhighlight %}

Assign class:

{% highlight r %}
# but we can assign the class 'example'
class(obj) <- 'example'

# object is now of class 'example'
class(obj)
{% endhighlight %}



{% highlight text %}
## [1] "example"
{% endhighlight %}

Alternatively, a new S3 class can be *created* with a constructor function. The constructor function below will create a new object of a class defined by the name of the object. 


{% highlight r %}
color <- function(x)  {
  object <- list(name = x)
  class(object) <- x
  return (object)
}
{% endhighlight %}

### Create an S3 Method

A **method** can then be defined for the class using the `UseMethod()` command. In doing this, we will define a set of functions and when the method is called, the function that is used will be determined by the class of the object that the function in called with. 

The first step is to define a generic function,

{% highlight r %}
# create the generic method
hue <- function (x) {
  if(is.null(attr(x, "class"))){
    print("no color group defined")
  }
  else  UseMethod("hue", x)
}
{% endhighlight %}


After creating the S3 generic, we can create the S3 methods which will be of the form `generic.class()`. These will be functions that will be used for specific classes.



{% highlight r %}
# create the S3 methods for specific classes

hue.black <- function(x)  {
  # Only if class of an S3 object is a vector
  NextMethod()
}

hue.red<- function(x)  {
  # First argument is an object of class "red"
  print(x$name)
  print("warm hue")
}

hue.blue <- function(x)  {
  # First argument is an object of class "blue"
  print(x$name)
  print("cool hue")
}
{% endhighlight %}


We can now use our class constructor function to create objects and then apply our newly contructed S3 method.


{% highlight r %}
# Create object of class type 'red' and 'blue'
a <- color(c("red","blue"))
class(a)
{% endhighlight %}



{% highlight text %}
## [1] "red"  "blue"
{% endhighlight %}



{% highlight r %}
hue(a)
{% endhighlight %}



{% highlight text %}
## [1] "red"  "blue"
## [1] "warm hue"
{% endhighlight %}


{% highlight r %}
# Create object of class type 'black' and 'blue'
b <- color(c("black","blue"))
hue(b)
{% endhighlight %}



{% highlight text %}
## [1] "black" "blue" 
## [1] "cool hue"
{% endhighlight %}


{% highlight r %}
# the generic method
hue("purple")
{% endhighlight %}



{% highlight text %}
## [1] "no color group defined"
{% endhighlight %}



