---
layout: default
permalink: /blog/May22
---

[Link back to all posts](https://alxwen711.github.io/blog)

## May 1st-15th

Well then, congratulations to myself (sarcastically) for actually beginning this post in the same month this post is supposed to recap. I can finally say that this blog will be updated on a more consistent up-to-date basis now that the Spring 2022 SFU Term is finally behind me. There isn't much else to talk about other than the two contests that took place in these two weeks because after April 26th, being my last final exam of the term, I could completely chill and relax for a few weeks until the summer term started. There was absolutely nothing else that went wrong within those past few months.

![ah. forgot about that.](/docs/assets/images/googlecodejam2020.png)

As it turns out, in the last few weeks as of writing while I was scrambling to update this blog's March and April posts, I forgot about a little known competition that I participated in known as [**Google Code Jam**](https://codingcompetitions.withgoogle.com/codejam/schedule). For those unaware, this is one of the largest individual competitive programming competitions hosted by Google. When you combine my recent CodeForces successes and the fact that much of last month was a courseload dumpload, it becomes more apparent why I made the mistake of not preparing that much for this competition. This led to me barely missing entry into Round 2 by finishing Rounds 1B and 1C in the top 2000 contestants, but just outside of the top 1500 that would advance from each sub round. I actually scored enough points in each sub round, but ended being too slow to move on, either because I had too much of a penalty from wrong submissions, or because in my infinite wisdom, I did Round 1C in a sleep deprived state at 2am. There were only 3 questions in each round, making the skill gap between each question huge and put simply, Round 1 of Google Code Jam was a severe case of "SpeedForces", ie. the faster, not better, coder wins. Yes, I am still salty over being just short twice. As for the problems themselves, they are best left to the editorials put out by Google as with so few questions in each round, the questions I can recap are either relatively easy or ones I don't completely understand how to solve, let alone begin.

As it turns out the Google Code Jam debacle was arguably still the most interesting contest I took part in in terms of how I did. There were two CodeForces contests in these two weeks, and looking back at them at the start of June, they can be best summed up as decent. [Round 788](https://codeforces.com/contest/1670) saw myself getting Problems A through D correct on a relatively easy contest, and [Educational Round 128](https://codeforces.com/contest/1680) saw me get Problems A and B correct very quickly, only to completely implode on a much harder [Problem C](https://codeforces.com/contest/1680/problem/C) immediately afterwards. [My last submission](https://codeforces.com/contest/1680/submission/157073407) was only able to be a working O(n^2) solution when linear time was required, and I'm still not exactly sure of how to properly approach this question.

There wasn't much of a rating change from these contests but one other thing I would note is my method for solving [Problem D in Round 788](https://codeforces.com/contest/1670/problem/D). This is a case where a programming question can be pretty much solved with only math and not much actual coding work. The way I solved this was by taking a hexagon grid, and simply trying to make as many triangles as possible using 1 line, then 2, 3, 4, and so on. This gave me the sequence 0, 2, 6, 10, 16, 24, 32. This is where the online resource [OEIS](https://oeis.org) comes into play, as my guess was that this sequence of numbers had some sort of pattern. I had used OEIS before to figure out a programming problem where the solution ended up involving the Catalan numbers, so I assumed this would be a similar case. It turns out the sequence above does not show up in OEIS, but since all the values are even, I tried 0, 1, 3, 5, 8, 12, 16. This sequence ended up being f(x) = floor(x^2/3) and through some basic algerbraic manipulation I came up with this humorously short solution for a normally complex problem:

```python
import sys
from math import sqrt
from math import ceil
 
for i in range(int(sys.stdin.readline())):
    n = int(sys.stdin.readline())
    x = (n+1)//2
    ans = ceil(sqrt(3*x))
    print(ans)
``` 

In other news, I begin the SFU Summer Term with seeking for a co-op position and one writing course in the form of CMPT376W. Seeing that I'm writing this at the start of June, I can say that my plan to have only this one writing course reserved for its own term was a good one as the course is a lot of reading and writing. I know that sounds expected, but it was a welcome change considering that the last actually proper English course I took was back in high school. There's not much else to recap on in these two weeks so let's just go to the second half of May.

## May 16th-31st


