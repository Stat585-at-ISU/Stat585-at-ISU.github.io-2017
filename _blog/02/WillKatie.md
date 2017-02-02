---
title: 'Blog Post 2: Split-Apply-Combine'
author: "Katie Will"
date: "2/1/2017"
---

The functions I know that support the split-apply-combine strategy are apply, lapply, and sapply in base R. I have also used aggregate some, but not much. In my experience, these have always been efficient for what I was doing. I do wonder, however, how much more efficient plyr functions would be with some of the larger data sets I have worked with in the past; data sets with 1/2 to 1 million rows. When I can't figure out how to use these base R functions, I always default to a loop (I believe that my first ever computing class, on JAVA, has something to do with that). In my undergraduate research which dealt with 3-D data, this took some time. I remember thinking then that I could write my code more efficiently, but the learning curve was steep at the time. 

We could use the split-apply-combine strategy with the temperature data we have been using in class. For a small example, we could find the temperature averages of each month for every station. In the lab, my group used apply to accomplish this for one station. It worked well for one station, but for the data set combining all stations, plyr functions would definitely be more efficient and easier to work with. 

