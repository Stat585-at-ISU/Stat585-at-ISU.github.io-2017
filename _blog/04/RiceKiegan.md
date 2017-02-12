---
title: "Time is Relative"
author: "Kiegan Rice"
topic: "04"
layout: post
root: ../../../
---


## What are intervals, durations, periods, and instants?  
Intervals, durations, periods, and instants are the different time related objects that `lubridate` uses in order to allow both exact and relative arithmetic with dates and times. An instant is a specific moment in time - a date and time of day. This is always an exact measurement of time. Intervals, durations, and periods are where the relative arithmetic functions come in. Intervals represent the timespan that occurs between two specific instants - i.e., the interval of time that occurs between the first day of January and the first day of February. Durations represents the actual measure of time that happens in that interval - i.e., the number of hours between the first day of January and the first day of February. Durations are most easily recorded in seconds, but we can also express those durations in other terms when we are using really large amounts of time. However, in that case it would be more convenient to use periods, which state our duration in terms of larger time periods - like how many months, weeks, days, or hours occur between the endpoints of our interval.  

## Why do we need these distinctions?
First, I think it is important to note that these distinctions are in fact useful. They allow us to look at different aspects of date and time that we may be interested in. Different situations and analyses call for different measurements of time. I think the distinctions between intervals, durations, and periods are especially useful because they allow us to measure how much time has passed between two instants in varying ways. If I am interesting in using a measurement of duration in seconds to calculate another variable (i.e. how many heartbeats per minute), having that recorded in seconds will be useful. However, if I just want to be able to compare something that happens over a longer period of time (i.e. time between hospital visits for a patient with a chronic condition), having periods in terms of days or months is much more useful and practical. I think the distinctions that `lubridate` makes are very useful for being able to accurately work with date data, while allowing the flexibility that is needed for thinking about things in terms of relativity. 
