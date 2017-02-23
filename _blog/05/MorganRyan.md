---
title: "The S3 class system"
author: "Ryan Morgan"
topic: "05"
layout: post
root: ../../../
---


For a small example of definining a new S3 class with objects and methods, I will create 3 different data frames. The first data frame will be a list of 3 NFL quarterbacks with their passing yards for the 2016 season, the second will be a list of 3 NFL runningbacks with their rushing yards for the 2016 season, and the third will be a list of 3 NFL wide receivers and their receiving yards for the 2016 season.

{% highlight r %}
qbs <- data.frame(players = c("Matt Ryan","Kirk Cousins","Aaron Rodgers"), yards = c(4944,4917,4428))

rbs <- data.frame(players = c("Zeke Elliot", "Jordan Howard", "Demarco Murray"), yards =c(1631, 1313, 1287))

wrs <- data.frame(players=c("Julio Jones","Odell Beckham Jr.","Mike Evans"), yards = c(1409,1367,1321))
{% endhighlight %}

Currently, the class of all three dataframes (qbs, rbs, and wrs) is just "data.frame". I will define the class of each dataframe as the position group they represent (ex: the class of the qbs dataframe will be "quarterback").

{% highlight r %}
class(qbs) <- "quarterback"
class(rbs) <- "runningback"
class(wrs) <- "widereciever"
{% endhighlight %}

Now say we want a funciton that gives us a summary stat of the player, but we want a different summary depending on what class we input (either quarterback, runningback, or widereciever). We can write a set of functions using the generic.class() format. In this case, we will use a set of summaryStat functions to print out a summary statement of the players and their yardage statistic.

{% highlight r %}
summaryStat <- function(x)UseMethod("summaryStat")

summaryStat.quarterback <- function(x){
  numPlayers = length(x$players)
  counter=1
  
  while(counter<numPlayers+1){
    statement= paste("The number of passing yards for ",x$players[counter]," was: ",x$yards[counter], sep="")
    
    print(statement)
    counter=counter+1
  }
}

summaryStat.runningback <- function(x){
   numPlayers = length(x$players)
  counter=1
  
  while(counter<numPlayers+1){
    statement= paste("The number of rushing yards for ",x$players[counter]," was: ",x$yards[counter], sep="")
    
    print(statement)
    counter=counter+1
  }
}

summaryStat.widereciever <- function(x){
    numPlayers = length(x$players)
  counter=1
  
  while(counter<numPlayers+1){
    statement= paste("The number of receiving yards for ",x$players[counter]," was: ",x$yards[counter], sep="")
    
    print(statement)
    counter=counter+1
  }
}
{% endhighlight %}

And so now we can use the summaryStat function on our three dataframes where the class of the dataframe determines which summaryStat() function is used.

{% highlight r %}
summaryStat(qbs)
{% endhighlight %}



{% highlight text %}
## [1] "The number of passing yards for Matt Ryan was: 4944"
## [1] "The number of passing yards for Kirk Cousins was: 4917"
## [1] "The number of passing yards for Aaron Rodgers was: 4428"
{% endhighlight %}



{% highlight r %}
summaryStat(rbs)
{% endhighlight %}



{% highlight text %}
## [1] "The number of rushing yards for Zeke Elliot was: 1631"
## [1] "The number of rushing yards for Jordan Howard was: 1313"
## [1] "The number of rushing yards for Demarco Murray was: 1287"
{% endhighlight %}



{% highlight r %}
summaryStat(wrs)
{% endhighlight %}



{% highlight text %}
## [1] "The number of receiving yards for Julio Jones was: 1409"
## [1] "The number of receiving yards for Odell Beckham Jr. was: 1367"
## [1] "The number of receiving yards for Mike Evans was: 1321"
{% endhighlight %}
