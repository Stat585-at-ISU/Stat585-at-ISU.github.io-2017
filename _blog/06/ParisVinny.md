---
title: "Functional Programming"
author: "Vinny Paris"
topic: "06"
layout: post
root: ../../../
---

I really liked how he talked about reducing duplicates even inside functions. I have honestly never that about that before. I have always just been proud of myself for writing the function in the first place so I didn't have to type something in a hundered times. I will say though that his putting functions in a list was a little weird to me. I never really think of functions in that sense before so it'll take some time for me to implement them. I will say though that while it is more efficient it does seem slightly less easy to read over the code he compares it to above in his book. 


{% highlight r %}
summary <- function(x) {
 c(mean(x, na.rm = TRUE),
   median(x, na.rm = TRUE),
   sd(x, na.rm = TRUE),
   mad(x, na.rm = TRUE),
   IQR(x, na.rm = TRUE))
}
{% endhighlight %}

To me that is  more readable and I know what it's doing at a glance (this is a small example though). Hadley's took me a second to figure out especialliay when he put the function into the arguement for lapply to get rid of the NA's. I think I'd rather that passed to the function he was creating in the first place as a step 1. I suppose I'm not a huge fan of anonomyous functions is what I'm trying to get at. Something I like for human readability is the names of the functions. They can usually be pretty good hints at what the function is doing, but when you use the anonmyous function I feel like I have to spend more time studying it to figure out what you did. Not that it's very long to study but more time than a simple glance. Part of the reason is that anonomyous functions seem to get passed to other functions quite a lot which makes for this weird nested reading in my opinion. Beyond that, I ffeel that anonomous functions are one of those things that people will slowly make longer and more complicated unless they have excellent self-control. 

But I feel like I've gone off topic. The point of this is to reduce the chance of making an error and to speedline the process. That is what functional programming allows us to do ultimately. If we can reduce duplications we can make the process easier to read (generally) and far less likely to mess up something small that will hide from you when you are looking for the problem. I als0 really liked his example of using listed functions with benchmarks. I just always find it fun to see the time it takes R to do something. Just a werid thing I enjoy. 
