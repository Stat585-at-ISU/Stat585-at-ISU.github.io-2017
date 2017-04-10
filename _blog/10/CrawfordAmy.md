---
title: "My First R Package"
author: "Amy Crawford"
topic: "10"
layout: post
root: ../../../
---


My only previous experience writing an `R` package is from a small guided workshop during graphics group. One of the biggest challenges that we had was getting the group connected to the package on GitHub, this part took up most of the class period and we only got a short start writing the actual funcitons for our package. Getting everyone to the point where we could commit, pull, and push from `RStudio` was challenging for us. Another challenge we had was with our data. Although everything looked right, the package broke when I tried to use the data. The problem was that I had accidentally saved the `.rda` file outside of the `data` folder, thought it was no big deal, and dragged it into the correct folder. I was looking at Hadley's page for help and he recommends using `.RData` file extension, so that confused me. I finally figured out my problem (with help from Kiegan) was that I needed to use the `save()` function to directly place my `.rda` file into the `data` folder. This was painful. I couldn't figure out what was wrong. Everything looked right but the code was breaking. 

It was exciting when everything finally worked! I can see how things could get very complex and intricate very quickly, but I also see the tremendous value in having the documentation that comes with encapsulating functions in a package.
