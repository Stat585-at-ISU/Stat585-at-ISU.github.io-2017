---
title: "The S3 class system"
author: "Chaohui Yuan"
topic: "05"
layout: post
root: ../../../
---

S3 objects are usually built on top of lists, or atomic vectors with attributes. Following is a simple example of how to create a S3 object of class student taking Stat585. 

{% highlight r %}
## a constructor functio for the "studentRecord" class: including first name, last name, maojr, grades array for each class taken, credit for each class
studentRecord <- function(firstName, lastName, major, scoreVec, creditVec) {
  if (!is.numeric(scoreVec)) stop("score must be numeric vector")
  if (!is.numeric(creditVec)) stop("credit must be numeric vector")
  if (any(scoreVec < 0) || any(scoreVec > 100)) stop("score must be between 0 and 100")
  if (any(creditVec <  1) || any(creditVec > 4)) stop("credit must between 1 and 4")
  if (length(scoreVec) != length(creditVec)) stop("length of score must be the same as length of credit")
  this <- list(
    firstName = firstName, 
    lastName  = lastName,
    major     = major, 
    score     = scoreVec,
    credit    = creditVec
  )
  class(this) = append(class(this), "studentRecord")
  return(this)
}


## add a print method for studentRecord 

print.studentRecord <- function(obj) {
  cat("First Name  : ", obj$firstName, "\n")
  cat("Last name   : ", obj$lastName, "\n")
  cat("Major       : ", obj$major, "\n")
  cat("The courses have taken:\n")
  totCourses <- length(obj$score)
  cat(" Score \t\t\ GPA:\n")
  for (i in 1:totCourses) {
    cat(format(obj$score[i], nsmall = 1), "\t\t ", 
        format(obj$credit[i], nsmall = 1), "\n")
  }
  cat("\n")
}

## calculate a weighted average of scores weighted by credits 
mean.studentRecord <- function(obj) {
  gpa <- obj$score
  credit <- obj$credit 
  weight <- credit / 4.0
  mean(gpa*weight)
}
{% endhighlight %}


{% highlight r %}
## 
cat("Initializing a studentRecord oject s\n")
{% endhighlight %}



{% highlight text %}
## Initializing a studentRecord oject s
{% endhighlight %}



{% highlight r %}
s <- list(firstName = "Liz", lastName = "Smith", major = "stat",
          score = c(98, 96, 86, 80, 90, 79), credit = c(3.9, 3.8, 3.7, 3.5, 3.4, 3.2))
class(s) <- "studentRecord"
print(s)
{% endhighlight %}



{% highlight text %}
## First Name  :  Liz 
## Last name   :  Smith 
## Major       :  stat 
## The courses have taken:
##  Score 		 GPA:
## 98.0 		  3.9 
## 96.0 		  3.8 
## 86.0 		  3.7 
## 80.0 		  3.5 
## 90.0 		  3.4 
## 79.0 		  3.2
{% endhighlight %}


{% highlight r %}
## weighted mean score 
mean(s)
{% endhighlight %}



{% highlight text %}
## [1] 79.33333
{% endhighlight %}


