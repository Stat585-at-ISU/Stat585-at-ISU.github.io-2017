---
title: "Which license would you pick for your R package?"
author: "Yue Zhang"
topic: "09"
layout: post
root: ../../../
---

Software licenses are about two things: copyright, and protecting yourself from being held liable if your software screws something up somewhere down the line. If you’re planning on releasing your package, there are many choices available for an open source license. For instance, the BSD and MIT licenses allow anyone to use the software in anyway without requiring much more than maintaining copyrights. Meanwhile, there are also many strong copyleft licenses such as GPL2.0, GPL3.0 and the Affero GPL3.0. 

If I am the author of a successful and popular R package, below are the points I should go through when picking a license:

(1)	Do I want to allow anyone to do anything at any time with the software? If so use the MIT or new (3-clause) BSD license, i.e. no copyleft and no discussion of patents. Moreover, I will also not hold any liability if the package doesn’t work as expected and causes any damage or loss. So if a software company wants to use the package as part of their code and sell a product, I will consider using these licenses. 

Nevertheless, these license terms don’t necessarily encourage the spirit of freedom and open source. It companies use or modify my codes for commercial purposes, they probably won’t make any change to the code open to the users.

(2)	The GPL take the licensing a step further and also require users/licensees/collaborators to disclose any changes they make if they redistribute the code in a source code or binary form. And the V3 license is further restricting in that it bans the use of the software in hardware that would forbid any software alterations. Therefore if I am a firm supporter of software freedom or want to ensure that if my package is used anywhere that the resulting derivatives are maximally published as open source ensuring software freedom, then I will look to GPL V2 or V3 licenses.

These licenses will be helpful for improving the package by the users. Since it’s already popular and then any change or improvement to it will enrich the functionality of code, then it may be more popular and can draw more developer to keep improving it, by making all the changes available to all the users. However, these licenses will limit the commercialization of the package.
