---
title: "Split-Apply-Combine Strategy"
author: "Xiangzhen Li"
topic: "02"
layout: post
root: ../../../
---

1. **Which (base R) functions do you know that support the split-apply-combine strategy? In your opinion, are these sufficient - state why or why not?**.

As I have learned in stat 579 course, the function to apply is “apply”, “sapply”, “tapply” and “aggregate” etc. The function to split data I learned is “subset”. And there is “rbind” and “cbind” functions to combine data. These functions are not sufficient and the usage of these functions are not flexible. Most of the time, we need to write loops for split-apply-combine steps in data analysis. For example, the functions of “apply” family apply for different data type, and have different usage. In the beginning when I learned these functions, usage of these functions confused me. I need to check help for detail of these functions every time. The functions in package “plyr” is a great idea. It does not only aggregate “split-apply-combine” into one function, but also names the function with easy to remember way. After reading Hadley’s paper, I learned the basic idea of **ply functions in “plyr” package. The functions seem to be convenient. I will read more details when I apply these functions in the future.

2. **Using a dataset of your choice, describe how you can use the split-apply-combine strategy for a part of the data analysis.**
For the french fires experiment. We could use "ddply" to easily know the mean or other statistic values grouped by variables. For example:


{% highlight r %}
library(plyr)
data(french_fries, package = "reshape2")
ddply(french_fries, .(treatment), summarize, 
      mean_potato = mean(potato, na.rm=T), 
      mean_buttery = mean(buttery, na.rm=T)) 
{% endhighlight %}



{% highlight text %}
##   treatment mean_potato mean_buttery
## 1         1    6.887931     1.780087
## 2         2    7.001724     1.973913
## 3         3    6.967965     1.717749
{% endhighlight %}
The above result shows mean of potato and mean of buttery for each treatment. We could roughly tell the difference of three treatmen. We split data by treatment, and then apply mean function to each group, then combine the result as above table.

{% highlight r %}
ddply(french_fries, .(treatment, time), summarize,
      mean_potato = mean(potato, na.rm=T), 
      mean_buttery = mean(buttery, na.rm=T)) 
{% endhighlight %}



{% highlight text %}
##    treatment time mean_potato mean_buttery
## 1          1    1    7.925000    1.7958333
## 2          1    2    7.591667    2.5250000
## 3          1    3    7.770833    2.2958333
## 4          1    4    8.404167    1.9791667
## 5          1    5    7.741667    1.3666667
## 6          1    6    6.079167    1.8250000
## 7          1    7    6.283333    1.2416667
## 8          1    8    5.175000    0.9869565
## 9          1    9    6.070000    1.8300000
## 10         1   10    5.465000    1.9600000
## 11         2    1    8.775000    2.4916667
## 12         2    2    8.537500    3.1250000
## 13         2    3    7.637500    2.0791667
## 14         2    4    8.204167    1.6083333
## 15         2    5    6.933333    1.8583333
## 16         2    6    7.016667    2.0541667
## 17         2    7    5.729167    1.3565217
## 18         2    8    5.641667    1.5826087
## 19         2    9    5.470000    1.6650000
## 20         2   10    5.580000    1.7950000
## 21         3    1    8.987500    2.4208333
## 22         3    2    8.050000    2.5166667
## 23         3    3    7.983333    1.9333333
## 24         3    4    6.533333    1.8166667
## 25         3    5    7.308696    1.7043478
## 26         3    6    6.916667    1.3791667
## 27         3    7    6.491667    1.5083333
## 28         3    8    5.479167    0.9875000
## 29         3    9    5.480000    1.2650000
## 30         3   10    6.065000    1.5400000
{% endhighlight %}
The above result shows mean of potato and mean of butery for each treatment and time.
