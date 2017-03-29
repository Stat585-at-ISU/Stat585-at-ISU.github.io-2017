---
title: "Literate Programming..."
author: "Gaurav Kandoi"
topic: "01"
layout: post
root: ../../../
---

In two papers, written 15 years apart, David L Donoho discusses the challenges and problems related to reproducible research. He also proposes some solutions for these problems. Looking at how computational analysis has changed during these 15 years, it is surprising that many problems still remain the same. The central theme of both papers can be boiled down to the case of reproducibility and credibility. Without reproducibility, the findings of a research holds no credibility. With the abundance of data and computational power, creating beautiful plots, irrespective of whether or not it explains the theory has become a trend. In his 1995 paper, Donoho seems to worry less about the credibility of the work being published. He is more concerned about the research being reproducible by someone in the future. He advocates using the computational setting that is described in the research to generate the graphs, rather than generating something that looks aesthetically beautiful, but doesn't offer the scientific basis behind it to the readers. He recommends making the software and/or the source code used to produce the results available for anyone to use.

Even in the days when literate programming was only beginning to get some push, Donoho's views are in perfect match with that of Donald Knuth when it comes to making research reproducible and accessible to all. My own research often involves analyzing and summarizing big datasets. As such, I often have deadlines to meet and I see myself taking the shortest way to *get* the result. Sometime, I would hard code few things in my scripts or take a shortcut to by-pass an otherwise lengthy step. This has often led me to scratching my head few months later. This usage of shortcuts and/or hard coding is clearly a no-no when it comes to reproducibility. Apart from being reproducible, it is often useless for similar analysis, because things would have been hard coded to specifically produce these results. I'm not saying that the results produced are necessarily wrong, but it sure is really hard to reproduce them.
