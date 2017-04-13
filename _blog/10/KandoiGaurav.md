---
title: "My first R package... Yayyy"
author: "Gaurav Kandoi"
topic: "10"
layout: post
root: ../../../
---

Writing a R package for the lab was a great learning experience. Even though we wrote a very basic function that gave the count table of any specified column of a data frame as the output, it was amazing to see how much goes behind developing an actual package. The main problem with our group's package was that of establishing dependencies with other packages. When we first wrote the function, we were importing other packages directly within our function using the `library()` function. Now, the function seemed to work on our system, but when we ran the `devetools::check()`, it gave us multiple errors and warning. Walking through the documentation and looking at other people's project, we were finally able to resolve the problems by defining the `@importFrom` roxygen2 tags in the code and the `Imports:` tag in the DESCRIPTION file.

We also did a very silly thing. We first wrote our function in the `HELLO.R` file which is created by default when creating a new package. We then created the new `.R` file for our function, without deleting the `HELLO.R` file. So, although we used the correct way to import dependencies in our actual function, we overlooked the `HELLO.R` file which still had the older function, calling dependencies using the `library()` function. We finally deleted the `HELLO.R` file and things were fine.
