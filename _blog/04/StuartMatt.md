---
title: "Working with date and time"
author: "Matt Stuart"
topic: "04"
layout: post
root: ../../../
---


## Background:

Read the paper [Working with date and time: http://www.jstatsoft.org/v40/i03/](http://www.jstatsoft.org/v40/i03/)

Write a blog post addressing the questions:

- What are intervals, durations, periods, and instants?
- (Why) do we need these distinctions?

## What are intervals, durations, periods, and instants?

An instant is a specific moment in time, including the year, month, day, hour, minute and second.  An interval takes two separate instances and measures the amount of time in between them.  A duration is similar to an interval, except the start and end dates are removed to record the time.  Finally a period is a time span that is recorded in larger units such as years, months, weeks or days.  Periods can be recorded in seconds, but then the period would have the same properties as a duration.

## Do we need these distinctions?

These distinctions are needed to properly analyze date information in an analysis, so the proper conclusion can be made.  The big difference between intervals and durations is the length of time of an interval in unambiguous because the start and end time is known, while a duration's length ultimately depends on when it begins.  Also, when analyzing time in terms of periods, the time lengths used in the analysis may not always have the same lenghts since, for instance, months or years never have the same number of days, meaning it is important to distinguish between a period and a duration.  Because of this, these distinctions are important when it comes to the analysis of time data.
