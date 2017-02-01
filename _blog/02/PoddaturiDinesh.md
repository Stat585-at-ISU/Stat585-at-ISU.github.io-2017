---
title: "Split-Apply-Combine Strategy for Data Analysis"
author: "Dinesh Poddaturi"
topic: "02"
layout: post
root: ../../../
---
Most of us encountered a situation, where we want to compute some statistics for different variables by applying some logic on 
a large dataset with many variables/attributes. In traditional programming, we can use loops for computing the statistics. 
However, loops are time-consuming, and not memory efficient. In short, by using loops analyzing large datasets with many attributes 
does not result in optimized code. 

By using Split-Apply-Combine strategy, we can analyze large datasets by splitting with respect to each attribute, 
then applying necessary functions to compute statistics and then combining the results to get output in a meaningful format.

 **Which (base R) functions do you know that support the split-apply-combine strategy? In your opinion, are these sufficient - state why or why not?**.

Following are the base R functions that support split-apply-combine strategy that I know of
 
•	aggregate -  aggregates a data frame by applying a specific function to each column of subset of the data frame.

•	apply – applies a defined function to each row or column of a matrix.

•	lapply – applies a defined function to each element of a list.

•	by – applies a defined function to the subset of a data frame. 

Other base R functions that are mentioned in the paper are 

•	sapply – applies function on a vector and returns a vector or matrix or array.

•	mapply – multivariate version of sapply.

•	tapply – applies a function to the subset of a vector.

While the above functions support the split-apply-combine strategy, they are inconsistent. Each function has a different syntax, has only a specific type of input/output. As Hadley mentioned in the paper, most of the base R functions that support split-apply-combine focus mainly on arrays, matrices and lists not data frames. 

**Using a dataset of your choice, describe how you can use the split-apply-combine strategy for a part of the data analysis.**

I have a dataset with the population of each county in Iowa from 1991 to 2015. The attributes are County Name, Year, and Population. From this dataset, we can analyze the population trends over the years or by county. One way to analyze this is by splitting the data for each year and then performing some function to get a statistic like the mean population or total population in Iowa in the corresponding year. Once we calculate the necessary statistics, we can combine the results to form a data frame or a list or a table. Another way to analyze the population trends is by splitting the data for each county and then calculating the average population of each county in Iowa. After calculating it, we can combine the results and return it as a data frame/list/table. “plyr” package makes our job easier to perform split-apply-combine on any kind of dataset.
