---
title: "LittleChickens"
author: "Katie Will"
topic: "10"
layout: post
root: ../../../
---

## Background:

By now all of you have collected some experience in writing an R package. How did that go? What were the difficulties? Have you got a story to share about a CRAN submission that went particularly well (or not)?

Write a blog post on your experience. 


## Response:

Overall, I think that my group did well in writing our first R package. Non of us had created an R package before, or worked in Github from RStudio. We found the instructions in the course notes to be very useful. However, we still ran into a couple issues that were somewhat frustrating. Both issues stemmed from the step in which we saved our data file.

1. We saved our data file with the extension .Rda instead of .rda.  We assumed that since all other R files have a capitalized "R" in their extension, we would do the same with an R data file.
2. We saved our data in our R environment as "data", read in using read.csv. We did not realize that save() not only saves the data to the appropriate file/file extension, but carries the environment name of the data with it. So, we were saving our data as Chicks.rda and our package was recognizing it as "data" instead of "chicks". 

Both of these issues were addressed after the lab (I'm assuming we weren't the only group to have these issues). With that being said, if I had any comments about how to approach R packages differently in the future it would be to address these potential issues first. I'm not sure if we would have figured out where our issues were if we did not have help. 

