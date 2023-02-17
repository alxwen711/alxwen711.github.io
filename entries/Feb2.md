---
layout: default
permalink: /blog/Feb23
---

[link back to all posts](https://alxwen711.github.io/blog)

## February 1st-14th

### [Round 848](https://codeforces.com/contest/1778) 

Problems Solved: A, B, C?

New Rating: **1860** (+25)

Performance: **1924**

Congratulations, my performance on this contest has just won the “Luckiest Contest Award of 2023”. There may be 10 more months in the year but I’m pretty confident this contest has already won this award. First off, I ended up gaining rating even though my progress on [Problem D](https://codeforces.com/contest/1778/problem/D) was equivalent to brute forcing the expected total values. You can argue that I had a dp solution in theory since I figured out the expected number of operations but I did not really have a practical idea as to how to implement my solution since it required finding infinite sums. Not to mention that it might have been an O(n^2) solution as well.

Part of the reason I gained rating was because of [Problem B](https://codeforces.com/contest/1778/problem/B). The question itself was pretty fair difficulty wise in theory. The real issue is that this might be one of the most confusingly written problems I’ve ever looked at. I think part of the issue was that usually when an array satisfies a specific constraint it would be called “good” and it was weird having it the other way around. Normally taking 18 minutes to solve B for me isn’t ideal, but it just happened that this was very fast for this contest.

Then there is [Problem C](https://codeforces.com/contest/1778/problem/C). Honestly, I’m not really on board with C being a brute force problem. You could argue that the brute force solution requires knowledge on runtime since the worst case would take O(xn), where x is 10 choose 5 = 252. Normally I’d have preferred some sort of more algorithmic based question in C; you could argue that the difficulty comes from being able to iterate through the combinations, but Python as `from itertools import combinations` to trivialize this issue. Hence why I solved this problem in 19 minutes and gained rating solely from being fast.

But, it gets better. Before the main tests, my solution took 561ms. I thought this meant that my solution was easily fast enough to pass the 2 second time limit since pretests usually have a few tests that use the maximum constraints possible. Turns out the 561ms time was incredibly weak because after main tests, I (luckily) passed main tests with *four* milliseconds to spare. Yep. 4ms. A 2 second time limit, and my solution took 1996ms. Turns out the O(252n) test wasn’t even used in pretests and was instead the final 28th test. To say I had incredible luck is an understatement.

It still does not end there. [Here](https://codeforces.com/contest/1778/submission/191574531) you can see the questionably implemented solution I got accepted:

I actually got my first successful hack. And it’s on myself. In `score()` where I was evaluating each possible combination, I had an O(n^2) method being used to create the lookup table for the characters that could be changed. Normally this isn’t a big deal since there were only up to 10 unique characters in each test case, so a difference between 100 operations and 15 operations wouldn’t be that bad. This does not take into fact that there could be up to 10000 testcases in a single testcase. Inexplicably, it seems like there was only one actual main test used to try and test the time limit which involved 1000 test cases of 100 characters each. All I had to do was increase the test case count to abuse the O(n^2) method, and just like that, I TLEd my own solution. To top it all off, uphacking is restricted to CM and above. I had dropped to Expert, but the previous contest at this time was rolled back for plagiarism checks, so I had CM status by 2 elo points which allowed for this uphack. Unbelievable. In short, my solution was correct but the sloppiness in implementation went hilariously unpunished. An absolute miracle.

It turns out that even with my sloppy execution, basic cleanup still results in TLE on additional test cases. The real slowdown ended up being from my over reliance on dictionaries. It seems like even though dictionaries are O(1) access in theory, even without hash collisions they are still significantly slower than basic array lookups, and this proved to be the difference in my later [upsolve](https://codeforces.com/contest/1778/submission/192231607). Best part is that you can see the test case to self hack myself as test case number 37. The changes made sped up the program by about 4.5 times, and there is still another dictionary that can be removed for significant speed improvement.


### [Round 851](https://codeforces.com/contest/1788) 

Problems Solved: A, B, C

New Rating: **1863** (+3)

Performance: **1870**

My run on this contest felt very mediocre. It’s one of those contests where I didn’t really have much of a clue how to do [Problem D](https://codeforces.com/contest/1788/problem/D) (the most progress I made was trying to determine some sort of dp, but I had no clue where to begin), but I ended up completing [C](https://codeforces.com/contest/1788/problem/C) and the problems before it in about 30 minutes. This is also reflected as the gap between C and D in solve rate made this somewhat a SpeedForces contest. Partial underwhelment likely came from the fact that the first 3 questions were mainly constructive problems where I found the solution relatively easily, but then the dp problem was one I felt I should’ve had better chances on. This also marks the third contest in a row without a A-D completion which is something I have to be consistent at to even think about reaching CM. It is still decent in that I’ve been very consistent over the last month or two, but this is at the expense of marginal improvement in skill cap. In the meantime, ICPC contests are coming up soon, and much of my practice recently has been more focused for that. There are key differences in the two contests that are worth noting that I’ll touch upon in the next recap after our team has competed at regionals.


## February 15th-28th

