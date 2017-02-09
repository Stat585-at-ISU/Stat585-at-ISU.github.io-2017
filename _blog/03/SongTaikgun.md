---
title: "A Layered Grammar of Graphics"
author: "Taikgun Song"
topic: "03"
layout: post
root: ../../../
---

*How does having a grammar help with creating charts?*

If I define **grammar** as a set of rules accounting for some constructions, grammar graphics would be a set of rules for constructing graphical display. Having grammatical structure may seem to limit flexibility, however, I was convinced it might be the opposite after reading [A layered grammar of graphics](https://pdfs.semanticscholar.org/d779/6f85dabccd18673f382c100fc06f55e8b501.pdf) by Dr. Wickham.

This flexibility is achieved by establishing a systematic structure for components that are necessary for graphics. Thus, assuming that these components are independent of one another and by changing one or more components, different graphics could be generated in a coherent fashion. These different components are then combined to form a _layer_ which is responsible for creating the objects that are recognized on the plot. Dr. Wickham proposed five categories of components that determines a layer: data, aesthetic mappings, statistical transformations, geometric object and position adjustment. Since all layers share these five components, one could interactively update plots or change single feature at a time. Finally, a graphics could be constructed by multiple _layers_ along with _scale_, _coordinate system_, and _faceting_ by embedding the layered grammar into existing programming language.

Additional positive effect of having grammar of graphic is that the grammatical structure allows to develop some tools that possibly identify common mistakes or provide templates.

Thus, grammar helps with creating charts by giving flexibility and by providing templates and possible tools.
