---
title: "Working with date and time"
author: "Ryan Morgan"
topic: "04"
layout: post
root: ../../../
---


## What are intervals, durations, periods, and instants?
Instants, intervals, durations, and periods are four time related objects that are used in the lubridate functions. An instant is a specific moment in time. For example, February 13th, 2017 is an instant. An interval is a span of time that occurs between two specific instants. For example, the span of time between February 13th, 2017 to February 14th, 2017 is an interval. This span of time is a day long, but is specific to the day long period between those two dates. An interval is similar to, but different from durations and periods. A duration is a generic time span, measured in seconds. For instance, instead of saying February 13th, 2017 to February 14th, 2017 (an interval), a duration would be 86,400 seconds. Durations are always measured in seconds. A period is a generic time span in units larger than seconds. For instance, instead of having 86,400 seconds (a duration), a period would be 24 hours. Periods don’t have consistent lengths, since not all units of time always have the same length. For example, a month is not always the same number of seconds, since not all months have the same number of days. 

## Why do we need these distinctions?

It is important to have the distinctions between these four objects because making the distinctions makes it easier to do arithmetic with date-time data. Perhaps the most obvious example of why a distinction is needed between these objects is trying to describe changes of time in unique situations. For example, 1 month is a period, but depending on what month we are talking about determines how many days, which determines how many seconds that 1 month is. So adding one month to August 25th is adding a different number of seconds then adding one month to February 25th. If working with periods instead of durations, strange things can happen in adding time. The article uses the example of adding one second to the instant right before daylight savings time kicks in. The result of adding one second to this unique time (in the article 2010-03-14 01:59:59 CST) is different than the result of adding one second to a different time. Understanding the distinctions in these four objects allows us to understand how our code or functions are interpreting and treating date-time data, and understanding how the data is interpreted makes using the functions simpler.

