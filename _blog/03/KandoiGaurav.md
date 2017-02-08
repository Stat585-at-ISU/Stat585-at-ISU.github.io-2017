---
title: "A Layered Grammar of Graphics"
author: "Gaurav Kandoi"
topic: "03"
layout: post
root: ../../../
---

***How does having a grammar help with creating charts?***


I like the analogy between good grammar being the first step in building a good sentence and the grammatically correct but nonsensical graphics which Hadley makes in the introduction. This itself highlights the need and importance of having a good structured grammar for graphics. Having a grammar will help us identify the composition of a graph and might reveal interesting yet unknown connections between these components. Although the idea of using layers to build graphics seem intuitive after reading about it, the idea doesn't seem to occur otherwise. I remember reading articles and trying to figure out for hours how that beautiful graphic was created. Now that I've learnt quite a bit about *grammar of graphics*, I hope to not spend hours figuring things out.

Build upon the popular R package *ggplot2*, the paper **A Layered Grammar of Graphics** by **Hadley Wickham** is an enjoyable read. It is also very easy to follow and provides a very intuitive perspective on using graphical layers to build better graphics. I've always struggled reading through codes using *ggplot2* to create plots. I always wondered what aesthetics meant or how faceting worked! It was always difficult to follow along and now I know exactly why. It was my limited understanding about the *grammar of graphics* and how layers exactly worked. I now understand the components of a plot as defined by the layered grammar which include: 1) data and it's mapping to aesthetics; 2) layers with geometric object, statistical transformation, position adjustment and a dataset with its aesthetics mapping; 3) scale for each aesthetics mapping; 4) coordinate system and 5) the facet specification. Now that I've a better understanding about the internal structure of a plot as defined by the *grammar of graphics*, I hope to be able to use this knowledge to create and understand appealing and informative plots using *ggplot2*.
