---
title: "A Layered Grammar of Graphics"
author: "Ashish Jain"
topic: "03"
layout: post
root: ../../../
---

**How does having a grammar help with creating charts?**

Grammer is defined as a general set of structural rules which governs the composition of different structure in a natural language. For example, in English, the grammar governs the composition of clauses, phrases, and words. These set of rules not only provides certain guidelines but also helps in understanding a particular language thereby making it easier to use it effectively. Similarly, the layered grammar of graphics lay down a certain set of rules and instructions which help us in understanding the logic behind creating graphs and make its easier to draw them. Building plot by using layered grammar is similar to building sentences using grammar in English. Being a graduate student, I know the importance of making of beautiful and explanatory graphs in research, especially for the publications.

In the paper **"A Layered Grammer of Graphics"** by *Hadley Wickham* a very nice and detailed explanation of the grammar of graphics is written especially about *ggplot2* and its usage. They have talked about the different layers using which a graphic is being created using *ggplot2*. There are five major components in *ggplot2* which has been explained in the paper. It includes dataset and its mapping, layers of geometric objects, scale for the dataset, a coordinate system, and facet specification. Using these components we can develop a nice and explanatory chart/graphics. The most important thing about having a layered grammar is that it provides flexibility to the user. By using different layers a user can explore many different things which are not possible by using basic plots functions. In addition to that, it is a lot easier to make changes or manipulate a graph due to its layered structure. We don't have to deal with any complex code. In the paper, the integration of different components by using layered grammar has been explained really well by using the *layer()* function. It has made me think that how easy it is to plot complicated charts and graphs in *ggplot2* as compared to basic plots in R.
