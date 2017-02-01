---
title: "Split-Apply-Combine Strategy "
author: "Xiangmei Zhang"
topic: "02"
layout: post
root: ../../../
---

1. **Which (base R) functions do you know that support the split-apply-combine strategy? In your opinion, are these sufficient - state why or why not?**.

Based on my knowledge, R functions that support the split-apply-combine strategy include apply(), lapply(), tapply(), sapply(), split(), aggregate(). And another clumsy way is writing a loop function according to the specific question. Apparently, loop function is not an efficient solution to get information because it will take much more time than *apply() functions. To be honest, I usually can not tell apart apply(), lapply(), tapply(), sapply(), I think they are good for use when I need to apply a simple function to split data, but not so sufficient if multiple functions needed to be done.


2. **Using a dataset of your choice, describe how you can use the split-apply-combine strategy for a part of the data analysis.**

I think the split-apply-combine strategy can be commonly used in a multi-factor dataset when we want to check how the factors affect the response variable. For example, in French_fries data, one simple case is to analyze oil type main effects on potato flavor, to answer this question, we need to split the data according to oil type treatment, and apply mean function to all split part then combine lsmeans for all treatments. 
