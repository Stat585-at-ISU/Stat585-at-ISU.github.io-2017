---
title: "Working with date and time"
author: "Taikgun Song"
topic: "04"
layout: post
root: ../../../
---
The definitions of intervals, durations, periods, and instants are given below.

- Instant: An instant is a specific moment in time. Requires date and time.
- Interval: An interval is a span of time that occurs between two specific instants. Since instant is a specific moment, an interval cannot be ambiguous.
- Duration: An exact measure of a span of time, preferably in seconds although other units could be converted into seconds.
- Period: A non-exact measure of a span of time, usually units that are larger than seconds.


These distinctions are important for arithmetic with date and time.
It is quite obvious that we need instants and an interval for a date-time calculation. However, the distinction between duration and period was interesting.
My initial thought was isn't having precise date-time, the better? But after reading the paper, I realized date-time arithmetic is more complicated than calculations with number. Period may be very useful since date-time arithmetic could be completed when leap years and daylight saving times are involved. Although there are certain patterns, it would be hard to write codes with exact measure when these factors are included.
