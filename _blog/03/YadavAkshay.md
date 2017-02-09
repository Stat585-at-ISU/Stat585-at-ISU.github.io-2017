---
title: "A Layered Grammar of Graphics"
author: "Akshay Yadav"
topic: "03"
layout: post
root: ../../../
---

#### Anatomy of statistical charts

Lets start with an example. If we want to draw a chart by hand, we need atleast three 3 components, a paper or a surface to draw on, the type of chart (way of representing the data) and the actual data. The grammar of  graphics helps in defining each of these individual components separately and then combine them to produce the chart of any choice. This also gives the power to change any individual component without the need for changing the other components in the chart.

A layer is composite object or component that is made up of individual grammar components. For example, the 3 components described above will form a layer. It is smallest component required to produce and display a chart. Different layers can be added on top of each other to produce complicated charts that display multiple types of information from the same data. 

The hierarchy of layered grammar of graphic is as follows: the grammar components makeup the layers and layers can be combined with other layers to display multiple types of information. So the layers can be controlled independently, with the individual components also being controlled independently within the layers.

