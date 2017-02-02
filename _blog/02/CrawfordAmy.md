---
title: "Split-Apply-Combine..."
author: "Amy Crawford"
topic: "02"
layout: post
root: ../../../
---


**Which (base R) functions do you know that support the split-apply-combine strategy? In your opinion, are these sufficient - state why or why not?**.   
  
  
All of the base R functions that I know of that support the split-apply-combine strategy were listed in the paper. Those that I use most frequently are for loops, subset, rbind, and cbind. Sometimes I use apply, lapply, or sapply but these aren't usually the first functions that come to mind. I don't think these are sufficient because I often find myself starting with one function, getting stuck with naming, indexing, or errors and moving to another function that may be a better fit for the task I am attempting to complete. They are quite clunky and I frequently find myself typing out large lists of related variable names. We have now learned about the dplyr package in class and I really enjoy using the helper functions, starts_with will be especially useful for me. 



**Using a dataset of your choice, describe how you can use the split-apply-combine strategy for a part of the data analysis.**  
  
  
The dataset I am working with for my creative component contains data on wells and water pumps in Tanzania. As part of the data analysis I'll be splitting the data by water source type (spring, river, bore hole, dam, rainwater, etc.) and analyzing trends over time of the amount of water available to the water points. 
