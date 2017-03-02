---
title: "Functional Programming"
author: "Ganesh Krishnan"
topic: "06"
layout: post
root: ../../../
---
Functional programming by definition involves creating and using functions in creative ways so as to minimize 
repetitive efforts, give clarity and to be able to efficiently manipulate different variables and functions itself. 
Now lets look at the following code


{% highlight r %}
x <- 1:10
funs <- list(
  sum = sum,
  mean = mean,
  median = median
)
y<-lapply(funs, function(f) f(x, na.rm=TRUE))
{% endhighlight %}



{% highlight text %}
## Error in FUN(X[[i]], ...): could not find function "f"
{% endhighlight %}

The above chunk of code first defines a vector x and then creates a list of summary functions. The
lapply function is then used to apply an anonymous functions f over the list. We can visualize the working of the 
code by imagining the anonymous function f to be applied over each member of the list funs. Calling a function from 
a list is straightforward as we first extract it and then call it.

We can see that the data vector x is already included in the anonymous function f and it performs an additional 
work of removing the na's from the vector x, therefore, when it is applied over each element of the list, we can 
imagine something of the sort f(sum()), f(mean()), and f(median()) happening. Now if you look closely at the 
anonymous function it takes f i.e. itself as the argument and by definition of f it contains the vector x (no 
matter what the input is). Therefore the result of the lapply function here is similar to 


{% highlight r %}
sum <- sum(x,na.rm=TRUE)
mean <- mean(x,na.rm=TRUE)
median <- median(x,na.rm=TRUE)
{% endhighlight %}

We could have achieved the same, as given above, but doing so using functional programming is much more compact. 
Also using list of functions lets us summarise an object in multiple ways. It also allows us to work with data 
frames where there are multiple columns and ensures that we dont accidentally miss any column. Also functional 
programming as in the first code chunk allows us to generalise the code and reuse it.  As we saw, using an 
anonymous function is sometimes desired especially when it’s not worth the effort to give it a name. This helps is
reducing redundancy and having an overload of named objects. Another important aspect of Functional programming is 
that it makes use of Lexical scoping which determines where to look for values. This is helpful especially because 
R looks for values when the function is run, not when it’s created, allowing the output of a function to be 
different and depending on objects outside its own environment. Using functional programming therefore not only 
makes is easier to write code but also makes
the process of mainting and reusing it simpler.
