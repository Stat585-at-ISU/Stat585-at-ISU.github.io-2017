---
title: "Working with date and time"
author: "Gaurav Kandoi"
topic: "04"
layout: post
root: ../../../
---



**Instants**

A specific moment in the entire time space is referred to as being an *instant*. For instance, we can use the *now()* function from *lubridate* package to get an instant down upto a second.


{% highlight r %}
paste("This is an instant:",now()) 
{% endhighlight %}



{% highlight text %}
## [1] "This is an instant: 2017-02-23 17:31:55"
{% endhighlight %}

**Intervals**

It is the simplest way to record timespans.The span of time that occurs between two specific instants is an *interval* which also suggests that it can never be ambiguous.


{% highlight r %}
paste("This is an Interval:", interval(today(),now()) )
{% endhighlight %}



{% highlight text %}
## [1] "This is an Interval: 2017-02-22 18:00:00 CST--2017-02-23 17:31:55 CST"
{% endhighlight %}

**Durations**

*Durations* are when a generic length of time span between any interval is recorded in seconds. This elevates the problem of varying lengths of the same time span when measured in higher units like minutes or years. The durations are invariant to leap years, daylight savings and even leap seconds, because these are measured in seconds and provide an exact length.


{% highlight r %}
duration(46)
{% endhighlight %}



{% highlight text %}
## [1] "46s"
{% endhighlight %}

**Periods**

When the length of time span between any interval is recorded in larger units like minutes or years, it is referred to as a *period*.


{% highlight r %}
years(1) + months(2) + days(10)
{% endhighlight %}



{% highlight text %}
## [1] "1y 2m 10d 0H 0M 0S"
{% endhighlight %}


**(Why) do we need these distinctions?**

Not every place uses daylight saving. Not every year has the same number of seconds. Not all months have same number of days and subsequently hours, minutes and seconds. But, we would like to combine and analyze data from these different sources. It is therefore, essential that we have these distinctions between an *Instant*, *Interval*, *Duration* and *Period*. Depending on our data and question, we may want a specific measurement of time. Having these distinctions provide us with an option to choose the most approprate measurement unit. Suppose manufacturing industries would like to identify the *timespans* when the productivity is maximum. Now, a candy manufacturing industry would be interested in knowing the number of candies produced in a second and hence can use *durations*. However, a ship manufacturing industry would be interested in knowing the number of ships produced in one year. Using *durations* will be difficult to comprehend in this case. But, using periods will be much more appropriate and helpful. Given these distinctions, we can be more precise even down to split seconds when performing analyses.
