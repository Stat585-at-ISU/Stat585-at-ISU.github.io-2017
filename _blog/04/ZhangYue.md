---
title: "Working with date and time"
author: "Yue Zhang"
topic: "04"
layout: post
root: ../../../
---

The R package “lubridate” allows arithmetic of dates and times by introducing four new time related objects: instants, intervals, durations, and periods.
(1)	An instant is a specific moment in time, such as January 1st, 2012.
(2)	An interval is a span of time that occurs between two specific instants. The length of an interval is always explicit, because we know when it occurs.
(3)	If we record the time span in seconds, it will have an exact length since seconds always have the same length. We call such time spans durations.
(4)	Alternatively, we can record the time span in larger units, such as minutes or years. Since the length of these units varies over time, the exact length of the time span will depend on when it begins. These non-exact time spans are called periods.

These objects are very help to deal with date and time arithmetic under various situations. For example: we need to calculate the exact timespan under many situations, where the start and end of the time span as well as many corrections such as leap second, year or daylight saving time are to be accounted for. The “instant” allows to record the start and end of the time span, so that an interval can be defined. Or, the exact time span in seconds (the “duration”) is known, we are able to recover the start or end of the time point given one of the “instants” is known. When the time corrections are needed, we may use the object “duration”, since it is invariant to leap years, leap seconds, and daylight savings time. “Durations” are also the appropriate object to use when comparing time based attributes, such as speeds, rates, and lifetimes. When the timespan is recorded using larger time units than seconds (the “period”), we can still perform date-time calculations by adding or subtracting a period to an instant, thus the period becomes anchored to the instant. 

