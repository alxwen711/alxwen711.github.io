---
layout: default
permalink: /blog/Mar22
---

[Link back to all posts](https://alxwen711.github.io/blog)


## March 1st-15th

Note: Most of this entry was written at the end of March, mostly because SFU Midterms and projects happened. I'm still in the heavy part of my courseload this term, so the next post may also be delayed, but hopefully by April posts are actually being posted on time.

The first two weeks of March was the first period in which I do not have any CodeForces contests to recap, due to the fact that nearly all of them run during times when I am in class at SFU, and the one that didn't started at 1:55AM. Regardless, there is still much to recap, mainly the ICPC Pacific Northwest Regional Contest that took place on March 5th.

The Pacific Northwest Regional is a university level programming competiton that serves as a qualifier for the North American Championship, the penultimate stage before the ICPC World Finals. The regional contest itself is divided into Divison 1, which is for more experienced competitors and has a problemset that is basically a lite version of what could be expected at the World Finals, and Divison 2, for newer competitors who have not completed the all the algorithm courses in their program yet.  Since this was my first time competiting in this kind of competition, I alongside Brandon Zhu and Rishi Saran Vijayarajan competed in Divison 2 as SFU_Honeydew (Honeydew is a very light green colour that would represent all the accepted submissions we would get in the contest. I may have made that last sentence up.).

The competition itself functioned similarly to most online competitions, but with a few significant changes, most trivially is that this is a team competiton, so communication and team strategy plays a key role here. 13 problems were to be solved within **5** hours, making this by far the longest competition I have competed in. This made the competiton much more of a marathon rather than a sprint where the focus was not to try and get the easy questions quickly with as little penalty as possible, but to solve as many questions as possible, even at the cost of having a large penalty due to incorrect submissions.

Anyways, that's enough explaining the format of the contest. [Here](http://www.acmicpc-pacnw.org/pacnw_div2_2022.pdf) is a link to the PDF containing the Division 2 questions. Note that the questions are not arranged in order of increasing difficulty. As for how our team did?

![Results from the ICPC Pacific Northwest Regional 2022 Division 2](/docs/assets/images/icpcresults.png)

We crushed the contest, placing clear second overall in the division by two questions. If it wasn't for the fact that each school could only enter a maximum of 6 teams in Division 1, we probably would have also won the divison outright, but that aside, our team was the only one to solve problem T, and that will be one of the three questions I'll be going over in this recap today, alongside problems S and Y.

### Problem S, Rise and Fall
This was one of the easier questions in the contest, and is similar to the kinds of problems one would find in CodeForces on a Div 2 contest as problem A or B. The first thing we can notice is that the key limitation on the input is that we'll be dealing with up to 10^5 digits in 1 second. This brings up a principle of coding contests that I will refer to as the "Rule of a Million", which is for a sample size of _n_, if your solution f(x) is to run within a reasonable timeframe (usually 1 second), then f(n) should be no greater than a million. With numerical examples, an O(n^2) solution will usually be good for sample sizes up to 1000 since 1000^2 = 1000000, O(n^(1.5)) solutions will likely be good for sample size up to 10000 since 10000^1.5 = 1000000, and O(2^n) solutions will usually work only up to n = 20. In this case, n = 100000, meaning that we'll likely need at least an O(n log n) solution, but in this case, the problem is solvable in linear time.

The one pass solution is to use a greedy approach in choosing the digits, and always attempt to choose the highest digit possible. This is relatively trivial as 3999999 < 4000000 because the first digit of the second number is greater, even if the other digits say otherwise. Our rise-and-fall number has to start with the digits nondecreasing, thus we copy the first digits of the number as our answer until we find two adjacent digits that are decreasing. From there, the nature of the rise-and-fall number means that the remaining digits have to either stay the same or decrease. From there, the remaining digits of the starting number are copied ONLY if they stay in a non-increasing subsequence. If the digits start increasing again, then we can copy the last digit in our answer and append it enough times until our final answer has the same number of digits as our given number. Such a case is seen with the value 137879620, for which the answer would be 137877777 since we start copying the 7 after we see the 5th and 6th digit increasing.

Example code implementing this approach is below:
```python
for i in range(int(input())):
    x = str(input())
    inc = True
    digit = 0
    ans = ""
    for j in range(len(x)):
        d = int(x[j])
        if inc: #increasing phase
            if d < digit: #enter the decreasing phase
                inc = False
            digit = d
            ans += str(d)
        else: #decreasing phase
            if d <= digit:
                digit = d
                ans += str(digit)
            else: #found increasing part, copy prev digit until long enough
                for k in range(len(x)-j):
                    ans += str(digit)
                break
    print(ans)
```

### Problem Y, Dorm Room Divide
This was actually a problem no one on our team could solve. As you'll see, we had the right solution, but there was some sort of implementation error that led to 18 failed attempts. Runtime speed was never an issue, as our attempts all used algorithms intended to run in O(n) time.



## March 16th-31st



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

