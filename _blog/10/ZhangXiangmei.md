---
title: "My first R package"
author: "Xiangmei Zhang"
topic: "10"
layout: post
root: ../../../
---
My first time to write an R package is working on a team in lab 5. Our team built a small R package named LittleChickens. The major issue during bulding the package is how to attach the data in the package properly. The error message we came across is "can not find the data". We tried several times and finally find where the problem is. We saved our data as .Rda instead of .rda extension and when we called function "save()" to save chicks data, the data object is named "data" while the saved file named "chicks", which confused us for a while when we later want to use the data.

I think we all learned from this experience about how to build a package and how to fix the problem. And there are many things we need to pay attention to, such ad attaching data in a package, writing help files, and I think one good way is to learn from other people's (successful) packages, i.e. dare to read!

