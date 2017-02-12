---
title: "Working with date and time"
author: "Xiangmei Zhang"
topic: "04"
layout: post
root: ../../../
---



- What are intervals, durations, periods, and instants?

An instant is a specific moment in time, such as January 1st, 2012.

An interval is a span of time that occurs between two specific instants and always have a positive length. But it is not very useful for date-time calculations.

A duration is a generic time span that we can use for calculation, it will have an exact length in second units.

A period is a non exact time span in larger units, such as minutes or years, and the length of these units varies over time.

- (Why) do we need these distinctions?

I think we do need all these 4 type of time record, so that we can use instants to read and identify the exact time point, and also perform accurate calculations with data times and handle time zones with duration object such as intervals, durations, periods class. By using duration type, we can have exact length in seconds. Periods can be added to instants, intervals and other periods. These distinctions make it much easier to work with date-time data.


