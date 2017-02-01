---
title: "Split-Apply-Combine Strategy for Data Analysis"
author: "Yue Zhang"
topic: "02"
layout: post
root: ../../../
---

The powerful plyr package in R

As an R beginner I didn’t use plyr package intensively before, instead I relied on “tapply” or “sapply” to do most of the jobs. Wickham’s paper [1] on the introduction of plyr provided me a very good chance to learn it. 

The mechanism of plyr to deal with data is very intuitive, which comprises adopts the split-apply-combine strategy. It is in analog to how computers or people deal with large amount of data. Firstly divide the data into similar chunks, where each chunk represents the unit to be processed. Then the operation is applied to each chunk, which is similar to but is much more efficient than a loop in R. Finally the results of individual unit are combined so the desired operation is finished. At the first look what plyr’s idea is not much different from the function like “tapply” in R. However, the following aspects reveal the power of plyr. 

(1)	It can handle various classes of data very easily, without having to make everything ready by myself like using “apply” functions. For most classes of input data (e.g. lists, dataframes, arrays etc), plyr has a corresponding function designed to read and provides a variety of output data classes available. Even if I don’t do any operation of the data, these functions will save me a lot of time when converting data classes is necessary.
(2)	The more complex operation, the more effective and powerful will be when plyr is used to solve the problem. Without writing long nested loops, the same operations can be completed by only several lines of codes employing plyr. As a result, the whole coding will be more clear and readable.
(3)	Besides the major functions, plyr also provides a lot of “helper” functions, which are very useful when I want to use a function as input and return a new function as output.

For example, for the Houston flights data (in package “hflights”), I can (1) use the “filter” function to subset the dataset, (2) use the “select” command to pick the columns for analysis, (3) use the pipeline operators and the verbs to make the data preparation much easier. For instance, I can find the delayed flights with delay longer than 1 hour of various carriers and then sort these records according to the delay time. 

As a summary, learning the plyr functions is very attractive, as these features can greatly improve the efficiency of R my codes.


[1] H. Wickham, Journal of Statistical Software, 40, 1 (2011)


