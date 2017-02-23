---
title: "The S3 class system"
author: "Haiyang Zhang"
topic: "05"
layout: post
root: ../../../
---


## My Example: define a new S3 class with objects and methods

Firstly, you want to creat an object about the midterm score of a student. Then you asssign it to a class named "student".

{% highlight r %}
midterm <- list(name = "Rachel", score = 97, lettergrade = "A")
class(midterm)
{% endhighlight %}



{% highlight text %}
## [1] "list"
{% endhighlight %}



{% highlight r %}
class(midterm) <- append(class(midterm),"student")
class(midterm)
{% endhighlight %}



{% highlight text %}
## [1] "list"    "student"
{% endhighlight %}

Secondly, you may define the method to get the information of the student's letter grade.

{% highlight r %}
letter_grade <- function(x)
 {
     UseMethod("letter_grade",x)
 }

 letter_grade <- function(x)
 {
    return(c(x$lettergrade))
 }

letter_grade(midterm)
{% endhighlight %}



{% highlight text %}
## [1] "A"
{% endhighlight %}
