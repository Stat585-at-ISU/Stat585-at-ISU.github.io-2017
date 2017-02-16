---
title: "Working with date and time"
author: "Chaohui Yuan"
topic: "04"
layout: post
root: ../../../
---


- What are intervals, durations, periods, and instants?
* An interval is a span of time that occurs between two specific instants. The length of an interval is 
well-defined and in `lubridate`, interval is an object to be used to calcualte the span of two instant. 
The length of an interval is never ambiguous, because we know when it occurs 
* A duration is a time span that record in second. In such way we will have exact the length.  The length 
of a duration is invariant to leap years, leap seconds, and daylight savings time because durations are 
measured in seconds. Durations have consistent lengths and can be easily compared to other durations.
* Periods recond a time span in units larger than seconds, such as years, months, weeks, days, hours, and 
minutes. We can use periods to accurately model clock times without knowing when events such as leap seconds, 
leap days and DST changes occur.
* An instant is a specific moment in time, such as January 1st, 2012. In `lubridate`, it recognizes any date-time 
object that refers to a moment of time as an instant. 


- (Why) do we need these distinctions?
Knowing the difference between those concept is necessary. First of all, we need to know what type of object we 
are working with when we're dealing with Time type of data, and what kind of operations we are allowed to use. 
Not all time objects are be switched between each other. For example, periods can be added to instants, intervals,
and other periods, but not to durations.  Second this package `lubridate` makes the way of working on time data 
set much more easier, for example calculate the timespans, convert between different time zones, formate the date, 
parse the date-time and so on. 






