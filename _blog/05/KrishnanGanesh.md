---
title: "The S3 class system"
author: "Ganesh Krishnan"
topic: "05"
layout: post
root: ../../../

---
We know that most R functions are writtten in C. But writing Base R functions in no longer possible, instead R
provides us a wih a neat object oriented programming based structure called the S3 which we can use to our benefit
whenever we need to create an object oriented style program. While dealing with S3 objects its good practice to first figure out the following:
1) class(X): This gives a class like objectt coming from object oriented programming (oops). Giving us a brief
idea to what class/ classes of functions does the S3 object belong to
2) Members of X: This will tell us about the hierarchy and kind of objects we need to deal with
3) Methods(class=class(X)): what kinds of methods are available. These are special functions that can be
implemented to accomplish a specialized task and deal with any required task as specified which is very much
depends on the S3 class in hand

A short program follows for making an S3 class that is essentially a description for each player a team (Club say 
Bayern München) in the sport soccer (I would prefer to call it football though). The class associated helps us 
define a set of attributes like player name, whether the player is in the first team, or the reserve team, the 
position he plays in, his age and if he is currently injured.

The FootballerDescription as defined below has therefore been made as a class. 


{% highlight r %}
FootballerDescription <- function(name,category = "First Team", position = "Forward", age = "", injured= FALSE)
  {
      playerattrib <- list(name = name,
                      category = category,
                      position = position,
                      age = age,
                      injured = injured)
    
              class(playerattrib) <- append(class(playerattrib),"FootballerDescription")
              return(playerattrib)
              }
{% endhighlight %}

In the above definition we see that we use the function class() to actually assign a name to the class. In order to
define a method for a class, the UseMethod command is used as shown below to define a hierarchy of functions for
appropriate actions. The UseMethod command is used here in the function playerposition for setting up the position
of the player if it needs to be changed.

{% highlight r %}
playerposition <- function(pos, newposition)
         {
                   UseMethod("playerposition",pos)
                    return(pos)
            }

playerposition.FootballerDescription <- function(pos, newposition)
          {
                      pos$position <- newposition
                      return(pos)
              }
{% endhighlight %}

Lets define a list for listing the 11 players with each element having the class list and the class
FootballerDescription and describing one footballer.


{% highlight r %}
player<- list()
{% endhighlight %}
Lets go ahead and describe the first player, and then we can go ahead and define the whole set of 11 players say in
FC Bayern München

{% highlight r %}
player[[1]]<- FootballerDescription(name = "Philip Lahm", age = "29")
player[[2]]<- FootballerDescription(name = "Thomas Müller", age = "27")
{% endhighlight %}
Both player[[1]] and player[[2]] took the segment "position" of the player fied as default which is described as 
Forward, but if we want to change the position of the first player i.e. Philip Lahm to say Left Back, we can do it 
as below, and then verify if it has changed to the new value.

{% highlight r %}
player[[1]]$position
{% endhighlight %}



{% highlight text %}
## [1] "Forward"
{% endhighlight %}



{% highlight r %}
player[[1]]<- playerposition(player[[1]], "Left Back")
player[[1]]$position
{% endhighlight %}



{% highlight text %}
## [1] "Left Back"
{% endhighlight %}
Now notice the different classes associated with player and player[[1]]. The former only has the class list while the latter has both the class list and FootballerDescription

{% highlight r %}
class(player)
{% endhighlight %}



{% highlight text %}
## [1] "list"
{% endhighlight %}



{% highlight r %}
class(player[[1]])
{% endhighlight %}



{% highlight text %}
## [1] "list"                  "FootballerDescription"
{% endhighlight %}
Thus we have an S3 class here and we can continue to create variables called players for this class, and change/
set the positon of the players if needed seperately.
