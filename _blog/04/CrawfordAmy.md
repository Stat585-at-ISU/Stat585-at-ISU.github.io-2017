---
title: "Working with date and time"
author: "Amy Crawford"
topic: "04"
layout: post
root: ../../../
---


## What are intervals, durations, periods, and instants?
An __instant__ specifies a specific moment in time, and an __interval__ is the span of time that occurs between two instants. __Intervals__ are associated with their start dates and end dates, and this restricts their usefulness. __Durations__ are lengths of time measured in seconds and stored that way. They don't have start and end dates associated with them and they are nice because they are invariant to leap year and daylight savings times. __Periods__ record time spans in units that are more intuitive than durations. We don't know exactly how long (in seconds) a period will be until we know when it happens. 

## (Why) do we need these distinctions?
We need these distinctions because there are situations when we will want to do calculations with dates for a specified moment, or range of moments, in time. For these situations we will want to use instants, intervals, and maybe periods. In other situations we would rather measure time in an arbitrary moment and for this durations will be very useful.
Periods are especially useful because we can work with the helper functions before anchoring the period to a moment in time. This becomes a very, very flexible way to perform arithmetic operations on dates.


