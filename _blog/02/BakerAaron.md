---
title: "Split-Apply-Combine..."
author: "Aaron Baker"
topic: "02"
layout: post
root: ../../../
---

# Function that supports the split-apply-combine strategy

The functions that I am familiar with come from the base apply functions within R. I am quite familiar with them and using them to nest within one another to do quite complicated sets of functions together that work quite elegantly.

Having said that, there have been an occasion or two where I was stumped and had to resort to more 'hard code'/loop style methods that were ugly and hard to read through and not the easiest to code, either. These functions work by parsing lists, matrices, and arrays based on thinks like column, row, list item, or value within a certain row.

Though it is not natural to me yet, I can see how the pipe can make coding more language rfriendly and more linear and 'direct' in its thought pattern in accordance to the function of the program itself. This makes it easier to read, go back to 5 months later and understand for myself, and to share with collaborators without them having to go through a headache to understand the stink what I just done.


# Example of dataset

In the lecture notes we used the french fry data set as an example. Here, we could use the french fry data and the apply functions to combine the negative and positive aspects into a single measure for each row of overall quality, subset it by say, time and treatment (along with the function subset), and then on each subset calculate the average and standard devation of these overall scores to see how the scores change over time.

