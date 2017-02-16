---
title: "Working with date and time"
author: "Aaron Baker"
topic: "04"
layout: post
root: ../../../
---

#####Instants, Intervals, Durations, and Periods

An instant is an exact time point referenced within the package lubridate. That is, a single time point. Intervals on the other hand have an end and start period associated with them. That is there is a 'from' time point and a 'to' time point. Durations refer to a __length__ of time recorded in seconds, whereas periods are __lengths__ of time recorded in a time measure larger than seconds, like years. 


#####(Why) do we need these distinctions?

It seems clear that these distinctions are very useful, and natural. Clearly, we need to be able to reference individual time points and also to reference intervals of time whether they are with respect to a certain date/time range or just a quantity of time (duration or period). These provide an appropriate syntax 'plain english' language for what we are attempting to do, which is great.

One point of the great advantage of lubridate is that it makes it simple to work with. Having worked with dates personally before, I know for a personal fact that translating date and time can be quite painful, even if different UTC codes aren't involved. Simplyfying the process for this provides a great advantage when these situations come up.

