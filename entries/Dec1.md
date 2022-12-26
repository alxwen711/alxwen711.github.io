---
layout: default
permalink: /blog/Dec22
---

[link back to all posts](https://alxwen711.github.io/blog)

## December 1st-15th


What I forgot to mention from last entry is that finals week happened. Thankfully most of the term is complete. Let’s just recap the two contests I did recently. Also, an end of year recap post on CodeForces will be out soon to describe this “journey”.


### [Educational Round 139](https://codeforces.com/contest/1766)

Problems Solved: A, B, C

New Rating: **1685** (-18)

Performance: **1628**

The good part is that I may have broken my personal record of solving the first 3 problems in a division 2 level contest with an 18 minute completion. [Problem C](https://codeforces.com/contest/1766/problem/C) wasn’t even egrigiously easy and I ran through that like it was nothing. This is where the good part ends because [Problem D](https://codeforces.com/contest/1766/problem/D) was a mess. I had the right idea with using the difference of two numbers and creating a sieve of primes, but the sieve needed to extend to the whole 10000000 range rather than just sqrt(10000000), and there were several other observations missed that would have made my attempt run fast enough. I did reduce the unnecessary wrong submissions on this question, just that my conclusion from the first two wrong submissions that I needed to look for all of the factors in the difference was wrong as a whole.

Overall this contest went okay, but it could’ve been great and I unfortunately blew Problem D after a great start. At least it isn’t “Days of Our Programmers” bad.


### [Round 838](https://codeforces.com/contest/1762)

Problems Solved: A, B, C

New Rating: **1745** (+60)

Performance: **1899**

I find it funny that the contest narrative for this round is nearly identical to the previous round, yet the elo change differs by 78 points. The difference here is that Problems C and D were significantly harder so a fast 3 question solve resulted in a higher rank. [Problem C](https://codeforces.com/contest/1762/problem/C) itself was actually not that difficult aside from it being a reading hell. Once you draw out the problem then the solution is very simple. Unlike last time, I did not complete a working solution on [Problem D](https://codeforces.com/contest/1762/problem/D), there is an idea I have that works in theory, but my implementation of it likely was problematic.

(This post will be updated once I figure out if my original idea on D was right or not.)

Update: [My attempt at D](https://codeforces.com/contest/1762/submission/185369118)

Looking back at Problem D, the method I seemed to use was creating a “cycle” of the n hidden values and checking the gcd between each adjacent pair. Each value will then have 2 gcd values assigned to it (due to having 2 neighbours in the cycle setup), and if the maximum of these values is 1, it can be eliminated as not being the zero. This is because if it was, then the only way both gcd’s are 1 are if the value to its left and right are 1, which is impossible. In addition, values that have both of their gcd values the same can also be eliminated. A new cycle is formed with the remaining values, and the process repeats, except the minimum gcd value for elimination is now 2, then 3, and so on until 2 values in the cycle remain. The issue seems to be that this method requires too many guesses; I used a fail safe line to check if this was the case by having the algorithm guess the first two values remaining in the cycle if no more guesses were needed, and this ended up in a wrong answer.

To those still here, this update was actually posted December 25th since the past week or so has been covered by the last bit of my school term and several days of much needed rest. Merry Christmas, Happy Holidays, or happy New Year’s Eve’s Eve’s Eve’s Eve’s Eve’s Eve if that’s your thing.

## December 16th-31st

