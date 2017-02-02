---
title: "Split-Apply-Combine..."
author: "Haiyang Zhang"
topic: "02"
layout: post
root: ../../../
---

1. **Which (base R) functions do you know that support the split-apply-combine strategy? In your opinion, are these sufficient - state why or why not?**.

I learned split( ), apply( ), lapply( ), tapply( ), lapply( ), rbind( ), and cbind( ) in the Stat 579 class. And used them often when I did my homeworks and projects. There are also some other *split-apply-combine* functions in base R mentioned in the article by Hadley Wickham. For example, mapply( ), by( ), aggregate( ), sapply( ), and replicate( ). Personally, these functions are much better than writing long loops. These *split-apply-combine* functions in base R are much more concise and can save much time comparing to the loops. But comparing with `plyr` package, I will not say that these functions are as efficient as the `plyr` package functions. As mentioned in the article, we can replace multiple lines of base functions with only two lines with `plyr` functions sometimes. So I think it will be better if we can replace some base functions with the `plyr` package functions or use some base functions and `plyr` functions together. Therefore, I think the functions in the base R are not sufficient to support the *split-apply-combine* strategy.

2. **Using a dataset of your choice, describe how you can use the split-apply-combine strategy for a part of the data analysis.**

I used the data set *Titanic* to see the relationship between survive status vs. the class of the ship. I used `ddply` to arrange the dataset by Class first, by Survived second, and then use function `mutate` to add a new column which is the sum of the total number of the passengers in each class with each survive status. Finally, I plot the results with a bar chart by using ggplot2.

Code:

