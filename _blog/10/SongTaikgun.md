---
title: "My first R package"
author: "Taikgun Song"
topic: "10"
layout: post
root: ../../../
---

Although I had some knowledge of creating an R package prior to the assignment, collaborative programming of an R package via Github was another experience.  The assignment went smooth for the most part: writing the 'DISCRIPTION' file, using `Roxygen2`, using `devtools` , and \textit{et cetra}.  However, there were some troubleshooting processes as well.  For example, establishing a link between R package project on RStudio and the Github repository took more time than expected. Once established, however, the process of push and pull was much easier.  Another trouble was passing the CRAN check using the `devtools::check()` function. The package itself ran smoothly on the system, but `devtools::check()` reported some warnings and the package had to be fixed.

I was planning on creating an R package from a collaborative research project that I was working on, and this assignment definitely suggested a useful tip/experience for me.
