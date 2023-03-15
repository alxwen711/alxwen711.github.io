---
layout: default
permalink: /blog/Mar23
---

[link back to all posts](https://alxwen711.github.io/blog)

## March 1st-15th

Currently not listed in this very high quality recap of recent CodeForces contests is that each week I am doing a practice ICPC contest. It’s more of a personal thing so they won’t be getting full recaps here, but I’ll use this space to document current progress. After the disasterclass that was ICPC Pacific Northwest 2022, I started off with the 2015 Pacific Northwest Div 2 contest to gauge where I’m at. It turns out a 2 star Codeforces Gym is a bit too easy for me since I got all of the questions right in 3 hours. Now I’m working on 3 star level practice, which is more suitable for my level. Ideally before October I’m consistently hitting 7-8 problems on 4 star level contests which should be the approximate level of the 2023 regional.

### [Round 856](https://codeforces.com/contest/1794)

Problems Solved: A, B, C

New Rating: **1829** (-20)

Performance: **1766** 

Congratulations: It’s more mid. Except this time, I ended in mediocrity in a funny way by screwing up [A](https://codeforces.com/contest/1794/problem/A) twice. I suspect what happened was that my reverse string method may have also been detecting substrings accidentally. For future contests it may be just best to not be overly reliant on fancy string indexing shenanigans when there are much simpler solutions possible. This random 100 point loss is rectified by myself solving [B] (https://codeforces.com/contest/1794/problem/B) and [C](https://codeforces.com/contest/1794/problem/C) in 14 minutes, but it still does not help my problem of not being able to solve [D](https://codeforces.com/contest/1794/problem/D). I would say that I made actual progress here but I felt genuinely stuck. Put simply, code libraries don’t really matter when you have no clue how to calculate the combinatorial problem.

This recap may seem short, but all I could discuss was me trolling A, ransacking B and C for being easy problems, or talking about what little progress I made on D. Maybe I’ll have more use out of recapping my ICPC practice contests that I’m doing weekly now.

### [Nebius Welcome Round](https://codeforces.com/contest/1804)

Problems Solved: A, B, C, D

New Rating: ~~**1900** (+71)~~ **1899** (+70)

Performance: ~~**2083**~~ **2080** 

Curse you cheaters. I was actually about to celebrate reaching CM from this contest. I thought that the plagiarism checks if anything, would increase my rating gain because it’s expected that cheaters do well on the contest. It turns out that there were enough cheaters that placed below me that my overall rating gain ended up decreasing. I would do the whole essay and condemnation here on why cheating hurts not just the cheaters themselves but the entire competitive programming community as a whole, but there are enough articles on the Internet about this and I doubt that another one here would change many cheater’s minds. That said, just wow. If you were one of those cheaters, I don’t know whether to be feeling disappointed, mockery, or nothing at all. You not just cheated, you cheated in a contest an actual company was using for finding legitimate candidates. Not only that, a lot you didn’t even cheat properly. Some people cheated for a virtual rating or title on the Internet thinking that it would bring respect or accomplishment. It maybe works since our world tends to be quite shallow when looking at surface level accomplishments. Still does not change the fact that it’s quite pathetic one would go through such fraudulent measures for the appearance of mediocre accomplishment. 

With that minor rant out of the way, this was actually a good contest for me. [B](https://codeforces.com/contest/1804/problem/B) felt slightly harder than [C](https://codeforces.com/contest/1804/problem/C) which is understandable since they both had the same point value, but more importantly, I actually solved a [D](https://codeforces.com/contest/1804/problem/D) problem again. My process for finding minimums is very simple and accurate; just assign 2 window rooms to as many “11”’s as possible. For maximums, it’s the exact inverse, place 2 window rooms anywhere except “11”’s. My first 3 attempts thought there was a difference in priority between “01”/”10” and “00” pairs, but turns out that this causes an incorrect answer given a specific setup. This contest as a whole feels like one where in a rare occurrence, I did not shoot myself in the foot. There was a bit of progress made on [E](https://codeforces.com/contest/1804/problem/E) as well; The solution involves checking between each of the 2**n possible groups of nodes if a cycle exists between them, and if it does, does this cycle and its neighbouring nodes consist the full graph. The issue is that determining if a cycle exists between x given nodes in a graph of n nodes is a bit complicated.




## March 16th-31st

