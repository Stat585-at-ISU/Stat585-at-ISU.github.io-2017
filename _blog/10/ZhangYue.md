---
title: "My first R package"
author: "Yue Zhang"
topic: "10"
layout: post
root: ../../../
---

Last lab was the first time I built an R package, and the learning was very helpful. Although I used many R packages from others, and those packages were like magic boxes to solve my problems. From the lab I learnt the basics to build an R package, e.g. how to put the data and source files into different folders, how to use Roxygen to write the documentation of the package, and how the code and documentation are arranged in the R code. It is very helpful not only for me to write a package, but also to get more details on how to read and learn others’ packages. 

However, I still met several problems writing the package. For instance the folder name and the extensions of the files are very critical and case-sensitive, otherwise wrong folder names or capital-letters cause troubles for R to find the data or the source code. The other problem was the Roxygen rules, it’s very convenient to generate the documentation, but the group spent quite a bit time on this part to fix the grammars. I also learnt how to develop the codes with the teammates using Github. At the end, when we ran the “devtools” to do a final check for the package, there are several warnings about the other R packages’ versions we included in our package, which was quite annoying to deal with. Nevertheless, I think the over-strict rules on CRAN to check the packages is understandable, meanwhile it is easy for the developers to manage all the packages from the users. Actually this is good for the users to have a high standard on their packages. Meanwhile the users can relatively easily read, learn and modify others’ packages. 

Overall, it’s quite exciting to write my first R package during the lab. Although it’s just a joy package, it makes me comfortable to learn others’ packages and develop my packages in the future.
