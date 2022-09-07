---
layout: default
permalink: /blog/Sep22
---

[link back to all posts](https://alxwen711.github.io/blog)

## September 1st-15th

As of posting this, I’ll be back to school in a 6 course term. This means that my time for competitive programming in the next four months is limited at best, and with the “contest” that occurred at the end of August, I need to make every contest count to return to CM (1900 ELO).

### [Round 818](https://codeforces.com/contest/1717)

Problems Solved: A, B, C, D

New Rating: **1880** (-3)

Performance: **1868**

I’m not sure if I’m being too hard on myself, or it’s been a poor mentality I’ve recently been having, or both, but even though this is statistically the 8th best contest I’ve had, I’m still not happy with this result. Yes, I solved A through D, but [Problem C](https://codeforces.com/contest/1717/problem/C) should not have taken 38 minutes to solve. The 38% clear rate it had puts it on the easier end of C problems, and I spent an egregious amount of time stumbling by overcomplicating my attempted solutions. Mainly, I was trying to find how to turn array A to array B when what I should’ve been doing was determining if it was possible to turn array A into array B. These two ideas are clearly different. For instance, if I asked you to determine if `987.83979*202.100971503 > 1000` is true, you would use common sense/basic estimation to determine that the answer is “yes”. What you would not do is manually take out a piece of paper and start creating abstract art in the name of “common core multiplication” to determine the exact value, then compare that to 1000. Solve only what the problem requires you to solve.

Then we go to [Problem D](https://codeforces.com/contest/1717/problem/D). I’ll give credit to myself for figuring out the solution because noticing how Pascal’s triangle is involved with this problem is actually well done. I’ll also excuse myself for the unsuccessful hacking attempt I desperately made since the benefits of potentially passing 92 other coders was worth the risk of dropping 32 places. What cannot be excused is how I had 4 wrong submissions for this problem.

*Note: originally I was going to excuse the first wrong submission because I was unsure why it inexplicably failed on test case 8. It is now 6 hours after the contest and put simply, I’m just sad now. The next paragraph may contain excessive amounts of salt.*

The [first submission](https://codeforces.com/contest/1717/submission/170630493) fail can be described as follows:
```
Let a = 2, b = 5, c = 3
My line of code: a = a + b % c

What I assumed would happen:
a = (2 + 5) % 3 = 7 % 3 = 1

What ended up happening:
a = 2 + (5 % 3) = 2 + 2 = 4
```

Yeah, instead of failing due to not being able to count to five, now I only failed due to 7th grade mathematics. I assume that’s when modular arithmetic is introduced. Oh but wait! What about the other wrong submissions? [Number 2](https://codeforces.com/contest/1717/submission/170633298) I thought my factorial algorithm that I took directly from my [competitive library](https://github.com/alxwen711/pythonCompetitiveLibrary/blob/main/algorithms/math/combinatorics/fermatCombinatorics.py) was bugged so I increased the memory allocated for no reason, EVEN THOUGH I already did extensive testing to confirm the algorithm was accurate. [Number 3](https://codeforces.com/contest/1717/submission/170634542)? Oh boy. I fixed the modulo error unknowingly and reverted the edit from the second submission, but OH BOY WHAT DID I REPLACE THE LINE WITH???

`arLen = max(n+k)+3 #array length`

Wow. I guess now we’re imploding on basic aspects of Python now. Note that if I had ran the program on the 3 given pretests this would have been caught, but instead I lost 50 more points for failing a pretest that is literally visible in the problem description. You think I’d realize this after seeing “Runtime error on pretest 2”, but nope. For [submission 4](https://codeforces.com/contest/1717/submission/170634783), what did I think the error was??? I thought `print(ans%m)` wasn’t working properly. Now excuse me while I go scream at this disaster class in a corner somewhere.

Okay I’m done screaming. Here’s the real kicker behind the Problem D disasterclass:

- I ended up with 3676 points at the end of the contest, landing me in 668th place with an 1868 ELO performance.

- 1088 of those points came from Problem D.

- Had I not made the modulo blunder, I would’ve had a successful submission for D 1:18 in the contest, netting me 1376 points.

- Furthermore, I would not lose an additional 50 points because the hacking attempt I made was one out of desperation to reach a performance level just good enough to reach CM.

- Thus, the blunder cost me 338 points and had it not happened, I would finish this contest with 4014 points.

- 4014 points would equate to 380th place, an approximate performance of 2004 ELO (1709 base + 82 net gain * 3.6)

- A 2004 ELO performance would’ve given me about a 34 ELO gain bringing me to 1917 ELO.

- Even if I made that first wrong submission, had I corrected it on my second attempt, I would still be at 3936 points -> 443rd place -> 1966 ELO performance -> 23 ELO gain -> 1906 ELO -> Still CM

Agony, thy name is 7th grade modular arithmetic.

### [Round 819](https://codeforces.com/contest/1726)

Problems Solved: A, B, C

~~New Rating: **1870** (-10)~~

~~Performance: **1840**~~

*EDIT: It turns out Problem F was copied from a past contest, so this entire contest is unrated. At least I didn’t lose rating?*

Contests like these are why I was so mad over how rubbish I performed on the previous round. In the previous round, Problem C was a greedy problem where the induction step was the main challenge, and Problem D was a combinatorics problem where my success depended on finding a pattern. Both of these questions played directly into my strengths, so I should’ve been able to reach CM. 

For this contest, [Problem C](https://codeforces.com/contest/1726/problem/C) was solved mainly due to luck. My solution that involved counting the number of “()” in the sequence was me throwing ideas randomly. I did not even bother trying [Problem D](https://codeforces.com/contest/1726/problem/D) because I found [Problem E](https://codeforces.com/contest/1726/problem/E) more approachable. D was a graph/tree problem that took me 10 minutes to understand the problem statement, and even after that I had no clue how to begin. E turned out to not be much better as one of the problem tags for this question was fast fourier transform, something I still have no clue of. My attempts at E involved finding the answer for small n values to create some sort of pattern. For 2 to 9, I got `[2,4,12,32,100,312,1076,3772]`. I suspect there is some sort of recurrence relation here but I could not find it. I have attempted this sort of method of brute forcing small n values to see a pattern before with mixed success, but here I feel this idea may have been a pitfall. I also attempted to find some sort of dp method for E but nothing was found.

With C being a lucky solve, D being a graph problem, and E requiring a technique I have no clue of, this contest was better executed than the previous one. Yes it was worse overall, but my only mistakes were a slow B solve and rushing my first attempt on C. It still hurts though that I’m only ~~30~~ 20 points away from CM, but with school starting tomorrow (September 7th), it feels so far away.

This blog was posted a week early, mainly due to the fact that there are no more contests coming in this two week period. I am starting classes at SFU again, 6 in fact. You can still expect frequent activity on other Github projects I’m working on as well as the rating post sometime at the end of this month. Alas, my goal of returning to CM by the end of this year is significantly harder now due to fewer contests and having much less time than normal to prepare. 


## September 16th-30th

