---
title: "Working with date and time"
author: "Akshay Yadav"
topic: "04"
layout: post
root: ../../../
---

Given data may frequently contain information about when a particular event occurs. Examples include  time length of each call that is received by a call centre or the release date of a movie in the movies dataset. This time information can be encoded in form of an "Instant" which could be an exact date or time at which the event in the data occurs. The span of time between two instants is called the "Interval". An interval will require an exact start and end time instant.

The time information can also be presented in form of "Duration" without information on exact start and end instant of the event in the data. Durations are generally in seconds but can be changed to other units of time measurment. "Periods" are durations with larger units of time measurement like, days, weeks or even years.

These distinctions can help us to uniformly represent the time and date related variables in the data with various levels of precision. Variables that represent time instants can be used to calculate time intervals which may be easier to work with and more informative. Durations and Periods could be inter-converted as required. 
