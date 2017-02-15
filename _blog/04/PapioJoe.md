---
title: "Working with date and time"
author: "Joe Papio"
topic: "04"
layout: post
root: ../../../
---


## What are intervals, durations, periods, and instants?

*Instants* represent a point in time, whereas intervals, durations, and periods all represent spans of time. *Intervals* represent a span of time with a specific beginning instant and a specific end instant. *Durations* are precise spans of time without specified beginnings or ends; they are recorded in lengths of seconds so as to be invariant to weird idiosyncrasies of our calendar, such as leap years/seconds and daylight savings time. *Periods* represent spans of time that only have exactly known lengths (in seconds) once they are assigned a specific beginning and/or end point so that the previously mentioned idiosyncrasies of our calendar can be taken into account.

## (Why) do we need these distinctions?

These distinctions are particularly useful when the data and/or question(s) of interest involve measurement or consideration of time. Without these terms and their distinctions, what someone intends when they reference a unit of time may or may not be clear. 
