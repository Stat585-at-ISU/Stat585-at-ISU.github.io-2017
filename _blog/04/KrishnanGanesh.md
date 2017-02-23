---
title: "Working with date and time"
author: "Ganesh Krishnan"
topic: "04"
layout: post
root: ../../../
---

Lubridate is a very efficient package for carrying out date and time related tasks. A specific moment in time is
called instant while an interval is a time span between two instants. Periods is used to specify longer durations
of time than seconds like years, months, week, hours etc, but they need to be have an exact date-time of starting
and ending. Durations are similar in the sense that they describe any length of time. But the difference is it can 
be a larger unit or a shorter one as per our convenience. The length of an interval on the other hand is always 
clear as we know when it occurs and we can calculate the exact length of any unit of time that occurs during it. 
Durations are used more when comparing time based attributes like rates, speeds and lifetimes. 

The distinction is important as it helps us precisely program and get whatever kind of answer in terms of calculating
these time-date attributes. Manipulating many individual pieces of data described as date-time is complex and 
arithmetic with these is not easy. Such distinctions therefore make it easy to follow date-time specific arithmetic
rules and let us compare and recognize different moments of time
