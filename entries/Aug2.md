---
layout: default
permalink: /blog/Aug23
---

[link back to all posts](https://alxwen711.github.io/blog)

## August 1st-15th

Yep, it’s time for another quality recap of codeforces contests.

### [Round 890](https://codeforces.com/contest/1856)

Problems Solved: A, B, C, E1

New Rating: **1973** (+21)

Performance: **2014**

Statistically, my performance here was mediocre. [Problem D](https://codeforces.com/contest/1856/problem/D) was legitimately harder than [Problem E1](https://codeforces.com/contest/1856/problem/E1), and I have to give credit to the contest setters for this contest had one of the most balanced difficulty curves, which is impressive considering the last problem was in multiple parts. Overall pace was okay, nothing out the ordinary, but I was still relatively capped out by the harder problems.

That said, [Problem C](https://codeforces.com/contest/1856/problem/C) was a glorious act of revenge. 

<details>
<summary>Ha ha ha. I got C.</summary>

To quote a rant in a very recent log entry:

_RUN O(N) TESTS TO BINARY SEARCH THE ANSWER. This pattern has shown up OVER and OVER again and for TWO hours I did not even bother considering it. It’s one of the most fundamental patterns in these problems, and shows up nearly every contest, and I decided that going for an approach that is `O(way too long)` was a better solution. And look where I am now. I’m basically back at the same level as the start of the year, hell even the summer of last year. This is a wakeup call. The last thing I want is another failure in October’s regionals, but repeating these blunders and idiocy is simply insanity. Actually goose egging a contest. What a bloody joke._

Let’s just say the wake up call happened here. The LT Binary pattern (Linear Trial Binary, that’s what I’m calling it now) was used for this solution. It took me a while to figure out, but if we assume that the maximum possible value is `x`, then a maximum of `x-1,x-2,x-3…` are all attainable. The challenge is determining if a such maximum is possible, but for this you can attempt to make each value in the array the maximum. Due to n being at most 1000, such a $O(n^2 log n)$ solution can work. Then to determine the minimum number of operations needed to make index i value x or higher, it goes as follows:

Suppose c is tracking the total operations needed. Add x-ar[i] to c, then check if the next value would’ve needed increasing to make this move work (ie. check if ar[i+1] >= x-1). If so, then add the required ar[i+1] operations needed and then check if ar[i+2] would need additions. Repeat until c is determined or you require ar[-1] to be increased; in this case, making ar[i] = x is impossible.

[solution link](https://codeforces.com/contest/1856/submission/217306814), `inc` tests a specific value in the array if it can be equal to x, `f` just runs `inc` on each element in the array, and `b` is the binary searching mechanism. Anyways, please excuse me as I celebrate that I got my revenge on a LT Binary problem.

</details>




### [Round 892](https://codeforces.com/contest/1859)

Problems Solved: A, B, C, D

New Rating: **2064** (+91)

Performance: **2299**

I won the first half of the contest! Then [E](https://codeforces.com/contest/1859/problem/E) happened which was kinda unfortunate. I first solved it if only at most 2 segments could be used, then solved it if the segment had to be a contiguous range. Both used a contiguous dp so I sort had the right idea, but couldn’t see how to optimize it from some $O(n^3)$ ideas I tried. A-D though in 1 hour, and A-C in particular in 17 minutes is exceptional pace. This sort of rating gain based on fast A-D with constantly missing E as skill cap might be somewhat unsustainable, but it’s still solid rating gain for an overall solid contest.


<details>
<summary>D thoughts</summary>

The idea of [D](https://codeforces.com/contest/1859/problem/D) is that some of the portals could connect to each other, for instance, a portal where you enter through [1,6] and exit through [4,5] can connect to a portal where you enter [5,12] and exit [9,11]. You want to track the minimum required position to be able to use the portal sequence to reach a further point. In this case you can track that as long as your position is at least 1, you can use the portals to reach 11. Eventually you will have several of these pairs of min entry points and maximum portal exits, for which you then use binary search on each starting pos to find maximum position. Note that using no portals is also an option, above example a starting position of 12 is a case of this.

There is one more part to consider in this for implementation, being how to know that for a given minimum entry point, you are reaching the absolute furthest point. What I did here was to keep all of the reachable unchecked entry points for a given segment chain in a heap structure. I would then check if the current entry point of the given segment is lower than the given portal segment, and if so, remove it from the heap to take the next segment to the right for comparison. Only when no segments remain in the heap do we know the furthest point has been reach, meaning we can create a new portal segment.

[Solution link](https://codeforces.com/contest/1859/submission/218547795)

</details>
### [Round 893](https://codeforces.com/contest/1858)

Problems Solved: A, C, B

New Rating: **1998** (-67)

Performance: **1786**

This is what I meant by my previous gains being unsustainable. There is the small caveat that I mainly lost rating because I spent half an hour on [B](https://codeforces.com/contest/1858/problem/B) before noticing that [C](https://codeforces.com/contest/1858/problem/C) was much easier, but blaming this is a pitfall. Firstly, this is more just bad strategy on my part; if B is 1250 points and C is 1500 points, it implies that their difficulties *should* be similar and I should’ve checked both of them first before running head first into B. Secondly, B only took that long with a wrong submission because I had very sloppy implementation. And lastly, all of these mistakes would have been negated had I solved [D](https://codeforces.com/contest/1858/problem/D). For this I’m still trying to upsolve it, and the plan is to start the next entry with how exactly this problem works.


## August 16th-31st

