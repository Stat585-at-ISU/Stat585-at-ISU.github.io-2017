---
title: "My first R package"
author: "Ganesh Krishnan"
topic: "10"
layout: post
root: ../../../
---

My first R package was a good experience as I learnt many things while trying to collaborate with my group members as 
well as trying to develop the R package. Developing individual fragments of code and then uploading your version on 
Github gave me a lot flexibility. On one instance when the development of package was apparently complete and 
everything was done I tried to run a CRAN Check, which surprisingly kept telling me that an unnamed and undocumented 
data set by the name .Random.seed  was detected, and this always happened for some reason during the build process of 
the package. The “.Random .seed “ was not present before the package was built, and after building the package I was 
able to remove it by using the rm() command. Yet, this error always popped up as a warning during the CRAN check, till 
I was saved by one of my  collaboraters who was able to updated the package by adding some documentation, and when I 
merged that version of the package, the warning stopped. I am still curious as to what was leading to that .Random 
.Seed object generation, as we did not have any random numbers being generated in the package. This was one the 
experiences I had while building my first R package.

