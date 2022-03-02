---
layout: default
permalink: /blog/Feb22
---

[Link back to all posts](https://alxwen711.github.io/blog)
## February 1st-14th
_Note: Both of the logs here are being written around the end of February/start of March and are relying on personal journal logs. As of next month all new logs will be completed at or within a few days of their ending time period._

These two weeks marked the actual start of this "blog" where I log my own thoughts about recent projects I have completed, my CodeForces (mis)adventure, and other noteworthy life updates. In this case, asides from getting my first booster for the virus that has been causing a pandemic since March 2020 (yes, it has been that long), not too much event wise out of SFU has occured in these two weeks, so I'll just be recapping the 3 contests I took part in this two week period.

[Round 770](https://codeforces.com/contest/1634) was the first contest of the month, and without wanting to sound repetitive, I ended up solving 3 of the 6 problems somewhat quickly, which led to my official starting rating after the first 6 rated contests being 1527. For context, my initial goal for CodeForces at the start of the year was to reach <span style="color:blue">**Expert**</span>  in 6 months, and with how close I was to reaching that goal after only 6 weeks, given that the rating floor for <span style="color:blue">**Expert**</span> is only 1600, shortly after this contest I readjusted this goal to be more ambitious, to reach <span style="color:purple">**Candidate Master**</span> by the end of the year, which requires a rating of 1900. After all, it would only take a few more contests to reach <span style="color:blue">**Expert**</span> anyways.

The above paragraph were my thoughts the day after the contest on February 7th. I am writing this at the beginning of March, and my rating has not crossed 1527 since then. The beginning of my fall began on February 12th with [Global Round 19](https://codeforces.com/contest/1637), a contest where I blundered the [3rd relatively easy question](https://codeforces.com/contest/1637/problem/C). In the contest, I made 5 wrong answer submissions that all failed on pretest 2 because my determinations for the setups of stones that would lead to an answer of -1 were incorrect. For example, a stone setup of [1,1,1,2,2,1,1,1,1] is possible with the following operations:

```
1,1,1,2,2,1,1,1,1
1,2,1,0,2,1,2,1,1
1,2,2,0,0,2,2,1,1
1,0,2,0,0,2,2,2,1

and then take each of the remaining 2 stone piles and distribute 1 stone to pile
1, and the other stone to pile n.
```

In fact, as long as the middle n-2 piles are not all 1 stone each, then it is possible to move all the stones to piles 1 and n, assuming n is not 3. (For n = 3, the 2nd pile also must have an even number of stones.) Inexplicably, for the above example during the contest, I did not even think about anything after C being possible. My thoughts somehow revolved around counting the number of "2s" that could be used to make the odd stone piles even, but I failed to realize that in using up stones to make the odd piles have an even number of stones, I now had new piles of an even number of stones that could be used to fix remaining odd piles. 

This brings me to one of things I learned involving debugging code you write on CodeForces; usually, if your program WAs on pretest 2,3,4, basically any value close to 1, it usually means that there is some sort of error within your algorithm for solving the question, where as a wrong answer on a higher pretest like pretest 8 or 9 would likely mean that your program does not look at the edge cases properly. And of course, 99% of the time, TLE just means your program is running too slowly in terms of Big-O notation, with the most common difference I've found being between O(n^2) and O(n _log_ n).

Notice how I did not mention what is the likely problem in the case of Runtime Errors. I'm not exactly sure what is the main problem in this case, but at the moment, I would guess it is due to potential edge cases triggering out of index searches, but this type of error would plague me in [Round 771](https://codeforces.com/contest/1638), two days after the previous contest. In this case, instead of just the 3rd question being a problem, the entire contest as a whole was a complete mess for me, with two avoidable incorrect submissions on [Problem A](https://codeforces.com/contest/1638/problem/A), an excruciating long 35 minutes to solve [Problem B](https://codeforces.com/contest/1638/problem/B), and _eleven_ runtime errors on [Problem C](https://codeforces.com/contest/1638/problem/C), which I am still unsure just how this runtime error kept occuring.

To put into context just how badly the previous two contests went, there are two statistics I would like to share with you. The first one is simply how my rating was affected after these two weak contests. Within the 4.5 hours these two contests took place, I went from a **1527** rated <span style="color:cyan">**Specialist**</span> to a **1384** rated <span style="color:green">**Pupil**</span>. Granted, the rating system could be argued to be an arbrituary metric, but from experience, it hurts when you spend two mornings at 6:30 AM grinding away only to pretty much lose all the progress you have built up from the previous month. 

The second statistic is the individual contest performance, which is a bit less obvious. To put it simply, I define performance from the contest as the rating the ELO system would expect you to be based on your results in a given contest. To put it in an example, if you performed equally as well as someone else who was rated 1500 in a contest, and the 1500-rated coder saw no change in rating after the contest, then your performance rating would be 1500. There are caveats to this method, being that there won't always be such a person with a similar performance and 0 rating change, and the fact that [CodeForces new method of rating calculation](https://codeforces.com/blog/entry/77890) means that the rating used for calculation is different from the one displayed for the first 6 contests, but this is a relatively accurate method to finding one's own performance to within 10-20ish points. With that said, this is a table of the 8 rated contests so far I had participated in:

| Contest    | Rating | Difference | Performance |
|------------|--------|------------|-------------| 
| Hello 2022 | 1359   | -41        | 1197        |
| 764        | 1432   | +73        | 1593        |
| 766        | 1426   | -6         | 1404        |
| 767        | 1450   | +24        | 1517        |
| 769        | 1531   | +81        | 1738        |
| 770        | 1527   | -4         | 1511        |
| Global 19  | 1446   | -81        | 1192        |
| 771        | 1384   | -62        | 1183        |

Hello 2022 was the first contest I participated in and given the difference in performance that is understandable. However, it also puts into context just how badly the previous two went due to my ineffective debugging, an often unspoken skill within programming competitions as a whole. Thankfully, this is _definitely_ the rock bottom in terms of rating I will reach, and _surely_ in the next two weeks I will make a strong recovery.

In other news, immediately after Global 19, as part of my prep term for a potential Co-op Term in Fall 2022, I went through 5 hours of workshops covering resumes, cover letters, and interviews. For future SFU Co-op students I would advise against this method and just take BOL I first as those workshops ended up building on concepts that I was supposed to learn first in BOL I.

## February 15th-28th





Below this is just for reference for now while I get used to markdown
### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for 

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
