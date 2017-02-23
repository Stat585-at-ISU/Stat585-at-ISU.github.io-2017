---
title: "The S3 class system"
author: "Matt Stuart"
topic: "05"
layout: post
root: ../../../
---


## Background:

In class, we have briefly touched on working with S3 objects. There are various online sources on this subject available, e.g. Hadley Wickham's chapter on [S3 objects](http://adv-r.had.co.nz/OO-essentials.html#s3), Cyclismo's [tutorial](http://www.cyclismo.org/tutorial/R/s3Classes.html), Abishek Tiwari's [blog post](https://abhishek-tiwari.com/hacking/class-and-objects-in-r-s3-style), ...


## Write a blog post addressing:

- At an S3 class of your choice discuss a set of functions/methods/approaches that allow you to interact with the class. Make sure to give plenty of examples!

## Interacting with the lm class

One of the most important parts in data analysis is fitting the data to a model, and the class "lm" has many important functions that allows me to interact with the class.  First and foremost, we can apply forward selection and backward elimination under the functions add1 and drop1 respectively to see how much better the model fit is when dealing with adding/dropping different variables to the model or adding/dropping interaction terms quadratic terms to the model.  Secondly, the summary function can provide estimates of each explanatory variable in the model, show its standard error and perform t-tests to test the significance of each individual term given all the other terms in the model.  The anova function can provide a similar test, using the Sum of Squares for each variable and factor to determine the significance of individual factors and variables given the others previously placed into the model.  What is also important is seeing if there is correlation between explanatory variables, and the vcov function can provide a variance-covariance matrix of those variables.  A visual aid for a model may also be useful in showing its significance, and the plot function can show the model graphically, provided the model is not too complicated.  

Finally, and what could be the most useful of model fitting, is the predict function.  The fitting of a model is an important step in data analysis, but the practicality of it is using new data for explanatory variables to predict values based on the fitted model.  This function can bring in a lm, plus a vector(s) of explanatory variables to predict new values.  Just as important, it can provide standard errors for the data to determine how much the predicted value can vary based on the fitted model.
