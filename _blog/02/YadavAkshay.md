---
title: "Split-Apply-Combine..."
author: "Akshay Yadav"
topic: "02"
layout: post
root: ../../../
---



One of the best advantages of R language over other scripting languages like PERL or PYTHON are the abilities to iterate over multidimentional arrays or lists without the annoying FOR/WHILE loops. For example, if we want calculate column-wise means for some tabular data in PERL or PYTHON, a nested for loop for rows inside a for loop for columns is required. 
This can be easily achieved in R without the FOR/WHILE loops using the base functions, which split the matrix columns-wise; apply the mean function on each column and return the combined means of all the columns in form of an array. The R base functions that can use this split-apply-combine strategy on data structures are the functions from the apply family - lapply, sapply, mapply and other functions like aggregate
The main limitation of these is that they require specific input formats and the output formats are restricted. For example, lapply will only return a list. Also, the R base functions cannot be used easily, if splitting on multiple columns is required.

We will study the split-apply-combine strategy used by different functions on the **Glass** dataset from the **mlbench** package

{% highlight r %}
library(plyr)
library(dplyr)
data(Glass,package = "mlbench")
{% endhighlight %}



{% highlight text %}
## Error in find.package(package, lib.loc, verbose = verbose): there is no package called 'mlbench'
{% endhighlight %}

There are 7 different Types of Glass in the dataset with other 9 columns giving the amount of different elements present in the corresponding type


{% highlight r %}
Glass %>% glimpse()
{% endhighlight %}



{% highlight text %}
## Error in eval(expr, envir, enclos): object 'Glass' not found
{% endhighlight %}



{% highlight r %}
table(Glass$Type)
{% endhighlight %}



{% highlight text %}
## Error in table(Glass$Type): object 'Glass' not found
{% endhighlight %}

We will calculate the mean of each element present in each type of Glass using the split-apply-combine strategy where first we will split data- rows-wise - according to the Glass type, apply the mean function to each portion of the data, and then combine the results

### Using the **aggregate** function

{% highlight r %}
aggregate(Glass[1:9],list(Type=Glass$Type),mean)
{% endhighlight %}



{% highlight text %}
## Error in aggregate(Glass[1:9], list(Type = Glass$Type), mean): object 'Glass' not found
{% endhighlight %}

### Using the **ddply** from **ply** package

{% highlight r %}
ddply(Glass,.(Type),summarize,mean.RI=mean(RI),mean.Na=mean(Na),mean.Mg=mean(Mg),mean.Al=mean(Al),mean.Si=mean(Si),mean.K=mean(K),mean.Ca=mean(Ca),mean.Ba=mean(Ba),mean.Fe=mean(Fe))
{% endhighlight %}



{% highlight text %}
## Error in empty(.data): object 'Glass' not found
{% endhighlight %}

### Using functions from dplyr packages

{% highlight r %}
Glass %>% group_by(Type) %>% summarise (mean.RI=mean(RI),mean.Na=mean(Na),mean.Mg=mean(Mg),mean.Al=mean(Al),mean.Si=mean(Si),mean.K=mean(K),mean.Ca=mean(Ca),mean.Ba=mean(Ba),mean.Fe=mean(Fe))
{% endhighlight %}



{% highlight text %}
## Error in eval(expr, envir, enclos): object 'Glass' not found
{% endhighlight %}





 
