---
title: "My first R package"
author: "Haley Jeppson"
topic: "10"
layout: post
root: ../../../
---
  
***
#### By now all of you have collected some experience in writing an R package. How did that go? What were the difficulties? Have you got a story to share about a CRAN submission that went particularly well (or not)?


***

I wrote my first R package, `ggmosaic`, last summer with the help of Dr. Hofmann. To get going, I skimmed [R packages](http://r-pkgs.had.co.nz/) by Hadley Whickham. It was a great resource and turned a daunting task into a relatively simple one. The more difficult parts of creating that package included troubleshooting bugs in the code, using the correct tags when documenting classes, generics, and methods, understanding how to fix the warnings from the CRAN check, and, finally, submitting to CRAN. 

It was those last two tasks that I found to be the most difficult. Dependencies in a package can be hard to navigate - especially when packages are continually being updated (in turn, breaking your code), or archived on CRAN (in turn, making functions you relied on no longer available). In addition, as Dr. Hofmann hinted to in class, there seems to be a set of unspoken rules that your package must follow when submitting to CRAN that are not checked for when running `devtools::check()`. For instance, when submitting to CRAN, I learned that the title field should be in title case, mosaicplots must be written as mosaic plots, how many examples should be included in the Rd files is subjective, and that it is not enough to credit well-known authors in the Rd file, but you may need to include them in the DESCRIPTION (after getting permission from them which may take some time). In the end, I learned a lot regarding the finer details of the package framework, and `ggmosaic` is now on CRAN with an average of over 600 downloads a month.

Though there were a few bumps in the road, my first experience in writing an R package was a great one. It's fun and motivating to see others using tools you spent a summer creating. I was pleasantly surprised with how manageable most of the process was and I look forward to writing more R packages in the future.

