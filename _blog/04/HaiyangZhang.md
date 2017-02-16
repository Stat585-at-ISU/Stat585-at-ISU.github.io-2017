---
title: "Working with date and time"
author: "Haiyang Zhang"
topic: "04"
layout: post
root: ../../../
---

- What are intervals, durations, periods, and instants?

**Instants**: An instant is a specific moment in time, such as January 1st, 2012. We create an instant each
time we parse a date into R.

**Intervals**: An interval is a span of time that occurs between two specific instants. The
length of an interval is never ambiguous, because we know when it occurs.

**Durations**: If we record the time span in seconds, it will have an exact length since seconds always have the same length.

**Periods**: Periods record a time span in units larger than seconds, such as years, months, weeks, days,
hours, and minutes.

- (Why) do we need these distinctions?

Not every year has 365 days and not every month has 30 days. We need a rule to follow to describe time. We need different time unit under different circumstance. For example, if you want to describe the time that Usain Bolt running 100 meters, you may want to use seconds. But if you want to describe one person's age, you may want to use years. So these distinctions are very important.
