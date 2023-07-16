---
layout: default
permalink: /blog/Jul23
---

[link back to all posts](https://alxwen711.github.io/blog)

## July 1st-15th

It’s the second half of 2023, and outside of CodeForces, there has been updates on my life. Mainly that I have been accepted into my first ever co-op position with Global Relay. I’m very excited and greatly look forward to this new opportunity to apply my learnings in this competitive programming journey to a meaningful real world use. Don’t worry though, this journal log will continue though during my co-op, because I enjoy these sort of problem solving challenges, and looking back, the depth of DSA knowledge I’ve learnt from these contests were one of the key factors in me being accepted to this position. To top it all off, I am also on an incredible streak in CodeForces. I’ve broken the 2100 Master threshold, and my last 5 contests have all been at least 1900-rated performances or higher, an all time longest streak. Surely I’m excited to keep this momentum going.

Yeah, that last part of the paragraph was a really bad transition. If only the contest in this log actually went that well.

### [Round 884](https://codeforces.com/contest/1844)

Problems Solved: A, C, D

New Rating: **1955** (-176)

Performance: **1064**

[Days of Our ~~Lives~~ Programmers theme, if you want it for your enjoyment or my schadenfreude](https://www.youtube.com/watch?v=98T3PVaRrHU)

No, I won’t bring the dramatic ***Days of Our Programmers*** monologue for this recap, much to the chagrin of anyone reading this. This contest really was a combination of a catastrophic misplay that was amplified by some sloppy execution in C and D, but also really bad luck.

First, the catastrophic misplay, ie. [Problem B](https://codeforces.com/contest/1844/problem/B) the question that started this disasterclass. The initial start of the problem is simple; I saw that the MEX value of a subarray depended on its values, and that if it contained values 1 to p-1 but not p, the MEX is p. Thus I made a sieve to determine the possible prime values.

It turns out that by this first step I was already dead lost. I made about 8 attempts on this problem to no avail, mainly due to the fact I didn’t find that `2 4 1 5 3` is another optimal primality setup for n = 5. The answer for this problem is really just infuriatingly simple.

<details>
<summary>A run down of B’s solution</summary>

If n <= 2, the order doesn’t matter (obviously). Otherwise, place 2 and 3 at the ends and 1 dead in the center of the array. Done.

Yep. The solution to B can be explained in half the required characters of a tweet. I can understand how placing 1 in the center is best due to how quadratics work, but as for how MEX = 5,7,11 does not have to be considered still baffles me. I’ll just let the [tutorial](https://codeforces.com/blog/entry/118128) directly explain here.

*note that we don’t even need to sieve for primes!*

I have no words on this final line.

</details>


With this question, I pretty much burnt the first half hour on it, and then about the last 70 minutes on it in futility. That said, C and D didn’t really help either. [C](https://codeforces.com/contest/1844/problem/C) had 2 failed attempts due to myself screwing with my dp ideas for solving the problem, and it turns out my first attempt on [D](https://codeforces.com/contest/1844/problem/D) was already sufficient (somehow.)

<details>
<summary>Why I resubmitted D</summary>

The example cases somewhat display this, but the important rule is that in the row-major order, two of the same character cannot be x units apart, where x is a factor of n and `x != n`. In an example like `abcba`, the a’s are 4 units apart, and this is a valid string since the factors of 5 are just 1 and 5. The more optimal method for generating the string with fewest distinct characters is to find the smallest natural number x that is NOT a divisor of n, and to cycle through the first x chars of the alphabet for the whole string. This is optimal because if we were to use x-1 unique chars, either we have two of the same char with a gap under x-1, or we repeat the chars in order to get many gaps of x-1, both of which would divide n by our definition of x. This is what I did in my second attempt.

What I did in my first attempt was to find all the factors of n, and then when adding in each new char to the string, I checked with each char several indices back relating to these factors to make sure no violations occurred. This somehow clears in under 2 seconds, the issue here is that n can go up to 1000000. A such problem case is in the highly divisible number 720720, which contains 240 factors. With some rough calculations, this could result in about `240 * 720720 = 173 million operations`, which should not be possible in Python assuming about 20 million calcs/second. This does slightly overestimate the operation count but I did test this on my own computer and it took about 20 seconds, so I have no clue how it is tenfold in pace on the judging machine.

</details>

That said, I at least solved C and D, which is also why this didn’t end up as a drama episode despite the satrically large rating loss. Solving A/C/D would place me above everyone that got A/B/C, even with the large timeloss from initial B attempts, but I ended up losing to several people with only A/B/D solves. It distracts from the bigger issue that a lot of people happened to solve C and D. It may have been a Div 1 + 2 contest, but 36% of competitors solving D is extremely rare. I could’ve made an attempt at E but that wasn’t much better since while 5600+ solves were on D, E only got 422 solves. The problem rating gap between D and E is expected to be around 1000 points, with D being rated 1350 and E about 2350. So you get the perfect storm of a collapse on B, bad execution on C and D, and a difficulty curve that really did not help me.

By all of this, it does mean that my run on this contest, while definitely atrocious, doesn’t feel like my worst underperformance. It just happens to have a -177 rating change, which is bad, but I’ve recovered from this. 



## July 16th-31st

