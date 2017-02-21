---
title: "The S3 class system"
author: "Ben Buzzee"
topic: "05"
layout: post
root: ../../../
---
## S3 Classes

New S3 classes in R can be constructed in two ways. The simplest way is to assign an existing object a class using
the command class(x) <- "class_name." Another way is to use a constructor function that creates an object from and assigns a class name
to the constructor's argument. To illustrate the idea of classes we can use an example. Suppose we had two lists of animals. One
is a list of animals we generally consider safe to be around and one consists of dangerous animals. We can create a new S3 class
by assigning them a class attribute. The code would look like this: friendly <- list("dog", "cat"); dangerous <- ("bear,"alligator")
class(friendly) <- safe; class(dangerous) <- unsafe. We now have two objects with an S3 class, one with class safe, and the other with class
unsafe. If we wanted to write a function that treated safe and unsafe objects differently, we would first start by writing a generic
of the form: safety <- function(x) UseMethod("safety"), and then we would define a couple of methods, one for each class: safety.safe
<- function(x) { print("These animals are safe to be around.")} and safety.unsafe <- function(x){print("Avoid these animals.")}.
Both methods are of the form generic.class, where the generic is telling us that we want to use one of the subfunctions of safety,
and the class tells us exactly which one to use.
