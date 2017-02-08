---
title: "A Layered Grammar of Graphics"
author: "Dinesh Poddaturi"
topic: "03"
layout: post
root: ../../../
---

Knowing a good grammar in any discipline will help us to gain insights in that discipline 
and assists us in attaining a good outcome out of it. In our context having a grammar for charts helps
us to create complicated charts and understand them with less effort. It encourages us to 
create customized graphs rather than specific/inbuilt graphs and helps the developers to develop 
statistical graphics without rewriting the whole code (developers can add certain components to the existing ones). 

In the paper “A Layered Grammar of Graphics”, Hadley used ggplot2 to explain how we can build
a graph by the idea of layering. The main components of a layered grammar are *data, aesthetics,*
*geometric objects,* and *scales*. Together all these form a layer and by adding more components like
*facets, statistical transformations, coordinate systems* we can create a complicated chart with any
type of data. Some of the above components come with defaults, which is very helpful when 
incorporating multiple components together. The layered grammar gives us the freedom to 
experiment with different components, explore new formats and assists us to explicitly explain
complicated charts with less effort.
