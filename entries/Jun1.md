---
layout: default
permalink: /blog/Jun22
---

[Link back to all posts](https://alxwen711.github.io/blog)

## June 1st-15th

Much of these two weeks saw myself mainly preparing applications for a potential co-op next semester, so I was only able to participate in one contest this time. However, this one contest is a blatant indication of my weaknesses in competitive programming.

### [Round 798](https://codeforces.com/contest/1689)

Problems Solved: A, B

New rating: **1625** (-52)

Performance: **1458**

The only reason this contest wasn’t a catastrophe was because I solved the first two problems quickly. What proceeded to follow was 100 minutes of Alex Wen suffering on yet another problem involving trees. [Problem C](https://codeforces.com/contest/1689/problem/C) is one of many cases with tree problems where I understand how to solve it, but struggle with implementing the solution. The optimal “tree pruning” involves only cutting nodes directly connected to the most recently infected node. If the most recently infected node has two children, then the child that would “save” the most vertices in the short term is cut, and the process repeats with the other child being the newest infection. Otherwise, there will be no further infections. This pruning method is exactly the same as the one presented in this contest’s editorial, except there is a dp method used to determine the prune sequence in reverse order. All of this I had figured out in contest, but I had no idea how to implement this solution in linear time. From this failure, the simple plan to fix this weakness was to upsolve this problem in the coming days and practice further tree-related problems on LeetCode.

This plan then proceeded to stall out when I contracted COVID on June 15th. I may have contracted it earlier given that I began having a dry throat around June 12th. It took until June 22nd for me to finally recover, and to top it all off, I have several applications to finish by June 26th. It’s June 23rd today, and all I really have is a template resume. The upsolving for this question will happen but it will have to wait since I intend on fine tuning a specific resume for each position. Codeforces Global Round 21 is also a contest I intend on participating in, mainly for experience, as it is on June 25th. Pray that a tree problem doesn’t screw me over in that contest as well.




## June 16th-30th

Before I begin this recap, I’d like to bring attention to the [Google Sheets page tracking my CodeForces progression](https://docs.google.com/spreadsheets/d/1aQObaGKSDEtilQrLuxFZ6-naW-EMjr4uTE5LnnNn6tY/edit?usp=sharing). I have updated the sheet with a new section where I’m keeping track of how many people solve each problem on each Division 2 level contest. This sheet will be used as part of a larger separate post that will likely be crossposted to CodeForces explaining how exactly its’ rating system works and how to use that knowledge to set goals for improvement. In addition, the [second March post](https://alxwen711.github.io/blog/Mar22) has been updated as the values used in the clear rate table were previously arbitrary values.

### [Global Round 21](https://codeforces.com/contest/1696)

Problems Solved: A, B, C, E

New rating: **1668** (+43)

Performance: **1794**

The entire section from my Round 798 recap aged impeccably here, except the topic of trees can be extended to graph problems as a whole. Problems A and B were simple questions done in the first 15 minutes, but [Problem C](https://codeforces.com/contest/1696/problem/C) actually took 38 minutes to complete. The trick for C is to notice that the actions for expanding and contracting the array are reversible, and that you are not restricted to finding a sequence of moves to turn array *a* into array *b*. If you can manipulate both arrays using the actions given so that they end up equal to each other, that is enough proof to show array *a* can be turned into array *b*.

[Problem D](https://codeforces.com/contest/1696/problem/D) and [Problem E](https://codeforces.com/contest/1696/problem/E) was where my contest strategy came into full effect. I would normally attempt D for the remaining contest time, alongside most other coders. After all, it’s usually a given that the questions in this contest are arranged in increasing difficulty. However, for this contest, notice that D and E were both worth the same 2000 points. This is a sign that the difficulty gap between these two questions will not be very large, if it is even noticeable. The post contest statistics back this up, as while 1621 people solved D, 1114 people solved E, which is not a significant difference. Lastly, a brief look at E made me determine it was some sort of mathematics/combinatorics related problem. Even though D is slightly easier than E, I knew I had much better chances of solving E. This risk of attempting a “harder” problem rewarded me with my first ever Problem E solve on a CodeForces contest, not including Division 3 contests. This is also the first time I actually solved a problem in the final 15 minutes of a contest, which feels good since I have had several instances of myself coming close to solving a problem, but then running out of time.

### [Round 803](https://codeforces.com/contest/1698)

Problems Solved: A, B, C, D

New rating: **1708** (+40)

Performance: **1819**

This was the first contest I’ve participated in where [Problem A](https://codeforces.com/contest/1698/problem/A) was worth only 250 points. The solution for Problem A is quite literally printing out *any* single value from the array. Combined with the contest for some reason having 7 problems instead of the normal 5 or 6, it gave me the expectation that Problems B to F would be easier than normal and Problem G would take the role that F normally does as an “endgame” problem.

My assumptions were correct for Problems B through D, as the first four problems all saw high clear rates. [Problem D](https://codeforces.com/contest/1698/problem/D) in particular had a 17.7% clear rate in competition, the highest in any Division 2 level contest I have participated in so far. The reason for this high clear rate actually had nothing to do with the solution to the problem itself, but rather the constraints of the question. The question uses an array of up to 10000 numbers, and the goal is to guess which value in the array hasn’t been swapped. To do this, you are given 15 queries to ask for information about the array. If the number of queries given was something normal sounding like 50 or 100, then the solution would be less clear, but with such a specific number like 15, it gives an important clue. 2^14 = 16384, meaning that with the array size constraint, a binary search method will be able to find the correct value with 1 query to spare for leeway. This observation was the hint that allowed this question to be easier than intended.

The easier than normal questions ended at [Problem E](https://codeforces.com/contest/1698/problem/E). This was the point when the contest went from over 2500 people solving Problem D to under **200** people solving Problem E. This wasn’t a graph problem, but it may as well have been as I had literally no clue how to even begin it. It’s effectively my current skill ceiling; I can solve problems A through C every contest, sometimes Problem D, but past that it’s extremely rare. It is an improvement from 6 months ago when Problem C would frequently be the last problem I could solve.

Overall, my consistency has been improving recently. The last time I had a sub 1400 level performance was in [Round 783](https://codeforces.com/contest/1668) back in mid April. The nine contests after that have resulted in 3 <span style=”color:cyan”>**Specialist**</span> level performances, 4 <span style=”color:blue”>**Expert**</span> level performances, and 2 <span style=”color:purple”>**Candidate Master**</span> level performances. Being able to solve 3 problems on a near routine basis has resulted in my ELO remaining consistently above 1600 for two straight months. The next step to reaching the next rating band at 1900 ELO is simple; I have to improve my skill cap to the point of being able to solve Problem D more consistently, and occasionally getting Problem E. 

Lastly, an update on everything else in my life. I have finally submitted a first round of applications, and have two more waves of applications prepared for later weeks if necessary. In the case that co-op doesn’t work out for Fall 2022 I still have flexibility in my program since I’m graduating in June 2024 at the earliest. 

