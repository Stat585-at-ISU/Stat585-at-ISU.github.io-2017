---
title: "The S3 class system"
author: "Yue Zhang"
topic: "05"
layout: post
root: ../../../
---

Almost everything in R is an object, therefore learning how to work with object-oriented programming is very important. In the following, I will show how to define a new S3 class and methods using an example. 

The following simplified data is the median height and weight for eight male and female infants from CDC growth charts (http://www.cdc.gov/growthcharts).


{% highlight r %}
age = c(0, 3, 6, 12, 18, 24, 30, 36)                                      # in months
male.wt = c( 3.53, 6.39, 8.16, 10.46, 11.80, 12.74, 13.56, 14.33)         # weight of male infants, in kg
female.wt = c( 3.40, 5.86, 7.45, 9.67, 11.09, 12.13, 13.04, 13.87)        # weight of female infants, in kg
male.ht = c(49.99, 62.08, 67.86, 76.11, 82.41, 87.66, 92.13, 95.45)       # height of male infants, in cm
female.ht = c(49.29, 60.46, 66.12, 74.40, 80.80, 86.20, 91.13, 94.43)     # height of female infants, in cm
{% endhighlight %}

### Create a class 
S3 is a simple and ad hoc system; it has no formal definition of a class. To make an object an instance of a class, we need to take an existing base object and set the class attribute. 


{% highlight r %}
# define a class called "infant", it has attributes ID, sex, age, height and weight
infant <- function(ID, sex, age, ht, wt) {
   out <- list(ID=ID, sex=sex, data=data.frame(Age.month=age, HT.cm=ht, WT.kg=wt))
   class(out) <- "infant"
   invisible(out)
}
{% endhighlight %}

### Create two objects (x and y) from the class "infant", these are the groups of male and female infants


{% highlight r %}
x <- infant(1, "male", age, male.ht, male.wt)
y <- infant(2, "female", age, female.ht, female.wt)
{% endhighlight %}

### Create some methods (functions) that print and plot the group information


{% highlight r %}
# Print method for infant class
   print.infant <- function(object) {
   cat("Group ID =", object$ID, "\nSex =", object$sex, "\n")
   print(object$data)
}

# Plot method for infant class
plot.infant <- function(object) {
   data <- object$data
   par(mfrow=c(1,2))
   plot(data$Age, data$HT.cm, type="o", pch=15, col="blue",
        xlab="Age (months)", ylab="Height (cm)", main="Height vs Age")
   plot(data$Age, data$WT.kg, type="o", pch=15, col="blue",
        xlab="Age (months)", ylab="Weight (kg)", main="Weight vs Age")
   mtext(paste("Group ", object$ID, ", ", object$sex), side=3, outer=TRUE, line=-1.5, cex=1.5)
}
{% endhighlight %}


{% highlight r %}
print(x)
{% endhighlight %}



{% highlight text %}
## Group ID = 1 
## Sex = male 
##   Age.month HT.cm WT.kg
## 1         0 49.99  3.53
## 2         3 62.08  6.39
## 3         6 67.86  8.16
## 4        12 76.11 10.46
## 5        18 82.41 11.80
## 6        24 87.66 12.74
## 7        30 92.13 13.56
## 8        36 95.45 14.33
{% endhighlight %}



{% highlight r %}
print(y)
{% endhighlight %}



{% highlight text %}
## Group ID = 2 
## Sex = female 
##   Age.month HT.cm WT.kg
## 1         0 49.29  3.40
## 2         3 60.46  5.86
## 3         6 66.12  7.45
## 4        12 74.40  9.67
## 5        18 80.80 11.09
## 6        24 86.20 12.13
## 7        30 91.13 13.04
## 8        36 94.43 13.87
{% endhighlight %}


{% highlight r %}
plot(x)
{% endhighlight %}

![center](../figure/05/ZhangYue-6-1.png)

{% highlight r %}
plot(y)
{% endhighlight %}

![center](../figure/05/ZhangYue-6-2.png)
