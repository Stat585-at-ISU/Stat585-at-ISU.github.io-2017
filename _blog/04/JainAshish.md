---
title: "Working with date and time"
author: "Ashish Jain"
topic: "04"
layout: post
root: ../../../
---

##Date and time

####Instants
When we capture a specific moment of time, it is called as an instant. For example, 14th February 2017, when we parse this into a date in R, it will create an instant having value `2012-02-14 12:00:00`. It is basically a data type to store a particular moment in time. In *lubridate* package, there is no separate class for instant objects. Instead, it recognizes any date-time object that refers to a moment of time as an instant.

####Intervals
In order to store a duration of time between two instants, intervals are used. An interval is defined as the span of time that occurs between two specific instants. In *lubridate* package an interval object has been defined which contains the start and the end instant of the interval.

####Durations
Duration is defined as the total amount of time span in seconds in an interval. If we remove the start and end instant from the interval, we left with a time duration. Now we can measure this time such that it will always have an exact or fixed length. For this, we use seconds and thus call this time span as duration.

####Periods
If the time span from the intervals is measured in longer time units such as minutes, hours, days, weeks, months, and years, it is defined as a period. The main difference between the durations and periods is that periods don't have a consistent length. For example, the number of days in each month is not the same and hence it is not consistent. However, if we measure periods in seconds it will be equivalent to duration.

I think these distinctions are quite useful. These distinctions have made playing with the time data very easy and efficient. As, we know that manipulating time dataset can be very challenging due to the time recalibrations such as daylight savings, leap years and leap seconds. In order to cater these things, *lubridate* has developed a number of different time definitions which take cares of those challenges. These different time definitions have their own usage depending upon the situation. For example, if we want to measure the time a car took to go from 0 to 50 mph, we will use exact units i.e. seconds which is also called as duration. On the other hand, if we want to know about the exact current day of the next year we will use periods which will give us a relative time and take cares of time recalibration. In my view, these distinctions are really good and can be used to manipulate time in a number of ways.
