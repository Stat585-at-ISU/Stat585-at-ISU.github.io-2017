---
title: "Split-Apply-Combine..."
author: "Taikgun Song"
topic: "02"
layout: post
root: ../../../
---

1. **Which (base R) functions do you know that support the split-apply-combine strategy? In your opinion, are these sufficient - state why or why not?**. 

I am not familiar with base R functions that support the split-apply-combine strategy other than the family of apply functions and functions that is an application of the family of apply functions (e.g. by, colSums/.../rowMeans, replicate, and etc.). In my opinion, these functions are sufficient enough, although the intended answer may be 'not sufficient'. I came to this conclusion because I do not have the neccesity of using other heavy packages that does a fancy split-apply-combine strategy, especially considering the type and structure of the data that I usually deal with.

Although loading the 'dplyr' package became a habit of mine (since STAT579), I always had a feeling that I am not fully utilizing the package.  I load 'dplyr' package because of the pipe operator, but this could be done by loading the 'magrittr' package which is much lighter. For my research, a combination of base R function such as 'subset'(or any other method that would split my data into biteable size), 'apply', and 'rbind/cbind' would do most of the trick. I will not say my code is super efficient nor nice looking, but I feel comfortable and safe using the base R package since I know what is going on. Also, it is easier for me to modify or tweak around with base R functions, compared to functions someone else have written. Maybe I just lack experiences using non-base R package or my data is not suitable for split-apply-combine strategy.  If I have chance to treat other types of data set, I may become a fan of non-base R functions that support the split-apply-combine strategy.


2. **Using a dataset of your choice, describe how you can use the split-apply-combine strategy for a part of the data analysis.**

I have a Twitter data set that consists hash-tag, user-id, and twitter-entry. A simple application of split-apply-combine strategy would be splitting the data set by each twitter-entry, apply some text scoring algorithm, and recombine by average score given hash-tag.  Then, one could find a general relationship between hash-tags and its mood.
