---
title: "The S3 class system"
author: "Xiangzhen Li"
topic: "05"
layout: post
root: ../../../
---

- Explain how a user can define a new S3 class with objects and methods at a small example of your choice. 

R is an object-oriented programming language. For every object, it has one attributes which is *class*. When we create function of the same section, it is like to put a "label"" on the function. R uses generic function to determine which method to invoke, depending on the *class* of the incoming object. 

First, we use command **class** to set the class attributes of function. For example, we create two function called *TA* and *RA* which return a list. And set class to these functions *TA* and *RA*.


{% highlight r %}
#---------TA
TA <- function(onduty=TRUE,youname="XZL")
{
  me <- list(
    YouAreoOnDuty = onduty,
    YouName = youname
  )
  ## Set the name for the class
  class(me) <- append(class(me),"TA")
  return(me)
}

#----------RA
RA <- function(onduty=TRUE,youname="QL")
{
  me <- list(
    YouAreoOnDuty = onduty,
    YouName = youname
  )
  ## Set the name for the class
  class(me) <- append(class(me),"RA")
  return(me)
}

#Test
t1<-TA()
t1
{% endhighlight %}



{% highlight text %}
## $YouAreoOnDuty
## [1] TRUE
## 
## $YouName
## [1] "XZL"
## 
## attr(,"class")
## [1] "list" "TA"
{% endhighlight %}



{% highlight r %}
t2<-RA(onduty = T, youname = "XZ1")
t2
{% endhighlight %}



{% highlight text %}
## $YouAreoOnDuty
## [1] TRUE
## 
## $YouName
## [1] "XZ1"
## 
## attr(,"class")
## [1] "list" "RA"
{% endhighlight %}
Secondly, we create method associate to these class. We create a generic function outside the class to check if the objects has the class from the section that we want to check. Then command **UseMethod** could define the name of the function. 

For example, create a generic function called *setOnDuty*. First, check if the object is *RA* or *TA*. Second, apply the *newValue* to objects if it is RA or TA.


{% highlight r %}
setOnDuty <- function(x,newValue) {
  print("Calling the base function")
  UseMethod("setOnDuty",x)}

setOnDuty.TA <- function(x,newValue) {
  print("You are in our school as a TA and setting the value")
  x$YouAreoOnDuty <- newValue
  return(x)
  }

setOnDuty.RA <- function(x,newValue) {
  print("You are in our school as a RA and setting the value")
  x$YouAreoOnDuty <- newValue
  return(x)
}

setOnDuty.default <- function(x,newValue) {
  print("You are not in our school and I don't know how to deal with you")
  return(x)
}
{% endhighlight %}

Test the **seOnDuty** function.

{% highlight r %}
t1<-TA()
t1
{% endhighlight %}



{% highlight text %}
## $YouAreoOnDuty
## [1] TRUE
## 
## $YouName
## [1] "XZL"
## 
## attr(,"class")
## [1] "list" "TA"
{% endhighlight %}



{% highlight r %}
t1$YouAreoOnDuty
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
t1<-setOnDuty(t1,FALSE)
{% endhighlight %}



{% highlight text %}
## [1] "Calling the base function"
## [1] "You are in our school as a TA and setting the value"
{% endhighlight %}



{% highlight r %}
t1$YouAreoOnDuty
{% endhighlight %}



{% highlight text %}
## [1] FALSE
{% endhighlight %}



{% highlight r %}
t2<-RA(onduty = T, youname = "XZ1")
t2
{% endhighlight %}



{% highlight text %}
## $YouAreoOnDuty
## [1] TRUE
## 
## $YouName
## [1] "XZ1"
## 
## attr(,"class")
## [1] "list" "RA"
{% endhighlight %}



{% highlight r %}
t2$YouAreoOnDuty
{% endhighlight %}



{% highlight text %}
## [1] TRUE
{% endhighlight %}



{% highlight r %}
t2<-setOnDuty(t2,"Leave")
{% endhighlight %}



{% highlight text %}
## [1] "Calling the base function"
## [1] "You are in our school as a RA and setting the value"
{% endhighlight %}



{% highlight r %}
t2$YouAreoOnDuty
{% endhighlight %}



{% highlight text %}
## [1] "Leave"
{% endhighlight %}



{% highlight r %}
t3<-"someone"
t3<-setOnDuty(t3,"Leave")
{% endhighlight %}



{% highlight text %}
## [1] "Calling the base function"
## [1] "You are not in our school and I don't know how to deal with you"
{% endhighlight %}
