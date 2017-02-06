---
title: "Split-Apply-Combine..."
author: "Chaohui Yuan"
topic: "02"
layout: post
root: ../../../
---
1. **Which (base R) functions do you know that support the split-apply-combine strategy? In your opinion, are these sufficient - state why or why not?**. 
In base R, if it's data frame object, to split it by particular column(s), I usually select it by column names. But this is not tidious since I have to type the data frame name every time when I try to call a particular column. This would make the code much longer. Another function that would select part of a data frame would be `subset`, but this still have to requre type the data frame name every time, which is not efficient.  There are some functions in base R that are kind of playing the role of `apply`, such as `lapply`, `sapply`, `tapply`, `rowMeans`, `rowSums` and so on. Those functions can be widely applied to vector, matrix and data frame, which is handy. Also as far as know, by using those function would make the R computing more efficient than `for-loop`.  To combine data frame or matrix, `rbind`, `cbind` or `merge` are the most frequently base R functions that I most use.  So there do exists some base R functions that could accomplish **split**, **apply** and **combine** well. But the problem is that they kind of accomplish it seperately rather then put them together. When we are pre-processing any data set, it's common to use all of them. It would be super nice if could do this in a nicer and efficient way, in terms of removing duplicated typing and hopefully have a `piping` characterisitcs. Thanks to `dplyr` package, it makes this kind of job much easier than only relyed on base R functions. But there is still some disadvantages only use `dplyr` to clean up the data set, for example it's not that easy to switch between wide-format and long-format for a data set in `dplyr`. Also,  

2. **Using a dataset of your choice, describe how you can use the split-apply-combine strategy for a part of the data analysis.**
I usually use `dplyr` to clean data, add new columns/features into data set, or do some simple summary about the data by using `group_by` and `summarise`. 

