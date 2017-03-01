---
title: "Functional Programming"
author: "Matt Stuart"
topic: "06"
layout: post
root: ../../../
---


## Making Code Easier to Write and Maintain Using Functional Programming

Using functional programming, it is much easier to write code because you do not have to write as many lines of code.  For example, if you wanted to apply the same function to multiple columns of a dataset, such as replace certain values with NAs to denote missingness or gathering summary statistics for multiple variables, it is much easier to write the code using a for loop or an apply function instead of hard-coding what you want done with every single column in a data set.  I know this is useful for me, because we will soon be obtaining a dataset with over 100 variables with some missing values for our research project, so using functional programming to recode any missingness will be much easier than hardcoding in all of those columns.

At the same time, maintaining code is made even simpler than when you're writing it because if you make a mistake in the coding, you can just change the function to make a fix by changing just one or two rows of code.  Otherwise, you would have to go into every single line of code you had made to manipulate the data, which is simply tedious work, and can be even more prone to errors based on a mistake by us humans.  I know if I hard-code for the dataset we are set to receive soon, I would likely make a simple mistake in the coding somewhere along the way, and it would be tedious enough just to find the mistake.  These are some of the reasons functional programming simply makes sense in coding in R, or any other language.
