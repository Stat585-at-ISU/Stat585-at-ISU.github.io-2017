---
title: "Split-Apply-Combine Data Analysis"
author: "Chelsey Legacy"
topic: "02"
layout: post
root: ../../../
---

Prior to reading this article, if I needed to manipulate data I would use the subset() function and/or for loops and nested for loops to apply functions to the vectors or individual items in a dataset.  I would then use rbind() or cbind() to put the vectors back together. I've always been warned that the for loops are a clunky way to manipulate the data frames and vectors in R, but on they fly, its always the method I think of first.  These methods, and others that exist in base R, are probably sufficient, in that they can eventually manipulate the data into the form that you want.  However, the plyr package described in the article "The Split-Apply-Combine Strategy for Data Analysis" would greatly simplify this process.  This package eliminates the need for complicated for loops and will make the code less lengthy and more efficient.  It seems like there is a slight learning curve with the functions in plyr, but it seems like an advantageous skill.


One of my favorite datasets in R is Edgar Anderson's Iris dataset.  We could use the split-apply-combine method for analysis of this data. The dataset contains the measurements for the sepal and petal lengths and widths in centimeters. The data is collected for 3 different species of iris.  We could split the data by species and then find the summary information (means, medians, standard deviations) of the sepal and petal lengths and widths for each species in order to compare the characteristics of the different species.  We could also use the split-apply-combine procedure to change the measurements to milimeters or inches or whatever measurement we think would be best for our specific analytical needs. There are many uses for the split-apply-combine method with this dataset and any other dataset we come across.


