---
title: "Split-Apply-Combine and airquality data"
author: "Kiegan Rice"
topic: "02"
layout: post
root: ../../../
---

## Which (base R) functions do you know that support the split-apply-combine strategy? In your opinion, are these sufficient - state why or why not?  

Some base R functions I know that support the split-apply-combine strategy would be things like __for loops__, __apply__, __lapply__, __sapply__, __mapply__ etc. Some of these were mentioned in the article. There are also things like __split__, __subset__, __merge__, and __rbind,cbind__. I don't believe that these functions are sufficient. While they allow us to do perform all the functions we need to to analyze data piece by piece, they aren't ideal in terms of computing time - for example, __for__ loops are much less efficient than even __apply__, as touched on in the article. I think that having a well streamlined and efficient set of functions in place - such as the __dplyr__ package that came after __plyr__ - is a much better option than using the functions I have listed above. It is also important to keep in mind that it is really easy for the split and apply part to get really messy with those base R functions. Code is hard to read and specific to a certain scenario, which doesn't make it easier to go back and change things if needed. Things like __merge__ are also tricky because they require careful detailing of exactly what needs to be put together and that is easy to slightly mess up. When you are working with a lot of data, if you have to be super specific about how the merge function needs to work, it is less simple to make changes later on. I have had this happen many times - either due to my own messy coding, or just the way the function is written. 

## Using a dataset of your choice, describe how you can use the split-apply-combine strategy for a part of the data analysis.  
Using the `airquality` dataset from the `datasets` package, we can use the split-apply-combine strategy to look at monthly averages rather than daily values. 


{% highlight r %}
library(tidyverse)
data(airquality)

airquality %>% head
{% endhighlight %}



{% highlight text %}
##   Ozone Solar.R Wind Temp Month Day
## 1    41     190  7.4   67     5   1
## 2    36     118  8.0   72     5   2
## 3    12     149 12.6   74     5   3
## 4    18     313 11.5   62     5   4
## 5    NA      NA 14.3   56     5   5
## 6    28      NA 14.9   66     5   6
{% endhighlight %}
Seeing the variables we have, we could split up the data by Month, calculate the mean (apply), and then add a variable that is the monthly mean for each observation back in to the dataset (combine). This would allow us to look at monthly averages instead of seeing the noise of daily variation. However, in this case, we might actually want to be able to see the bigger picture of what the pattern looks like when we consider every day. This is just one example of something we could do.  
