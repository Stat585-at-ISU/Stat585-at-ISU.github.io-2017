---
title: "A Layered Grammar of Graphics"
author: "Chaohui Yuan"
topic: "03"
layout: post
root: ../../../
---

*How does having a grammar help with creating charts?*

A grammar of graphics creates a efficient way to communicate with data visulization. 
When I use `plot` function in base R with other function, say `lines`, there is no such concept of mapping, 
layer at all. At very first, it might seem have to write more lines just to create a figure using `ggplot2` than 
base R function. But once get used to it, it's really super powerful using `ggplot2` to produce some complicated 
figures. The first step `mapping` allows people to think about how to present/visulize the data in a better
way, including not only the corordinates of each data point wanna present, but also including the shape, color
and so on. The most powerful thing that I like ggplot2 is the characteristics of `layer`. It 
allowers to add/customize figure when ever needed by simplil enough using a symbol `+`.  
Before reading this paper, this always confuses me why this works even I get used to this. 
Only after reading this paper, it mentions tha each layer is actually an object. That makes a lot sense to think 
about a figure as an object and then later on could manipulate a plot. Another characterisitcs of `facet` is also very handy. 
It makes the syntax much shorter to create a plot and facet by a certain variable using `ggplot2` than base R function.  
Although sometimes the R is a little bit of longer by following such a grammer, it's easier to understand the meaning of code 
since the way of creating the figure is exactly the same of the way of thinking. 
