---
title: "The S3 class system"
author: "Taikgun Song"
topic: "05"
layout: post
root: ../../../
---

## Explain how a user can define a new S3 class with objects and methods at a small example of your choice. 

I have created a short and naive algorithm for music recommendation using the S3 class system. The first step is to define 'Class' from my data. 

### Define Class
To begin with, I have created a toy data frame that has information of 8 musics with its title, genre, mood, and URL address. 

{% highlight r %}
dat=cbind.data.frame(title=c("i will always love you", "did youever love me", "sexy and I know it", "four to the floor remix", "december, 1963 (oh, what a night)", "forever", "Light Cavalry Overture", "cavalleria rusticana intermezzo"),
genre=rep(c("rnb/hiphop", "house/dance/electronics", "rock/metal", "classic"), each=2), 
mood=rep(c("positive", "negative"),4), 
url=c("https://www.youtube.com/watch?v=3JWTaaS7LdU", "https://www.youtube.com/watch?v=EAmVdgoghOw", "https://www.youtube.com/watch?v=wyx6JDQCslE", "https://www.youtube.com/watch?v=woE2h5k1NW4", "https://www.youtube.com/watch?v=nDxhugRKZ8g", "https://www.youtube.com/watch?v=WrQyPHzzfCA", "https://www.youtube.com/watch?v=XFQpPbjJWTc", "https://www.youtube.com/watch?v=BIQ2D6AIys8"), stringsAsFactors=F)
{% endhighlight %}

Here, I have constructed a simple function 'rec_music' that would define and return the above data set as a class.

{% highlight r %}
rec_music <- function(i=7)
{
  my_music <- list(
    my_title = dat$title[i],
    my_genre = dat$genre[i],
    my_mood = dat$mood[i],
    my_url = dat$url[i]
  )
  
  ## Set the name for the class
  class(my_music) <- append(class(my_music),"rec_music")
  return(my_music)
}

> rec_music()
$my_title
[1] "Light Cavalry Overture"

$my_genre
[1] "classic"

$my_mood
[1] "positive"

$my_url
[1] "https://www.youtube.com/watch?v=XFQpPbjJWTc"

attr(,"class")
[1] "list"      "rec_music"
{% endhighlight %}

### Define Method

A generic function 'setMusic' was defined to reserve the function name. Then 'UseMethod' function was used to target the function with name 'setMusic'. Then the code was written so that the class information of the object 'rec_music' was passed down to 'setMusic.rec_music'. For 'setMusic.rec_music' a simple function 'answer' was written so that one could change their preference for music recommendation.  A simple 'browseURL' function maybe useful for checking out the music that was recommended for the user.

{% highlight r %}
setMusic <- function(object)
{
  print("Calling setMusic function")
  UseMethod("setMusic",object)
  print("Note this is not executed!")
}
setMusic.rec_music <- function(object)
{
  answer <- substr(readline("Please Select Your Favorite Genre\n 1. RnB/Hip-Hop Positive\n 2. RnB/Hip-Hop Negative\n 3. House/Dance/Electronics Positive\n 4. House/Dance/Electronics Negative\n 5. Rock/Metal Positive\n 6. Rock/Metal Negative\n 7. Classic Positive\n 8. Classic Negative"), 1L, 1L)
  print("My music recommendation for you")
  object<-rec_music(as.numeric(answer))
  browseURL(object$my_url)
  return(object)
}
{% endhighlight %}


{% highlight r %}
> setMusic(rec_music())
[1] "Calling setMusic function"
Please Select Your Favorite Genre
 1. RnB/Hip-Hop Positive
 2. RnB/Hip-Hop Negative
 3. House/Dance/Electronics Positive
 4. House/Dance/Electronics Negative
 5. Rock/Metal Positive
 6. Rock/Metal Negative
 7. Classic Positive
 8. Classic Negative

3
 
[1] "My music recommendation for you"
$my_title
[1] "sexy and I know it"

$my_genre
[1] "house/dance/electronics"

$my_mood
[1] "positive"

$my_url
[1] "https://www.youtube.com/watch?v=wyx6JDQCslE"

attr(,"class")
[1] "list"      "rec_music"
{% endhighlight %}

If time permits, I would use S3 class system more efficiently by giving hierarchical class structure and inheritance. For example, the music class being at the top of the hierarchy, the next tier class would be the genre, and the information of the title and its URL would be stored at the lowest tier class. Maybe a scoring function that interacts with class(es) could be introduced in the recommendation system as well.
