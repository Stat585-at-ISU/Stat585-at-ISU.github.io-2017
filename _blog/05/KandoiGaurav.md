---
title: "The S3 class system"
author: "Gaurav Kandoi"
topic: "05"
layout: post
root: ../../../
---

#Explain how a user can define a new S3 class with objects and methods at a small example of your choice.

Defining a new S3 class with objects is fairly straight forward in R. In fact, it can be as simple as following:


{% highlight r %}
genes <- list(KRT1=0.4,BRCA1=0.2,ALDH=0,MAPK=2.8,IR10=1.5)
class(genes)
{% endhighlight %}



{% highlight text %}
## [1] "list"
{% endhighlight %}



{% highlight r %}
class(genes) <- append(class(genes),"GeneExpression")
class(genes)
{% endhighlight %}



{% highlight text %}
## [1] "list"           "GeneExpression"
{% endhighlight %}

Suppose we have expression values of these 5 genes for 3 conditions and we want to find out the genes which have highest expression values in each of these conditions.


{% highlight r %}
condition1 <- list(KRT=1,BRCA1=2,ALDH=5,MAPK=10,IR10=10)
condition2 <- list(KRT=0.2,BRCA1=20,ALDH=0.5,MAPK=10,IR10=1)
condition3 <- list(KRT=15,BRCA1=0,ALDH=1.2,MAPK=0,IR10=0.1)
expressions <- list(condition1 = condition1,condition2 = condition2,condition3 = condition3)
class(expressions)
{% endhighlight %}



{% highlight text %}
## [1] "list"
{% endhighlight %}



{% highlight r %}
#Assign class "GeneExpression" to the object expressions

class(expressions) <- append(class(expressions),"GeneExpression")
class(expressions)
{% endhighlight %}



{% highlight text %}
## [1] "list"           "GeneExpression"
{% endhighlight %}

We can now define a method, HighestExpression(), which will give us this information.


{% highlight r %}
HighestExpression <- function(x) {
  UseMethod("HighestExpression",x)
}
HighestExpression <- function(x){
    return(lapply(x, function(x) x[which.max(x)]))
 }

 HighestExpression(expressions)
{% endhighlight %}



{% highlight text %}
## $condition1
## $condition1$MAPK
## [1] 10
## 
## 
## $condition2
## $condition2$BRCA1
## [1] 20
## 
## 
## $condition3
## $condition3$KRT
## [1] 15
{% endhighlight %}
