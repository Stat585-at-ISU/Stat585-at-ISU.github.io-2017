---
title: "The S3 class system"
author: "Xiangmei Zhang"
topic: "05"
layout: post
root: ../../../
---


Write a blog post addressing **one** of these topics:

- At an S3 class of your choice discuss a set of functions/methods/approaches that allow you to interact with the class. 
- Explain how a user can define a new S3 class with objects and methods at a small example of your choice. 

For a given R object such as a vector, a matrix, a list or anything else we can change certain class type by simply attaching the ‘class’ attribute. S3 generics are methods belong to function, we can use a call "UseMethod()" to creat a method. Here is a small example.

{% highlight r %}
o <- c("A","B","C","D","E","F") # a vector of characters
{% endhighlight %}

we can change object belongs to class type "grade" using the following codes:

{% highlight r %}
class(o) <- c("grade")  # or use next line
attr(o, "class") <- "grade"
{% endhighlight %}
Now we can build a constructor and a simple method for "grade" class:

{% highlight r %}
# Constructor function for "grade" class
grade <- function(x){
  structure(x,class="grade")
}
# a simple method for "grade" class
pass <- function(x) UseMethod("pass",x)
pass.grade <- function(x){
  x.pass=x[x<="C"]
  x.nopass=x[x>"C"]
  cat("Grades pass the exam: ",x.pass,"\n")
  cat("Grades fail the exam: ",x.nopass)
  
}
{% endhighlight %}
Test the "grade" constructor and the new method":

{% highlight r %}
# create a new object of class "grade"
new <- grade(c("C","D","G","A"))
methods(class="grade") # check methods for class "grade"
{% endhighlight %}



{% highlight text %}
## [1] pass
## see '?methods' for accessing help and source code
{% endhighlight %}



{% highlight r %}
pass(o)
{% endhighlight %}



{% highlight text %}
## Grades pass the exam:  A B C 
## Grades fail the exam:  D E F
{% endhighlight %}



{% highlight r %}
pass(new)
{% endhighlight %}



{% highlight text %}
## Grades pass the exam:  C A 
## Grades fail the exam:  D G
{% endhighlight %}



{% highlight r %}
ftype(pass)
{% endhighlight %}



{% highlight text %}
## Error in eval(expr, envir, enclos): could not find function "ftype"
{% endhighlight %}

