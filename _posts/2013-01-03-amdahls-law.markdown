---
layout: post
title: Amdahl&#39;s Law
---

Amdahl's Law is a model used to quantify the maximum expected performance gain that can be obtained by improving only some parts of a system. The Law states that the overall improvement of a system is limited by the time the improved part is used. In other words, as you can see in the following example, it is better to improve the most frequent case than to make enhancements to rarely used parts of a program.
<img class='image' src='/images/amdahls-law.jpg' width='610' height='256' alt='Amdahl&#39;s law'/>
Consider a task consisting of two sequential parts, where, the purple one takes 70% of the time of the whole computation and, the blue part, the remaining 30%. By working hard, one may be able to make the blue part 3 times faster, but this only reduces the time for the whole computation by a 20%. In contrast, one may need to perform less work to make the purple part be twice as fast, obtaining a speedup of 35%.

<p class='references'>References:</p>
<p class='reference'>Wikipedia.org. http://en.wikipedia.org/wiki/Amdahl&#39;s_law</p>
