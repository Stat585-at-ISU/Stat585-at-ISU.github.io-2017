---
title: "Programming with Time"
author: "Vinny Paris"
topic: "04"
layout: post
root: ../../../
---
The easiest one to understand is the instant. That is it happens at one exact point in time, 
if you want to consider it something like a point in a number line. The other three record timespans 
(a length of some form over an instants point).
An interval gives the beginning and ending times for some length of time so an example might be that I was working on my undergrad
at the Univeristy of Maine from August 20, 2012 to May 15, 2016. ( 20-08-2012 -- 15-05-2016 ). The advantage of these is that they 
have no ambiguity.Durations are the amount of time between an interal's start and end by seconds. A period is through non-standard units of
time (day, months, new moons). It should be noted that the lubricate package does report things in minutes, hours or even days but those are 
only for approx. and convience; all objects that are durations are dealt with in seconds.
The periords big advantage is that while duration always produces seconds, occasionally its a lot easier to think in years or months 
and not worry about things like leap year, leap second, how many days or in the month. Instead it bases itself off of an instant and 
works from there. So a Feb 1 + One month will give you March 1 but a duration would be pretty much useless unless you want to convert 
things to seconds.

These distictions firstly allow us to talk to each other about specific points of data analysis and how the data is presented, 
secondly it allows for a lot more easy manipulation of objects dealing with date and time and through that allow for a faster 
cleaner analysis. I've actually had problems with dates in analysis before dealing with inflation rates and it became such a pain to find and 
match days that were six months ahead. Kind of wish I had known about this package/paradigm sooner. I think the big boost is in the ability to 
communicate what is happening in these analysis going back to the idea of literate programming; if I can't read what code you wrote or if I
use 52 weeks in a year vs 365 days things get wonky. Using a duration or an instant + period helps clean that up. 
