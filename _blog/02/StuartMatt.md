---
title: "Split-Apply-Combine..."
author: "Matt Stuart"
topic: "02"
layout: post
root: ../../../
---

## Background:

The `plyr` package has by now been replaced by other, even faster packages, but the idea of *Split, apply, combine* is as relevant as ever.

Read the paper [The Split-Apply-Combine Strategy for Data Analysis](https://www.jstatsoft.org/article/view/v040i01) by Hadley Wickham.


Write a blog post addressing the questions: 

1. **Which (base R) functions do you know that support the split-apply-combine strategy? In your opinion, are these sufficient - state why or why not?**. 
2. **Using a dataset of your choice, describe how you can use the split-apply-combine strategy for a part of the data analysis.**


## Base R functions I know:

One way I use the split-apply-combine strategy in base R is using for loops.  For example, let's say I wanted to use the full weather station data used in class to get the average temperature from each station in the data set for each month over all years data.  The first thing I would do is to create a list of the unique weather stations by using the unique function.  Then I would create two for loops, one for the weather station IDs and another for the month, and use the mean function over a split data set to get the average temperature for that month at that station.  I would use the first data point to create another data frame to show the data and, for all other monthly data, I would use the rbind function to merge each data point into one final data set.

I do not believe these are sufficient.  As we tested in STAT 579, for loops can take a long time to run and get the data you want, especially if the data set is large.  For most cases, time is of the essence and it is inconvenient to take a large amount of time to run the code, and it takes even more time if you run the code and realize there is a mistake in the code.  Obviously, for loops can get the job done, but in terms of efficiency, it is far behind what some packages allow you to do.


