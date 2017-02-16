---
title: "Working with date and time"
author: "Haley Jeppson"
topic: "04"
layout: post
root: ../../../
---

***

## What are intervals, durations, periods, and instants?

**Instants** are specific moments in time whereas intervals, durations, periods are spans of time. 
An **interval** is a span of time between two specific moments in time (two instants). Durations and periods both measure the length of an interval (the span of time between two instants). To measure the length, a measurement unit needs to be chosen. Because not all units of time are the same length (due to leap years, leap seconds, daylight savings time, etc.), the measurement unit selected is important. A **duration** is a time span measured in seconds and a **period** is a time span is measured in any unit larger than seconds. A duration is therefore a more precise measurement of a time span than a period, but not as convenient to interpret when dealing with larger spans of time.




### (Why) do we need these distinctions?

Without these distinctions, arithmetic with date-time data would be more difficult. For example, the length of an interval can vary depending on whether the duration or the period was recorded. The inconsistencies in lengths of time spans can occur for many reasons such as leap years/seconds, varying number of days in different months, or daylight savings time.  Additionally if we need to compare two intervals of time, it can become essential that the lengths of the two time spans are measured similarly. `Lubridate`, in recognizing the distinctions between intervals, durations, periods, and instants, allows for date-time operations to be simpler and more intuitive.


