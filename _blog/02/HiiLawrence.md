---
title: "Split-Apply-Combine..."
author: "Lawrence Hii"
topic: "02"
layout: post
root: ../../../
---

## Function that supports the split-apply-combine strategy

The basic one that I can think of is the sort() function in R. I took an algorithm class from computer science department this past summer. We learned that most sorting or ordering function in Excel or SQL or others are using Merge-Sort idea which is also one of the split-apply-combine strategies. For example, when we sort, let say "statistics" alphabetically, the system technically keeps breaking down the words (array) in to half length until granular level like a tree. Then at the lowest level the system orders and combines and move back up. 

This process is way more efficient than creating loop to compare first character to the rest of the characters etc.

Here is the link of the picture for merge-sort: https://s3.amazonaws.com/ka-cs-algorithms/merge_sort_recursion.png

## Example of dataset
We can use AirPassengers dataset here. We can remove the seasonality trend from time series using split-apply-combine strategy. I will plot the raw graph and identify if there is a seasonal trend, maybe every 12 months. Then I can split the data by 12 months and take average of each 12 months and combine them and look at the average trend. 
