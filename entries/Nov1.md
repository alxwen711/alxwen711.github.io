---
layout: default
permalink: /blog/Nov22
---

[link back to all posts](https://alxwen711.github.io/blog)

## November 1st-15th

Welcome back to a regularly scheduled recap of my CodeForces contest shenanigans. I may not have much time for actual practice due to school being extremely heavy right now, but with how much I’ve tanked the last 10 contests, I can’t really go much lower right?
### [Round 833](https://codeforces.com/contest/1748)

Problems Solved: A, B, C

New Rating: **1673** (-43)

Performance: **1540**

Well this was a rough contest back. The main problem here was that I overcomplicated many of my solutions. This was not the case for [Problem A](https://codeforces.com/contest/1748/problem/A), which was done in 2 minutes because I did not overcomplicate things and found the very basic solution.

[Problem B](https://codeforces.com/contest/1748/problem/B) should have been relatively easy since basic thought on the question reveals that any string exceeding 100 characters will never be diverse, thus only a maximum of 100n strings need to be checked where n is the length of the string. This would be 10 million operations, so with optimal Python code, it’s easily solvable in under a second.

What proceeded to happen was a series of blunders from myself overcomplicating my approach. The only problem in my [first submission](https://codeforces.com/contest/1748/submission/180631623) was that it should’ve stopped when it counted 11 of a single digit rather than 10, but what even is going on in this code? I’m keeping track of the last 10 occurrences of each digit, which is completely unnecessary. I know I’m supposed to give more explanation behind my thought process here, but there really is no way to explain it other than overcomplicating the solution. Like, there’s really no other explanation for it. I figured out the 11 v 10 error in my [fifth submission](https://codeforces.com/contest/1748/submission/180643847), and only because I got a WA verdict this time due to simplifying my code. Further basic code optimization in calculating the number of new values and maximum frequency got me the right answer.

There’s actually still more to this mess because in my overcomplicated process, I somehow thought trying to recreate my heavily unoptimized solution in C++, a language I really don’t use, was a good use of 25 minutes. [The results were about as expected: bad.](https://github.com/alxwen711/contestSubmissionArchive/blob/main/codeforces/live%20contests/2022-4/833/b.cpp). It’s here that I bring up a bit of advice from myself several months ago:

_Problem B tends to require more reasoning to figure out the solution, but is best thought of as a "complex Problem A"; usually it is still basic implementation and knowledge of data structures other than arrays is usually not vital._


Basically, it’s Problem B, the solution is probably pretty simple, and stop overcomplicating it.

Normally I would be more aggravated by my attempts on [Problem C](https://codeforces.com/contest/1748/problem/C) but here it wasn’t that bad. The [first submission](https://codeforces.com/contest/1748/submission/180625229) was an aggressive attempt 19 minutes in the contest since B was still giving me trouble, which was a reasonable decision since I saw the problem, knew I could implement an attempt quickly, and went with it. The only issue was that this attempt only considered the first zero in the array.

My later attempts though were something. As a spoiler, this [second submission](https://codeforces.com/contest/1748/submission/180650505) is algorithmically correct but TLEs on testcase 8. I then make 4 more failed attempts to optimise my code which is excessive since one change was desperately swapping from PyPy-64 to PyPy. Spoiler alert, this does not work. But then I figured it out. You may recall the misery that an anti hash table attack caused me. Well I can now give a formal thanks to Beethoven97, for had this not occurred, I would not have solved this problem. My [correct C submission](https://codeforces.com/contest/1748/submission/180653423) is the equivalent of Norton Antivirus on my dictionary setups by xoring each value by a predetermined random value, but it did prevent what could’ve been an abysmally crap ~1284 ELO performance and made it into a moderately crap 1540 ELO performance. 

I guess welcome back? There’s still time for me to return to CM before the end of this year, but I pretty much need to be at my best in each of the remaining contests. Well, may the odds be ever in my favour.


## November 16th-30th

