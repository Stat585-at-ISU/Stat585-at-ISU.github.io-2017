---
title: "Working with date and time"
author: "Lawrence Hii"
topic: "04"
layout: post
root: ../../../
---


##  What are intervals, durations, periods, and instants?

An instant is like a moment or specific moment in time. An interval is a span of time that occurs between two specific instants that means it can never be ambiguous. A duration is a time length that has exact length like seconds. On the other hand, the non-exact time is called period. Periods measures time units greater than seconds like minutes, hours etc.


## (Why) do we need these distinctions?
I think it's the same concept when we change the question to why do we need seconds, minutes, hours and etc. For me, the biggest reason is the structure of our time or calendar. It is not uniform or not each month carries the same days which leads to years where there is leap year. Because of this, we need some structure to capture these differences which I think it is important. With instances, intervals, durations and periods, they helps our analysis be more precise even down to split seconds results. And also, I do really like lubridate idea where it simplifies time related variables.
