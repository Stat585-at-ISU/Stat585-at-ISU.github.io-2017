---
title: "The S3 class system"
author: "Amy Crawford"
topic: "05"
layout: post
root: ../../../
---

## Explain how a user can define a new S3 class with objects and methods at a small example of your choice. 
We know that `R` treats everything like an object. One common attribute associated with an object is its class, and a user can set the class attribute using the `class()` command. Understanding these basics, a user can define a new S3 class by writing a function that creates an object of a certain class, and returns a copy.
The following example will demonstrate how a user can create an object of class type S3 and define methods.
First, I create a list and set defaults for data entries that are stored in the list. I then procede to set the class.

{% highlight r %}
Cupcakes <- function(myFlavor = "chocolate", myFrosting = "Buttercream", isGlutenFree = FALSE, isNutFree = TRUE)
{
  myFavorite <- list(favoriteFlavor = myFlavor,
                     favoriteFrosting = myFrosting,
                     isGlutenFree = isGlutenFree,
                     isNutFree = isNutFree)

        ## Set the name for the class
        class(myFavorite) <- append(class(myFavorite),"Cupcakes")
        return(myFavorite)
}
{% endhighlight %}
Now, I can create objects of class _Cupcake_ by calling the function.



{% highlight r %}
John <- Cupcakes(myFlavor = "Red Velvet", myFrosting = "Cream Cheese")
John
{% endhighlight %}



{% highlight text %}
## $favoriteFlavor
## [1] "Red Velvet"
## 
## $favoriteFrosting
## [1] "Cream Cheese"
## 
## $isGlutenFree
## [1] FALSE
## 
## $isNutFree
## [1] TRUE
## 
## attr(,"class")
## [1] "list"     "Cupcakes"
{% endhighlight %}


{% highlight r %}
Jane <- Cupcakes(myFlavor = "Peanut Butter", myFrosting = "Salted Caramel", isNutFree = "No - Includes Peanuts")
Jane
{% endhighlight %}



{% highlight text %}
## $favoriteFlavor
## [1] "Peanut Butter"
## 
## $favoriteFrosting
## [1] "Salted Caramel"
## 
## $isGlutenFree
## [1] FALSE
## 
## $isNutFree
## [1] "No - Includes Peanuts"
## 
## attr(,"class")
## [1] "list"     "Cupcakes"
{% endhighlight %}
Now I can create methods that are associated with the _Cupcakes_ class. The methods are defined in a generic way, then in a way that is very specific to the _Cupcakes_ class.


{% highlight r %}
setFavoriteFlavor <- function(obj, newValue)
        {
                print("Call the base setFavoriteFlavor function")
                UseMethod("setFavoriteFlavor", obj)
                print("This is not executed!")
        }

setFavoriteFlavor.default <- function(obj, newValue)
        {
                print("You screwed up. I do not know how to handle this object.")
                return(obj)
        }


setFavoriteFlavor.Cupcakes <- function(obj, newValue)
        {
                print("In setFavoriteFlavor.Cupcakes and setting the value")
                obj$favoriteFlavor <- newValue
                return(obj)
        }
{% endhighlight %}

Let's take a look at how the function works! The object class is recognized and the correct function is used.

{% highlight r %}
Jane$favoriteFlavor
{% endhighlight %}



{% highlight text %}
## [1] "Peanut Butter"
{% endhighlight %}



{% highlight r %}
Jane <- setFavoriteFlavor(Jane, "Vanilla")
{% endhighlight %}



{% highlight text %}
## [1] "Call the base setFavoriteFlavor function"
## [1] "In setFavoriteFlavor.Cupcakes and setting the value"
{% endhighlight %}



{% highlight r %}
Jane$favoriteFlavor
{% endhighlight %}



{% highlight text %}
## [1] "Vanilla"
{% endhighlight %}
The object class is recognized and the correct function is used.
