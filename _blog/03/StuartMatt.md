---
title: "A Layered Grammar of Graphics"
author: "Matt Stuart"
topic: "03"
layout: post
root: ../../../
---

## Background:

Read the paper [A layered grammar of graphics](https://pdfs.semanticscholar.org/d779/6f85dabccd18673f382c100fc06f55e8b501.pdf) by Hadley Wickham (*Journal of Computational and Graphical Statistics*, 19(1), 2010, 3-28.)


Write a blog post addressing the question: *How does having a grammar help with creating charts?*

## Why a grammar is important.

There are two main reasons why having a grammar is important in creating charts.  The first, and the most important, is that it is easy to write any code to produce the charts or graphs that you need.  For example, using ggplot2, all commands are separated by a plus sign, so it is easy to put in a new layer to add something extra to the charts.  Also, it is easy to add scales and labels to the axes via new layers to separate out different data points and make the charts easier to read for others privy to the project.  Finally, if you want to add a graph that is side by side with another, all that is needed is to take your original code and add another layer instead of having to start all over with new code, making it easier to add additional visual aids.

The other main reason a grammar is important is that it makes the code easier to read for anyone who did not write it on a project or for anyone unfamiliar with the project.  For example, with ggplot2 and its layered format, it is easy to see how the graph was created.  Also, anyone can modify the code and add a new layer to the graph without disturbing the original graph that was created.
