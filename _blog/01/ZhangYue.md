---
title: "Literate Programming..."
author: "Yue Zhang"
topic: "01"
layout: post
root: ../../../
---

Literate programming is an approach to programming which emphasizes that programs should be able to be read by people as well as compilers. Therefore programmers shouldn’t keep the documentation separate from the program but embed the program into the documentation.

Dr. Knuth’s speech introduced the development and applications of literate programming. He coined the term literate programming and created the original literate programming tool/language, WEB, which he used to write TeX and MetaFont. An experienced programmer, who wants to provide the best possible documentation for his program, needs two things simultaneously: a language like TeX for formatting, and a language like C for programming. Neither can provide the best documentation by itself; but when both are appropriately combined, the resultant language is much more useful than either separately.

I have been a programmer for several years, but I haven’t used literate programming so far. However, questions, such as how to improve the readability and implementation of my code are always in my mind. If my programs can be written in a format of book chapters, they can be understood easily for future reuse. Although I have the habit of adding enough (sometimes more than enough) comments in my code, I found it hard to track the details after sometime, for instance, the meaning of some parsed arguments in a certain function, especially among the functions. To get familiar again to my previous code requires much more efforts than modify or simply start the code from scratch. 

The immediate application of literate programming still seems unclear to me at this moment, because my programs are not so long and I don’t reuse them very often. However, the idea of literate programming is still inspiring. Therefore there are several potential application of literate programming in my workflow, because many programming tools can be extended to accommodate the idea of literate programming. For example, there is CWEB and literate SQL for C and SQL programming, respectively. As I searched the web, the feature of the “with” clause in SQL sub-queries can be used to implement literate programming. In next steps I will try to implement the literate programming and check if it will provide me codes with better documentation, readability and reusability. 
