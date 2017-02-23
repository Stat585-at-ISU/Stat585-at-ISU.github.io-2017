
---
title: "The S3 class system"
author: "Dinesh Poddaturi"
topic: "05"
layout: post
root: ../../../
---

Everything we use in R is treated as objects. In general, an object is an instant of a class and class has methods that perform certain functionality (by default most of the classes has constructors).

The most commonly used objects in R are S3 objects. An S3 object is an R object with a "class" attribute. In S3, the methods belongs to generic functions not objects or classes. The process of calling a method by using generic functions is called Method Dispatching.

First we create a class (with or without a constructor) and then we create an object of that class. Now we can use this object to call the generic methods that we write for the class.

Here is an example that illustrates the process of creating S3 objects, methods and classes.


{% highlight r %}
##Creating a class with constructor, in this constructor we create an S3 object and return that object
department <- function(name)  {
  s3object <- list(major= name)
  #here we create S3 object
  class(s3object) <- name
  return (s3object)
}
{% endhighlight %}

{% highlight r %}
##writing methods that will print the department's building name according to the persons major
printDepartment <- function(major){
  #the following will call the appropriate method
  UseMethod("printDepartment",major)
}

printDepartment.Mathematics <- function(x){
  print(toupper(x$major))
  print("You are in Carver Hall")
}

printDepartment.Statistics <- function(x){
  print(toupper(x$major))
  print("You are in Snedecor Hall")
}

printDepartment.AnimalScience <- function(x){
  print(toupper(x$major))
  print("You are in Kildee Hall")
}
{% endhighlight %}


{% highlight r %}
#Here we created an S3 object 
printDepartmentBuilding <- department("Mathematics")
#Method dispatching
printDepartment(printDepartmentBuilding)
{% endhighlight %}



{% highlight text %}
## [1] "MATHEMATICS"
## [1] "You are in Carver Hall"
{% endhighlight %}



{% highlight r %}
# "MATHEMATICS"
# "You are in Carver Hall"
{% endhighlight %}

{% highlight r %}
printDepartmentBuilding <- department("Statistics")
printDepartment(printDepartmentBuilding)
{% endhighlight %}



{% highlight text %}
## [1] "STATISTICS"
## [1] "You are in Snedecor Hall"
{% endhighlight %}



{% highlight r %}
# "STATISTICS"
# "You are in Snedecor Hall"
{% endhighlight %}

{% highlight r %}
printDepartmentBuilding <- department("AnimalScience")
printDepartment(printDepartmentBuilding)
{% endhighlight %}



{% highlight text %}
## [1] "ANIMALSCIENCE"
## [1] "You are in Kildee Hall"
{% endhighlight %}



{% highlight r %}
# "ANIMALSCIENCE"
# "You are in Kildee Hall"
{% endhighlight %}

