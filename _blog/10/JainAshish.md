---
title: "My first R package"
author: "Ashish Jain"
topic: "10"
layout: post
root: ../../../
---

## Background:

####By now all of you have collected some experience in writing an R package. How did that go? What were the difficulties? Have you got a story to share about a CRAN submission that went particularly well (or not)? Write a blog post on your experience. 

Writing an R package was fun and exciting. During that process, I developed a lot of respect for all of the available well-documented packages. It was my first time of writing an R package. Although, the package we wrote was quite easy but making it ready for CRAN submission took more time than expected. We encounter many difficulties during the process. First, while updating the documentation, we forgot to delete the manual file (.Rd) of an older function due to which we were getting warnings while checking the package using devtools::check(). The second problem we faced was with the extension of the data we stored. Devtools only detect the data which have extension ".rda". Any other variation including ".Rda" or ".RDA" is not detected by devtools. In addition to that, we also faced problems while using the external libraries as we didn't know at that time that we have to give the dependencies in the DESCRIPTION file. All in all, it was a great experience and made me realize that there is a lot of efforts behind a well-documented R package.
