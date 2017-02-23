---
title: "S3 flavors"
author: "Katie Will"
topic: "05"
layout: post
root: ../../../
---

#### Explain how a user can define a new S3 class with objects and methods at a small example of your choice.

For this small example on S3 objects, lets assume we have two lists of ice cream flavors. The first list is of Blue Bunny seasonal flavors, and the second are of Edy's slow churned flavors. 

{% highlight r %}
BlueBunny <- list("Peppermint Party", "S'more Please", "Strawbunny Bliss", "Cocoa Bunny", "Cherrific Cheesecake")
Edys <- list("Mississippi Mud Pie", "Vermont Maple Syrup", "Coffee", "French Silk", "Cookies 'n Cream") 

BlueBunny
{% endhighlight %}



{% highlight text %}
## [[1]]
## [1] "Peppermint Party"
## 
## [[2]]
## [1] "S'more Please"
## 
## [[3]]
## [1] "Strawbunny Bliss"
## 
## [[4]]
## [1] "Cocoa Bunny"
## 
## [[5]]
## [1] "Cherrific Cheesecake"
{% endhighlight %}



{% highlight r %}
Edys
{% endhighlight %}



{% highlight text %}
## [[1]]
## [1] "Mississippi Mud Pie"
## 
## [[2]]
## [1] "Vermont Maple Syrup"
## 
## [[3]]
## [1] "Coffee"
## 
## [[4]]
## [1] "French Silk"
## 
## [[5]]
## [1] "Cookies 'n Cream"
{% endhighlight %}



{% highlight r %}
class(BlueBunny); class(Edys)
{% endhighlight %}



{% highlight text %}
## [1] "list"
{% endhighlight %}



{% highlight text %}
## [1] "list"
{% endhighlight %}

Currently, the class of the two lists is "list" by default. If we wanted to change the class, we can do it by using class(object) <- append(class(object), "class.name"). With this ice cream example, let's set the class of the Blue Bunny flavors as *Seasonal* and the class of the Edy's flavors as *SlowChurned*. This is done with the following two lines of code. 

{% highlight r %}
class(BlueBunny) <- append(class(BlueBunny),"Seasonal")
class(Edys) <- append(class(Edys),"SlowChurned")

class(BlueBunny); class(Edys)
{% endhighlight %}



{% highlight text %}
## [1] "list"     "Seasonal"
{% endhighlight %}



{% highlight text %}
## [1] "list"        "SlowChurned"
{% endhighlight %}

Notice that now *BlueBunny* and *Edys* are of both class *list* as well as the ones we just assigned. With S3 objects, we can create methods that work for only a certain class. This last holdiay season, Blue Bunny's holdidy flavor was Peppermint Party. So let's create a function, *GetHoliday*, that will extract this flavor. This is done with the following two functions.  

{% highlight r %}
GetHoliday <- function(x)
{
  UseMethod("GetHoliday",x)
}

GetHoliday.Seasonal <- function(x)
{
  return(x[[1]])
}

GetHoliday(BlueBunny)
{% endhighlight %}



{% highlight text %}
## [1] "Peppermint Party"
{% endhighlight %}



{% highlight r %}
#GetHoliday(Edys) ##doesn't work
{% endhighlight %}

Side note: If my regular expreassion knowledge was up to par, I could have gotton fancy and had the function search for the word "Peppermint" since that's a common holiday flavor. 

Anyways, if we were to use the function *GetHoliday* on *Edys*, we would get an error saying: __Error in UseMethod("GetHoliday", x) : no applicable method for 'GetHoliday' applied to an object of class "c('list', 'SlowChurned')"__. The function only works for *BlueBunny* because it is of class *Seasonal*. We could just as well create a function that only works for class *SlowChurned*. 
