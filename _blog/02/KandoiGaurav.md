---
title: "The powerful trio of Split-Apply-Combine"
author: "Gaurav Kandoi"
topic: "02"
layout: post
root: ../../../
output: pdf_document
---




## Which (base R) functions do you know that support the split-apply-combine strategy? In your opinion, are these sufficient - state why or why not?

Having taken the STAT579: An Introduction to R course, here at Iowa State, I'm fairly familiar with several base R functions which make use of the Split-Apply-Combine strategy. To split a data object, there are functions such as split() and subset(). Some of the common apply functions come from the popular "apply" family, i.e. apply(), sapply(), lapply() and mapply() etc. Other function which serve similar function include aggregate(). Finally, to combine the data back, we have rbind(), cbind(), and unlist() functions. These are some of the functions I use to perform the split-apply-combine tasks for my research. With practice, I now think that most of these base R functions are easy to use, but there is definitely a steep learning curve. A major problem with the base R functions is the fact that they behave absurd when dealing with different object types. Converting an object to another type is often a pain when using these functions.

Hadley discusses 12 key functions when describing the plyr package. These have the flexibility of giving back different output class than the input. The naming convention is straight-forward and easy to interpret. Although, I've used the base R functions quite a lot, I often find myself struggling trying to get the output I want. I'vent used plyr functions a lot, but having worked through them during the class and reading the well-written paper by Hadley, I would like to believe that these are more user-friendly. Because, I'vent seen any benchmarks comparing the performances of the base R function and the corresponding plyr functions, I would restrain myself from commenting on their efficiency.

## An example case

To illustrate the use of the split-apply-combine strategy, let's use the ChickWeights dataset. Briefly, the dataset is a time-series data that contains the weights of 50 chickens on 4 different protein diets measured at birth, every second day till day 20 and also for day 21.

Assume we want to build a model to predict the weight of a chicken based on the time and diet. It is always a good practice to scale the data before feeding it to a prediction algorithm. To accomplish this, we use the split-apply-combine strategy. We will first split() the weights based on the 4 diets. Then, we will scale the weights for every diet using the lapply() function for lists. This often helps reduce apparent biases in data measurements. Finally, we will combine the scaled weights in the original dataset using the unsplit() function.

The same can be accomplished using the plyr package and I think that is more intuitive and easy to follow.


{% highlight r %}
chicks <- split(ChickWeight$weight,ChickWeight$Diet)
chicks1 <- lapply(chicks,scale)
ChickWeight$weight_scaled <- unsplit(chicks1,ChickWeight$Diet)
summary(ChickWeight)
{% endhighlight %}



{% highlight text %}
##      weight           Time           Chick     Diet    weight_scaled    
##  Min.   : 35.0   Min.   : 0.00   13     : 12   1:220   Min.   :-1.3986  
##  1st Qu.: 63.0   1st Qu.: 4.00   9      : 12   2:120   1st Qu.:-0.8183  
##  Median :103.0   Median :10.00   20     : 12   3:120   Median :-0.2136  
##  Mean   :121.8   Mean   :10.72   10     : 12   4:118   Mean   : 0.0000  
##  3rd Qu.:163.8   3rd Qu.:16.00   17     : 12           3rd Qu.: 0.6230  
##  Max.   :373.0   Max.   :21.00   19     : 12           Max.   : 3.5716  
##                                  (Other):506
{% endhighlight %}
