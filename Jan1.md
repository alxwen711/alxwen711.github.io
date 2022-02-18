---
layout: default
permalink: /blog/Jan22
---

[Link back to all posts](https://alxwen711.github.io/blog)

## January 1st-15th

_Note: this journal entry was written on February 11th mostly by referring to entries from my personal journal log in this time period._

Welcome to my first "written" journal log on this site. This entry will mostly be a recap of what happened during the first two weeks of 2022, although I'll also be including some of my other thoughts here from time to time, as well as anything else I feel like writing here. (Note that when I say anything else, I really do mean "anything else".)

The most significant event of the first two weeks of 2022 is my opening of a CodeForces account, [here is the link to it](https://codeforces.com/profile/alxwen711). I knew about CodeForces since last year, but I waited until the start of 2022 to create my account as I was still getting used to in person classes at SFU during the Winter 2021 term. Thus, I made it such that one of my main motives for 2022 would be to officially join CodeForces and see just how far I could progress over the span of a year. As of writing this (on Feb 11th), I have participated in 7 contests which all started at 6:35AM, with the first two being on January 3rd and January 10th. So how did those go?

The first contest I participated in was [Hello 2022](https://codeforces.com/contest/1621), and while it was easily my worst performance out of the contests I have participated in so far, I took away two key lessons. First lesson is pretty blatently obvious being that a good night of sleep before a contest is essential, as the night before the contest, as my Fitbit describes it, I was restless 19 times, woke up at 4:00AM (two hours earlier than intended), and was asleep for the grand total of 5 hours and 18 minutes. This I attribute to my own nerves getting excited/anxious at my first coding contest in about a year, and this mess of a rest partially contributed to the second lesson I learnt.

### input() vs sys.stdin.readline()

The problem in question from this first question is [Problem B](https://codeforces.com/contest/1621/problem/B). The solution to this question is quite trivial and is as follows:

<!--note to self to keep code blocks to at most 80 characters, also, this is a comment, it should not show up on the webpage.-->
```
Vasya will buy at most 2 segments. He will only buy the segment containing 
the minimum possible value, and the segment containing the maximum possible 
value. Most of the time, the minimum and maximum will be in different segments, 
meaning that Vasya will buy these 2 segments, but there is the possiblity that 
he buys only 1 segment if that specific segment contains both the minimum and 
maximum value. Furthermore, if 2 or more segments contain the minimum/maximum, 
then Vasya will only buy the cheapest one. Thus, the simplest method is to 
keep track of 3 segments:

- Segment A: The cheapest segment containing the minimum value x
- Segment B: The cheapest segment containing the maximum value y
- Segment C: The longest segment, if there is a tie for this choose the cheapest one

If C contains y-x+1 elements, then it must contain both x and y, meaning that 
Vasya would spend min(A+B,C) coins, with the letters referring to the cost of 
the segments. Otherwise, the cost would be A+B coins.
```

Now, in my sleep deprived state, when I was writing this contest, this was the final attempt I submitted for this question:

```python
for i in range(int(input())):
    n = int(input())
    low, high, cost = map(int, input().split())
    dual = False
    lc,hc = cost, cost
    print(cost) #first set
    for j in range(n-1):
        l, h, c = map(int, input().split())
        if dual:
            #2 set boundary
            if (l < low and h >= high) or (h > high and l <= low):
                cost, low, high = c, l, h
                dual = False
                #det subset
            #not subset
            elif (l < low) or (l == low and c < lc):
                low, lc = l, c
                cost = hc+lc
            elif (h > high) or (h == high and c < hc):
                high, hc = h, c
                cost = hc+lc
                
        else: #1 set boundary
            if (l < low and h >= high) or (h > high and l <= low) or (l == low and h == high and c < cost):
                cost, low, high = c, l, h
                #det subset
            #not subset
            elif l < low or h > high:
                dual = True
                if l < low:
                    low, hc, lc = l, cost, c
                else:
                    high, hc, lc = h, c, cost
                cost = hc + lc
 
            
        #new cost print
        print(cost)
```

In all fairness, the quality of code in coding competitions is much lower than than code I normally produce due to the fact I'm attempting to solve the problem as fast as possible, and proper documentation in this case is a secondary issue. What my algorithm was attempting to do was to continuously keep track of the segments Vasya would buy, with low, high, and cost tracking the min, max, and total cost of the segments respectively. I also correctly identified that Vasya could end up buying either 1 or 2 sets. Despite this, there is a technical error with my algorithm, which involves cases where Vasya swaps from buying 1 segment to 2 segments. Even if I found a way to fix this error though, I would still end up exceeding the time limit.

In comparison, this is an accepted solution I created after the contest as practice:

```python
import sys
 
for i in range(int(sys.stdin.readline())):
    n = int(sys.stdin.readline())
    length = -1
    lec = 1000000001
    low = 1000000001
    loc = 1000000001
    high = 0
    hc = 1000000001
    for i in range(n):
        l, h, c = map(int, sys.stdin.readline().split())
        if l < low: low, loc = l, c
        elif l == low: loc = min(loc,c)
        if h > high: high, hc = h, c
        elif h == high: hc = min(hc,c)
        if h - l > length: length, lec = h - l, c
        elif h - l == length: lec = min(lec,c)
        ans = loc + hc
        if high - low == length: ans = min(ans,lec)
        print(ans)
```

The above solution returns the Accepted verdict in 1.029 seconds. It is a basic implementation of the verbal solution listed above, but more significantly, it makes use of sys.stdin.readline(). As of writing this (Feb 11th), I'm not exactly sure why, but from [this webpage](https://medium.com/@xkumiyu/8-speed-differences-you-need-to-know-in-python-db7266c3b177), sys.stdin.readline() is about 10 times faster than input(), which proved to be enough of a difference to make this program fast enough. As a comparison, I submitted the exact same working solution above, but replaced all sys.stdin.readline() with input(), and that made the program fail to complet within the 2 second time limit. In a future entry I will delve into more detail as to why sys.stdin.readline() is so much faster than input().

This brings me to my second contest I took part in, [Codeforces Round #764 (Div. 3)](https://codeforces.com/contest/1624). This contest had generally easier than normal questions due to it being intended for non-experts, which is why I managed to complete 4 of the 7 questions, the most I have ever completed. My solution for [Problem D](https://codeforces.com/contest/1624/submission/142260424) in particular was relatively clean, where I simply kept track of the frequency of each character in an int[26] array to keep track of how many "pairs" of the same letter and how many left over letters I had, which could be used to determine the maximum length of each coloured palindrome string. The lack of "first contest stress", as well as actually being able to rest the night before, shows a clear difference between how I did in my first two contests, and more numerical analysis into this is detailed in my [Februray](https://alxwen711.github.io/blog/Feb22) logs.

Lastly, besides Codeforces, I also began the Spring 2022 term at SFU technically as a 3rd year student due to somehow having 60 credits completed, but I'd still consider myself finishing up 2nd year as I still have a few 200 courses to complete and some of the "completed" credits are really AP courses that are not really relevant to Computer Science. Most of the first two weeks was just reviewing previous concepts, although I did setup a VirtualBox to run Ubuntu for CMPT300 as well as MatLab for MACM316.

 

## January 16th-31st

For future logs written here, they will be following a set structure. This first paragraph will state a summary of important events regarding my life and other important updates to this journal log. After the opening paragraph will be my bi-monthly update on my journey through CodeForces with reflections after each contest, occasional rating statistics, and some highlighted problems with my method of approaching them that I found noteworthy of further discussion. Lastly in each post will be just a continuation of an update on my life events in general that I feel like sharing, but aren't really critical enough to put in the first paragraph. With that out of the way, the sole noticable update is that January 28th saw the official creation of this webpage, although it took me another 2 hours on January 31st to actually setup the webpage with the Jekyll theme used here, mainly due to the fact that I have a severe weakness when it comes to noticing small details at times.

In the span of these two weeks I completed 4 more contests on CodeForces, the first of which being [Round #766 (Div. 2)](https://codeforces.com/contest/1627). For future reference, all further contests mentioned are assumed to be Codeforces contests, and all will be assumed to be intended for Division 2 participants, which pretty much means the approximately 90%ish of coders who are rater under either 1900 or 2100, depending on the contest. As for this contest, from my reflection in my private journal immediately afterwards, it went pretty well, with myself solving the first two questions quickly due to having practiced solving easy 800-rated questions quickly a few days prior to this contest. The [third question](https://codeforces.com/contest/1627/problem/C) however was a basic tree problem, which was one of my weaknesses, and while I correctly determined that the only way a tree could become a prime tree was if it was a path, my method to solving it was likely an O(n^2) solution that was not fast enough. In hindsight writing this (on February 14th), the problem has a simple solve in O(n log n) time by creating a simple "binary" tree search and using recursion to search through the tree, but at the time that thought never really crossed my mind.

[Educational Round 121](https://codeforces.com/contest/1626) was a similar case where I solved the first two problems quickly and effectively but got stuck on the third one. I haven't really had much time to look at this question, but it will be covered in a future log. (link to it will show up here when I write it.) This also happened to be the first unrated contest I participated in, but this was mainly due to factors out of everyone's control since the Codeforces servers basically went out for me in the second hour, not that it really would have changed the overall result for me.

Next up is [Round 767](https://codeforces.com/contest/1629), which I didn't really have much time to prepare for and review after due to SFU classes starting again and in person teaching resuming 2 days after this contest on January 24th. Despite this, I still solved 3 of the 7 problems. [Problem C](https://codeforces.com/contest/1629/problem/C) had a greedy solution that matched the one described by the editorial and can be found [here](https://codeforces.com/contest/1629/submission/143675357) (annotated version coming soon).I also submitted a solution for [Problem D](https://codeforces.com/contest/1629/submission/143690128), but got the typical TLE for it due to it being mainly a brute force solution, which as a method of approach, brute force tends to fail being effective I find usually around Problem C, although the next contest makes a clear exception to this.

My last contest in January was [Round 769](https://codeforces.com/contest/1632), which actually saw at the time, by far my best overall performance in a contest (more detailing this in the [February](https://alxwen711.github.io/blog/Feb22) post.) The strange part is that while I did get 3 problems quickly on this contest, I feel that my solution for [Problem B](https://codeforces.com/contest/1632/problem/B) was the best solution I created, mainly because [Problem C](https://codeforces.com/contest/1632/problem/C) just saw me running a mainly brute force solution that somehow gave the correct answer.

At the end of January, I had completed 5 rated contests in total, meaning that I was 1 away from being officially rated. In my personal logs I had manually determined what my actual rating would be at this point if I had an official 6-contest rating, and it would be around **1531**. For context, [this](https://clist.by/resource/codeforces.com/) is a current distribution of the CodeForces "ELO" system including everyone who has completed at least 6 rated competitions. My initial goal was to reach 1600 by June, but after this start, even reaching 1900 does not seem too out there. As for the main takeaway from these contests, the main thing is that if you get a TLE error on a question, you're best off attempting to restructure your algorithm instead of resubmitting the program over and over again with micro-improvements. This is a mental trap that many novice programmers, including myself at times, fall for, where they get a TLE on their submission and proceed to make very marginal improvements in a desperate hope to make the program go faster, such as replacing every "i += 1;" with "i++;". Such examples of this are found in my submissions for [Round 766](https://codeforces.com/submissions/alxwen711/contest/1627), where I made 7 TLE submissions for problem C where the only difference between each submission were increasingly esoteric methods that maybe made my code 1-2% faster. Sure, it is possible this may help if your program for some reason happens to consistently finish 2 or 3 milliseconds over the time limit, but more often than not, the TLE means that your solution can be significantly improved in terms of big-O notation (frequently I find this to be going from O(n^2) to at least O(n log n)), and this means that the only reasonable way to speed up the code by a factor of at least 10 is to rethink a more efficient method for solving the problem.





Below this is just for reference for now while I get used to markdown

also figure out colour text at some point
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
