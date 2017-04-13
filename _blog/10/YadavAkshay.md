---
title: "My first R package"
author: "Akshay Yadav"
topic: "10"
layout: post
root: ../../../
---

One of the main challeges in writing the R package was getting it ready for CRAN i.e. the goal of getting no errors or warnings when the `devetools::check()` function is executed on the package. The main sources of errors or warnings were the 3-party packages that were imported in our R package. Initially for importing other packages for our package (dependencies), I had simply used the `library()` function inside our package functions. This is not the right CRAN convention for importing packages dependencies, instead, the `@importFrom` roxygen2 tag in the '.R' file is supposed to be used. The imports should also be mentioned in the DESCRIPTION file


