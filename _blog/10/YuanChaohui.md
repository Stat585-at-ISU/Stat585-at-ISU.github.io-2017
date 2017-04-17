---
title: "My first R package"
author: "Chaohui Yuan"
topic: "10"
layout: post
root: ../../../
---

After the last lab experience working on trying to create a R package, 
there were some troubles we encountered at the first place: one is the DESCRIPTION file, 
since we were not sure about the difference between depends and imports. It didn't pass through the `devtools::check()` at 
the first time, then we had to modify this file manually.  It took some time to figure out the error/warning message 
from `devtools::check()` and most of times it seems the issue of different R packages versions, and had to check it
out one by one. Another experience is about how to write function description/documentation using `roxygen`. 
Although there was just one simple function in our R package, to make it even simplier, we didn't consider all 
types of situation, for example how to handle error message. But I think if we really make our r package to be 
uploaded into CRAN, we definitely need to consider all those cases, and make our r function documnetation more user friendly.  
