---
title: "Split-Apply-Combine..."
author: "He Jiang"
topic: "02"
layout: post
root: ../../../
---


Write a blog post addressing the questions: 

1. **Which (base R) functions do you know that support the split-apply-combine strategy? In your opinion, are these sufficient - state why or why not?**. 

I used many apply functions before, such as apply(), mapply(), lapply(), aggregate(). They are sufficient most of the time, but I always need to code several different functions to get things done. For example, I need to use subset() at first to subset the needed dataset, and apply some functions to it, then use melt() to combine them in the end. So, they can get things done, just clunky. 


2. **Using a dataset of your choice, describe how you can use the split-apply-combine strategy for a part of the data analysis.**
I continue to use the french_fries dataset we learned in class. I want to see the main effect on time for the rating of potato. So, I split the data using group-by, and apply the summarise function to find mean and standard deviation for the rating of potato. From the output, it's the mean of rating of potato decreases as time increases, and standard deviations stay around 3.5. 


{% highlight r %}
french_fries %>%
  group_by(time) %>%
  summarise(mean_potato = mean(potato,na.rm=TRUE), 
            sd_potato = sd(potato, na.rm=TRUE))
{% endhighlight %}



{% highlight text %}
## Error in eval(expr, envir, enclos): object 'french_fries' not found
{% endhighlight %}

