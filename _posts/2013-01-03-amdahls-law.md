---
layout: post
title: Amdahl&#39;s Law
---

![Example of the law of Amdahl](/img/amdahls-law.png)

Consider a process (represented by the topmost bar in the picture) consisting of two sequential parts. The first one (red) takes 70% of the time of the whole process, and the other one (blue) takes the remaining 30%. In order to make the process faster, you might have decided to work on optimizing the blue part. However, given the limited time of the blue part, it turns out that even making it 3 times faster would only bring an overall speedup of 20% to the process. Conversely, it may be esasier to work on the red part to make it 2 times faster, obtaining a total speedup of 35%.

Amdahl's law is a model used to quantify the maximum expected performance gain that can be obtained by improving only some parts of the system. The law states that the overall improvement of a system is limited by the time the improved part is used.

In conclusion, normally it is better to improve the most frequently used parts than make enhancements to rarely used parts.
