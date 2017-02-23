---
title: "an S3 of our own"
author: "Joe Papio"
date: "February 22, 2017"
output: html_document
---

## Explain how a user can define a new S3 class with objects and methods at a small example of your choice. 

The most straight forward way to create a new S3 object class is to define it and assign its class directly:


{% highlight r %}
cellmeansstm <- structure(list(Var1 = "year", Var2 = "partyID", Var3 = "race", Var4 = "gender"), class = "cellmeansstm" )
{% endhighlight %}

Then, for our new class, we need to identify a method or methods (ie function(s)) for it. For example, we can create functions which lists off the names and values in our new (basic) class: 


{% highlight r %}
listVars <- function(x, ...){
  UseMethod("listVars", x)
}

listVars <- function(x){
    for (i in 1:length(x)){
      print(x[[i]])
    }
 }

listVar <- function(x){
    for (i in 1:length(x)){
      print(x[i])
    }
 }

varNames <- function(x){
  for (i in 1:length(x)){
    print(names(x[i]))
  }
}
{% endhighlight %}


{% highlight r %}
listVars(cellmeansstm)
{% endhighlight %}



{% highlight text %}
## [1] "year"
## [1] "partyID"
## [1] "race"
## [1] "gender"
{% endhighlight %}



{% highlight r %}
listVar(cellmeansstm)
{% endhighlight %}



{% highlight text %}
## $Var1
## [1] "year"
## 
## $Var2
## [1] "partyID"
## 
## $Var3
## [1] "race"
## 
## $Var4
## [1] "gender"
{% endhighlight %}



{% highlight r %}
varNames(cellmeansstm)
{% endhighlight %}



{% highlight text %}
## [1] "Var1"
## [1] "Var2"
## [1] "Var3"
## [1] "Var4"
{% endhighlight %}
