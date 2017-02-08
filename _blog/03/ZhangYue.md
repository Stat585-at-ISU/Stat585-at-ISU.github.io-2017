---
title: "A Layered Grammar of Graphics"
author: "Yue Zhang"
topic: "03"
layout: post
root: ../../../
---

## How does having a grammar help with creating charts?

Creating high quality and attractive charts is very important for scientific publications nowadays. When I plotted data or create graphs, the first things in my mind are mostly the elements of a graph, such as the graph type, colors and shapes of the points and some legends. Nevertheless, Wickham’s paper [1] on the layered grammar of graphics has provided me a new perspective to understand the graphics. Having such a layered grammar provides a strong foundation for understanding a diverse range of graphics. Actually this paper also provides a good background knowledge of the R package “ggplot2”.

In layered grammar of graphics, the key components of a chart (the data, mappings, statistical transformation and geometric object) are encapsulated into a layer. A chart may consist one or more layers, together with other “formatting components” such as scales and the coordinate system, facet specification and so on make up for the entire chart. It is quite interesting to view the main body of the chart as a layer or stacking of multiple layers. 

In my opinion, there are many advantages to use the layered grammar to create charts. First, it provides an effective way of design and construct the desired graphs. Instead of trying every plan from scratch and having hard choices among designs, the layered grammar tells me the starting point and allows me to do “trials and errors” when constructing plots, simply by adding or deleting layers. Second, it makes the modifications a lot easier. Usually adjusting the elements on the graph is a cumbersome task, but under layered grammar the elements can be distributed into separated layers, allowing me to have a clear mind to identify where the changes should be and how to perform it. Finally, the layered grammar promotes my wish to try different combination effects of the layers even the graph type is fixed. Therefore I don’t need to rely on previous plot templates or preferences and can keep improving my graphical skills.

[1] H. Wickham, Journal of Computational and Graphical Statistics, 19, 3 (2010)
