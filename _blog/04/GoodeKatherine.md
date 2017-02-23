---
title: "Working with date and time"
author: "Katherine Goode"
topic: "04"
layout: post
root: ../../../
---


## What are intervals, durations, periods, and instants?

These four terms describe different ways of documenting time. They can be described as follows.

- **Instants**: These are particular points in time. For example, the first class for STAT 585 for the 2017 spring semester began at 2:10 pm on January 10, 2017.

- **Intervals**: An interval is the time between two instants. That is, it is a time span for which we specify the instant at which the interval begins and the instant at which the interval ends. For example, the 2017 spring semester at Iowa State has an interval of January 9, 2017 (first day of classes) to May 5, 2017 (last day of final exams).

- **Durations**: A duration is the exact length of time during an interval. A duration is measured in seconds since seconds are considered to be an exact time, whereas one month may consist of 30 days or a different number of days. For example, the duration of a class for STAT 585 is 4800 seconds long.

- **Periods**: A period is similar to a duration in that it the length of time during an interval, but its measure of time does not have to exact. It can be measured in a unit larger than seconds. For example, the period of a class of STAT 585 is 1 1/3 hours long.

## (Why) do we need these distinctions?

Time can be measured and recorded in many different ways, which can make the storing of time in an electronic dataset complicated. When trying to do manipulations with the times, it becomes even more complicated. These distinctions are helpful for creating a computer program that can handle the manipulations of different variations of times in datasets. Additionally, it is a good idea for the person working with the dataset to recognize which type of time one is working with. Depending of the objective of the analysis, a particular type of time may be more advantageous to be used than another. The analyst could even get into trouble if the measure of time does not take into account certain issues such as leap years and daylight savings times. 



