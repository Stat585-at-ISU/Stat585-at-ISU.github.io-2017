---
title: "Split-Apply-Combine..."
author: "Vinny Paris"
topic: "02"
layout: post
root: ../../../
---
I have used aggregate and subset to some extent in R. Honestly I'm still not sold on plyr's filter over base
subset since there doesn't appear to be a huge gain in effeciency. But I am a fan of the ply functions from the little I used of them. Also, I never realized the naming convention beofre now. I always thought the letters were just some random not useful 
techincal thing, not the I/O formats. I'm really glad I learned that :) I'm really honestly not that familiar with any base R
that does well with combining outside of cbind() and rbind(). As such, I think the base alone is pretty inadequate.

For data that benefits from this would actually be data from the World Fact Book ran by the CIA. I used it in my undergraduate
for a project and the cool thing is it gives you a lot of economic variables (the class was an econometrics course) but the issue was
that there were a lot of variables that I needed to derive out of the data (long term growth rates of gdp per capita 
took mulitple steps to find). So for example you might want to find energy production per person relative to the average of the 
OECD nations. You could break the data set into countries and then from there find their populations and energy production 
levels. Then find the ratio of these numbers. Also, we will want to find the subset of all nations that are in the OECD and find that
group average. After that we can subtract if off of the ratios we found earlier. Then we can add it back into the orgianl data so that it
can be used in analysis against other variables. 
