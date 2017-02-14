---
title: "Working with date and time"
author: "Dinesh Poddaturi"
topic: "04"
layout: post
root: ../../../
---

- What are intervals, durations, periods, and instants?

Intervals, durations, periods and instants are time related objects in *lubridate*. By using these objects we can perform arithmetic operations with date-time in R.

*Instant* is a specific moment in time in R. Every time we parse a date into R we create an instant object.

*Intervals* is the duration of time between two instants. By subtracting two different instants we create an interval object or we can use the function *new_interval()* to create an interval object. By using *as.interval()* function, we can convert a timespan into an interval object.

*Durations* is the time span between two instants in seconds. By using this object we can measure the exact time span since seconds always have the same length irrespective of leap years, leap seconds and daylight saving time. By using the function *new_duration()* a duration object can be created. For large duration it’s cumbersome to type the seconds (for example 1 hour is 3600seconds, 1 year is 31557600), lubridate has special functions to avoid this. Functions *dminutes(), dseconds(), dhours(), dyears()* convert everything written inside the parenthesis (an integer) to seconds and makes our job easier. We can add or subtract two different duration objects. We can create a *duration* object from *interval* and *period* objects.

*Periods* is the timespan between two instants in units larger than seconds like minutes, days, weeks, months, and years. By using the functions *seconds(), minutes(), hours(), days(), weeks(), months(),* and *years()* we can create a period object. Periods are used to model clock times accurately regardless of the leap seconds, leap days and DST changes. By using *as.period()* function, we can convert a timespan to *period* object.

- (Why) do we need these distinctions?

As discussed in the paper we need these distinctions to perform any kind of operation on the date object.

In the paper Hadley Wickham used a simple example “how many weeks are there between Halloween and Christmas?” In order to calculate the exact number of weeks first we need to get an *interval* object between Halloween and Christmas. This interval object gives us the timespan between these two days. We can calculate the exact number of weeks by dividing an *interval* object with *duration* object (since it uses seconds).

Usually it is very confusing when dealing with daylight savings time and time zones. If we use *durations* object our results will be completely different, since we lose one hour in the spring and gain an hour in the fall. By using *periods* we can avoid the clock time changes caused by daylight savings, time zones and get the proper results.
