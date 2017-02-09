---
title: "A Layered Grammar of Graphics"
author: "Xiangzhen Li"
topic: "03"
layout: post
root: ../../../
---

 *How does having a grammar help with creating charts?*

The grammar helps us to build logical thoughts when we analyze data using charts. With the grammar, we could think more clear. Layer grammar for graphics would let us to decomposition a problem. It makes much easier when we are dealing with data analysis if the problems are decomposed into components. For example, to use ggplot2 package to draw a plot, first step is to define data and aesthetic mappings, then choose geometric objects of the plot. After the basic plot been built, we could add on other components step by step. Sometimes we are not clear what kind of plot could useful for problem solving in the beginning. With layer grammar, the basic plot might provide great ideas. And it is much easier to editing on basic plot or changing facet or other components while we have depth understanding for problems.

In addition, a strict and clear grammar helps beginners to get started easier. When we learned the basic “plot” function, it is simple to draw basic plot, while it is difficult to draw more complicated plot, at least for an R beginner. Ggplot 2 provide a concise and consistent grammar to draw all kinds of plot, no matter it is simple or complicated. I used to think ggplot2 is not flexible compared to qplot. The paper “A layer grammar of graphics” well explained how components such as geoms, scales and stats are used. I have a better understanding of ggplot2 which is useful and convenient. 

