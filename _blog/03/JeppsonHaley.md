---
title: "A Layered Grammar of Graphics"
author: "Haley Jeppson"
topic: "03"
layout: post
root: ../../../
---

***

### How does having a grammar help with creating charts?

The motivation behind the grammar of graphics seems similar to that of literate programming and the split-apply-combine strategy – when tackling a complicated task, it is advantageous to tackle it one step at a time. Having a grammar of graphics allows for you to see a plot as a construction of a small number of building blocks. 

In `ggplot2`, the layered grammar specifies the following five large building blocks which can then be broken into smaller blocks:  
  
1. **Defaults**
  + A dataset 
  + A set of aesthetic mappings
2. **Layers**
  + A statistical transformation i.e. `stat_bin`
  + A geometric object i.e. `geom_line` or `geom_point`
  + A position adjustment   i.e. stacking or dodging bar charts, or adding jitter to points
  + (optional) a dataset 
  + (optional) a set of aesthetic mappings
3. **Scales**
4. **Coordinate system**
5. **Facets**


Viewing a plot in terms of these building blocks significantly simplifies the task of making complex, multi-layered visualizations. Similar to how a grammar of a language assists in constructing meaningful sentences out of a set of words, a grammar of graphics assists in constructing a meaningful graphic out of a set of graphical elements. 

Interestingly, many graphs share many features of their construction. As Wickham points out in *A Layered Grammar of Graphics*, when applying the grammar, a pie chart is only different from a stacked bar geom drawn in that it is plotted in a polar coordinate system rather than a cartesian coordinate system. Having a grammar allows for the similarities and differences in different types of graphs to be better recognized. 

Understanding the underlying components of a graphic does more than help you in composing the plot, it aids in the interpretation of the final graphic and in the development of new software for statistical graphics not already supported. Additionally, I think the true advantage of having a grammar is that when it is easier for us to create and interpret the graphic, it allows us to spend more time and energy on refining our plot and creating the *right* graphic for our data and audience. 
