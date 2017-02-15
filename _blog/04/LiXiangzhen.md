---
title: "Working with date and time"
author: "Xiangzhen Li"
topic: "04"
layout: post
root: ../../../
---


- What are intervals, durations, periods, and instants?

Intervals:
Interval is a span of time that occurs between two specific instants. An interval should have length, start time and end time.

Duration:
Duration is a generic time span which is interval without start time and end time. The default length of duration is recorded by seconds. We could also change seconds to minutes, hours or other time unit measurements. Durations often used to do calculation. 

Periods:
Periods record a time span in units larger than seconds, such as years, months, weeks, days, hours, and minutes. If we use seconds as unit measurement for periods, it will have the same properties as durations.

Instants:
Instants is a specific moment in time. Every time we create a time point in R, R will create an instant.

- (Why) do we need these distinctions?

Different objects have different properties. Instants is easier for R to recognize time from variety of different forms. Interval is used to specify a specific time span in a real example. When we want to do calculation or comparison between time intervals, we could use duration. For calculation of longer time intervals, we could use periods. 

