---
title: "Working with date and time"
author: "Chelsey Legacy"
topic: "04"
layout: post
root: ../../../
---




Instants are a specific moment in time.  This measurement of time records the month, day, year, and time down to the second.(p. 8) Intervals are a span of time that occurs between two specific instants.  This is one of several ways to record a span of time. (p. 9) Durations are lengths of time spans measured in seconds.  Durations are good for comparing different intervals of time because they are measured by a unit of time that does not vary.  (p. 10) Periods are non-exact time spans measured in units larger than seconds (i.e years, months, weeks, days, hours, and minutes). Periods can be different lengths in seconds depending on when they occur. (p. 12)


It is important to have these distinctions because we may want a different measurement of time based upon the questions we have to answer with our data.  Durations are good for comparing different times. One example is comparing the times it takes two different balls to hit the floor once dropped from the same height.  However, we would want a different measurement of time if we were measuring something less precise, like the difference in ages between you and a friend.  This may be better measured as a period because we would be satisfied to know this answer in months. Using lubridate with these many time distinction calculation can be very helpful. For lab 2 we spent some time looking at "recent" movies, and there was some trouble determining how we wanted to define "recent" and how to calculate it from the dates give. Lubridate would have been a good package to use to solve that problem. I will definitely make use of it in the future.

