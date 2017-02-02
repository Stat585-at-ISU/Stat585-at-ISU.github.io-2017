---
title: "Split-Apply-Combine..."
author: "Joe Papio"
topic: "02"
layout: post
root: ../../../
---

## Which (base R) functions do you know that support the split-apply-combine strategy? In your opinion, are these sufficient? State why or why not.
    
Some of the base R functions I've used for the S-A-C strategy include forloops (which I probably use more often than I should), rbind(), cbind() and c(), (which I often use inside a for loop to store results from repeated simulations or something like that), and also functions like merge() or subset(). Even pulling off parts of a dataset or vector or other object by a list of indices could be considered a base R function for application of S-A-C.

Often, if I'm doing something where I'm using nested forloops, I'll need to get out a piece of paper and draw out some of what's going on so I can make sure I'm getting the indexing (what Hadley refers to as bookkeeping) correct. And it will still often involve some trial and error after that, to make sure the results are getting stored correctly when I feed them into the recursive cbind(), rbind(), or c() step before the loop goes on to *i+1*. So while they might be sufficient in that they do get the job done (eventually), getting a forloop structure set up correctly can often be rather time consuming, so reliable alternatives are probably a better choice.

## Using a dataset of your choice, describe how you can use the split-apply-combine strategy for a part of the data analysis.

I'm currently in the process of writing some functions to collect and then utilize information from the output of the *stm* package. The package outputs a list of effects parameter estimates, and also does some plotting, but we'd like to be able to take the information from that output and create our own plots that more intentionally represent the information present in the estimates. For a set of simulations, the parameter estimates and their variance-covariance matrices are presented from the *stm* package output as a list of items. 

So far, I've written my functions mostly using for loops. But after rereading Hadley's paper (I think we read it a couple years ago for 579, if I recall correctly), I have been contemplating redoing that part of the function using plyr functions instead. It might be redoing some work, but it will probably produce a more stable function if I do try to publish it as a package. Using ldply to get from the list object to a dataframe which can then be melted or cast as needed, would probably be more efficient than my current method of using for loops to pull off individual elements and then rearrange them.

I've also yet to really tackle the incorporation of the variance-covariance matrices into the function as it currently stands, so it might be good to try out using dplyr on that part of it, then going back and applying that same strategy to the point estimates for the parameters.
