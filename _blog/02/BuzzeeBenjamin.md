---
title: "Split-Apply-Combine"
author: "Benjamin Buzzee"
topic: "02"
layout: post
root: ../../../
---



I'm aware of the apply family of functions in base R, as well as functions like aggregate and sweep. For combining data
I'm only aware of cbind, rbind, and adding arguments to c() or data.frame() to expand a vector or dataframe. One problem I have
with the base R apply family is that it is difficult to remember all the variations and identify which one is appropriate for the task at hand. Plyr's intuitive naming scheme for the 12 key functions goes a long way in overcoming this challenge.

In STAT 579 we analyzed microarray gene expression data using base R and it was quite difficult. The dataset came from the
Diurnal Papaya Project through the Donald Danforth Plant Science Center. The experiment exposed plants to differing amounts of light before measuring gene expressions. The experiment was
repeated twice, and genes were compared via euclidean distance after standardization. A key part of this analysis was 
taking an average across replications, substracting the row means, and scaling by the row standard deviation.

Using the split-apply-combine strategy outlined in the article, first we would take a subset of just the first row or two. Then
we would figure out exactly what we wanted to accomplish and write appropriate functions while testing them on the small subset.
Then we would use the appropriate plyr function to apply the standardizaiton function to the original dataset.
