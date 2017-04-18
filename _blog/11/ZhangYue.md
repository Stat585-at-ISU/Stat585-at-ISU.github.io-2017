---
title: "Interactive Statistical Graphics"
author: "Yue Zhang"
topic: "11"
layout: post
root: ../../../
---

In the video, Tuckey introduced the PRISM-9 system, which can do picturing, rotation, isolation and masking up to 9 dimensions. The idea of interactive statistical graphing and its realization were really at the cutting edge back to those days. As Tuckey mentioned at the end of the video, the interactive graphing was not only just to handle these operations individually, but also to integrate them in a single system. 

The interactive graphing is very important in statistical data analysis, because often times we need to visualize high-dimensional data but our eyes are limited to 3D space and the plotting is done in 2D. It is very helpful to have an overview of the data before setting out for detailed analysis. My experience of interactive statistical graphing mostly comes from the class, i.e. using plotly and ggvis. However, I have worked a lot on similar interactive graphing, for example to visualize the structures of materials in terms of the locations of the atoms in the 3D space. The tool I used can plot the atoms, color them according to different attributes, rotate the graph, cutting along a specific crystallographic plane and make animations using a frame of snapshots. I think these functions are very important to understand, or at least give me a feeling about what kind of structure I am dealing with. 

In the class and lab, I learnt that plotly and ggvis can make very useful interactive graphs. These tools not only make the graphs more clear, but also can show the results or data together with the graph, which can save a lot of space to show the results on a slide for presentations. Moreover, they also offer a rich collection of functions for isolating and masking the data. So beyond the functions in PRISM-9, we can now combine the plot and data together. It is also desirable if some operation oriented functions can be implemented, so data or results at hierarchical levels can be viewed. For instance, a map shows the state-level statistics, and when we click a certain state, county-level or city/town level data can be shown.
