---
title: "S3 Objects"
author: "Vinny Paris"
topic: "05"
layout: post
root: ../../../
---
So, I decided to make a little (stupid) function that will hold as a list some basic stuff about a Dungeons and Dragons character or for a Pathfinder character. They both get their own classes and I used Methods to return two seperate lines for each class. This is actually a real cool tool now that I know how methods work. I have always done some ugly (and I do mean ugly) ifelse statements to work around different objects getting passed to my self built functions.This really streamlines the process of knowing where you objects are going in the function instead of having to go down 8 levels worth of ifelse statements. It makes it easier to read once you know what the methods are doing and how to interpret classes. For the actual technique of giving them a class the best way appears to just be to use the append function on class(x) 


{% highlight r %}
DnD <- function(which.person = which.person , my.race = "Elf", which.level = level, which.class = class)
{

        Player.1 <- list(
                Gamer = which.person,
                Race = my.race,
                Level = which.level,
                Class = which.class
       )

        class(Player.1) <- append(class(Player.1),"DnD")
        return(Player.1)
}

Pathfinder <- function(which.person = which.person , my.race = "Elf", which.level = level, which.class = class)
{

        Player.1 <- list(
                Gamer = which.person,
                Race = my.race,
                Level = which.level,
                Class = which.class
       )

        class(Player.1) <- append(class(Player.1),"Pathfinder")
        return(Player.1)
}
#Pathfinder is an old DnD-esq game if you are wondering. Very similar look though. 


example <- DnD("Vinny", "Half-Elf", 5, "Cleric")
example
{% endhighlight %}



{% highlight text %}
## $Gamer
## [1] "Vinny"
## 
## $Race
## [1] "Half-Elf"
## 
## $Level
## [1] 5
## 
## $Class
## [1] "Cleric"
## 
## attr(,"class")
## [1] "list" "DnD"
{% endhighlight %}



{% highlight r %}
ex2 <- Pathfinder("Nick", "Human", 8, "Druid")
ex2
{% endhighlight %}



{% highlight text %}
## $Gamer
## [1] "Nick"
## 
## $Race
## [1] "Human"
## 
## $Level
## [1] 8
## 
## $Class
## [1] "Druid"
## 
## attr(,"class")
## [1] "list"       "Pathfinder"
{% endhighlight %}



{% highlight r %}
GamingCharacter <- function(x){
  UseMethod('GamingCharacter', x)
}

GamingCharacter.Pathfinder <- function(x) {
print("Pathfinder, update already")
}

GamingCharacter.DnD <- function(x){ 
  print("DnD object, Nerd!")
}

GamingCharacter.default <- function(x)
        {
                print("Not a DnD Object")
        }
        
GamingCharacter(ex2)
{% endhighlight %}



{% highlight text %}
## [1] "Pathfinder, update already"
{% endhighlight %}



{% highlight r %}
GamingCharacter(example)
{% endhighlight %}



{% highlight text %}
## [1] "DnD object, Nerd!"
{% endhighlight %}
