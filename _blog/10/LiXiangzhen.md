---
title: "My first R package"
author: "Xiangzhen Li"
topic: "10"
layout: post
root: ../../../
---

## My first R package
The first time that I tried to build an R package is in the beginning of last semester. I begin to work on my creative component last semester and the first part of my creative component is to build an R package called “RTseries” based on Prof. Meeker’s source code. This package is used to provide graphical tools for exploring and analyzing data using ARIMA time series models. The source code is written several years ago, and some of them are written in S-plus, and some of them are written in Fortran code. 
I met lots of problems when I was trying to build the package since I learned to build the package basically by myself. Three of them are difficult. First problem is that I built “. Rd” file which is the help file by hand the first time. It works well with the simple examples. However, when I finished built all the “. Rd” files and run the “check”, it bumps up lots of warnings. Most of the warnings are because the function did not been written correctly in “NAMESPACE”. Then I read the book “R packages” written by Hadley. I learned to use roxygen2 to generate “. Rd” files and manage “NAMESPACE”.

The second problem that I met is to add dataset in R package. I learned “Lazydata” to solve the current working environment. However, I found I need to include tens of dataset in the package. The “Lazydata” is not convenient and easy to make mistakes. In addition, raw data in the package is more flexible to use. So, I learned to put the data in “inst” file, also from Hadley's book.

The third problem is that the Fortran code in the source code gives me warnings. I was supposed to put a “lib” file in the package so that my computer could recognize the Fortran code. However, I did not correctly solve the problem. Prof. Meeker help me with the Fortran problem in the end. 

Even though we have solved all above problems, the package still not ready to upload it to CRAN. When we tried to upload it to CRAN, we were told we need to test the binary package file on Mac and Windows and other platforms. Right now, this package is being used by students in STAT 451 course. After the internal test, we will upload the package to CRAN next step.

