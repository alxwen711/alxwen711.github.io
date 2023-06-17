---
layout: default
permalink: /blog/Jun23
---

[link back to all posts](https://alxwen711.github.io/blog)

## June 1st-15th

Here we have another typical recap. Sometimes I’m unsure what to put here in these initial sections, but I guess I have a few thoughts about this journal. I guess now I find this as a good form of self reflection on each contest I do, and one of the more honest expressions of myself. Anyways, here’s the two most recent CodeForces contests I went in:

### [Round 877](https://codeforces.com/contest/1838)

Problems Solved: A, B, C, D

New Rating: **2028** (+32)

Performance: **2110**

To describe this contest in one sentence: It was looking ugly for a moment, but I got it done. 


<details>
<summary> Thoughts on B </summary>
I had issues as early as [B](https://codeforces.com/contest/1838/problem/B) in this contest mainly due to myself trying to figure out why my solution worked. My assumption is that there is a pair that exists that would minimise the number of permutation subarrays to 2 (being for length 1 and length n).  This intuitively makes sense but as to how exactly is the part I was pretty much guessing. With my solution I ended up trying 4 different swaps where either the value 1 or 2 is swapped to the left or right end of the array, and if this didn’t work I just guessed. Turns out that moving the value 1 or 2 to the end of an array will always be optimal. Either that or there’s a really obscure test case no one has found yet that would cause a successful hack. I’m leaning towards the former.
</details>

I would go into more detail for [C](https://codeforces.com/contest/1838/problem/C), as on the surface of my solve time, it looks like a fairly complex problem. However, this is more me overthinking this and it feels very similar in its constructive process to a B-level problem like [Anti Permutation Forces](https://codeforces.com/contest/1644/problem/B). Yes, I still remember the “I can’t count to five” problem.


<details>
<summary>Literally the answer for C, after I go over the overcomplicating I did</summary>

First thing that can be noted is that there is no need to quickly determine if the dimensions of the grid are prime or not. I used a sieve to compute this but if either dimension is even, then it is sufficient to list the numbers incrementally row by row or column by column. Such ideas can be used to easily generate boards where the difference between each adjacent pair is either 1 or one of the dimensions of the grid.

If both dimensions are prime (or even just both odd works as well), then it’s a bit more complicated. First you can split the values into rows or columns as follows. For instance, for a 7x7 grid, one row will have 1-7, then 8-14, then 15-21, and so on until 43-49. From there you just place the highest value row in the middle, and place the remaining rows lowest the highest building out from the middle like this:

```
 29 30 31 32 33 34 35
 15 16 17 18 19 20 21
  1  2  3  4  5  6  7
 43 44 45 46 47 48 49
  8  9 10 11 12 13 14
 22 23 24 25 26 27 28
 36 37 38 39 40 41 42
```

With this method row by row adjacencies will trivially have a difference of 1. Between most columns the difference is 2n, where n is a dimension of the grid, which can never be prime. The difference between the middle 3 rows will vary, but assuming n is at least 5, it will be a factor of n and not equal to n, so it will also never be prime.

As for what my initial complication was? What my first idea was that if both dimensions are prime, then a grid of size n-1 by m could be filled out, and then for the remaining m values some sort of  search algorithm would be needed to find a setup that specifically works there. An example of this thought is with this 5x5 grid, where a 5x4 grid is filled and the remaining values are placed god knows where:

```
 1  2  3  4 22
 5  6  7  8 23
 9 10 11 12 24
13 14 15 16 25
17 18 19 20 21
```

A fun case would be to try and show which grid dimensions have this sort of solution, or if this idea could be used for any grid size.

</details>


[D](https://codeforces.com/contest/1838/problem/D) is significantly harder, but I managed to figure this out. Somehow. With 6 minutes left in the contest.


<details>
<summary> D thought process </summary>
Seeing that there is up to 200000 queries and a length of 200000, this likely means the queries have to be at least O(log n). With the bracket sequence, a first useful idea is to think of each `(` as a +1 and each `)` as a -1. For a bracket sequence to be valid, when you take its running sum, it must always be non-negative AND its total sum has to be 0. That’s why something like `())()(()` fails; after the first 3 characters its at a sum of -1.

This initial logic means that a valid bracket sequence must start with `(`, end with `)`, and be of an even length. The next step is to track where each `((` and `))` occurs. These are important as a backwards move can be used infinitely between these two patterns to increment/decrement the running sum as needed. If neither `((` or `))` is present in the sequence, then it is comprised of only `()()()()()...`, which is always valid. If only one of them is present, then the final running sum will never be 0 making it always invalid. Lastly, if both of them are present, then the first `((` must appear before the first `))` in the sequence and the last `))` must appear before the last `((` in the sequence for the running sum to always remain non-negative. Assuming all the rules above are followed, the bracket sequence has a valid walk.

To track the first/last `((/))`, you can use 4 heaps to track each occurrence. The general case is to add new occurrences of each pattern after flipping a symbol. After the additions, you check if the top of the heap is correct, and if not, keep removing the top of the heap until the top value represents the correct index where the pattern exists. Since each removal is O(log n) and only up to 2 new patterns could potentially be added (`()( -> (((`) for a heap (at most 4 heap pushes per query), this ends up as an amortised O(log n) operation.

[Accepted Submission](https://codeforces.com/contest/1838/submission/208506761)

</details>



### [Educational Round 150](https://codeforces.com/contest/1841)

Problems Solved: A, B, C

New Rating: **2010** (-18)

Performance: **1953**

I did pretty weirdly on this contest. Normally a poor contest occurs due to missing a problem D or getting skill capped on later questions, but here more of the errors are due to scuffed execution on middle problems. [B](https://codeforces.com/contest/1841/problem/B) had one avoidable mistake which I attribute to bad implementation. [C](https://codeforces.com/contest/1841/problem/C) was incredibly scuffed and required over an hour to complete. [My submission](https://codeforces.com/contest/1841/submission/209449649) comments actually explain my thought process pretty well; the only change being that an `E` could replace the first of any A, B, C, or D letter, not just the first non E. [D](https://codeforces.com/contest/1841/problem/D) I was genuinely screwed on, but [E](https://codeforces.com/contest/1841/problem/E) was where I actually thought up a legit solution.

<details>
<summary>E solution</summary>

A row segment refers to the number of consecutive cells in a row. For instance, if the input was something like the following:
```
4
0 1 2 3
5
```
Then there would be a single row segment of length 1, 2, 3, and 4. Once you know how many row segments of each length there are, computing the answer simply requires filling in the longest row segments greedily.

The eventual grid will resemble a bar chart, so you want to scan from top to bottom for when each column begins its white cells. Here the tricky part is tracking the length of each segment; for this I used two arrays L and R. With this setup, suppose a segment of white cells traverses indices a to b, then `L[b] = a` and `R[a] = b`. Another way to put it is that for the L array, L[x] = n means that index x is the right endpoint of a segment, and that n is the respective left endpoint. R array works in opposite. By tracking these indices, the length of the segment is calculable. Updating these segments with a new white cells results in one of three cases:

The new cells neighbours are both not part of existing segments: this results in this new cell creating a length 1 segment.
One of the neighbours is in an existing segment, causing it to be extended by 1 unit
Both neighbours are in existing segments, thus combining two segments into a single one

Each of these cases has its own rules for updating the segments and an array tracking the lengths of each segment. Lastly after every row, the segment lengths are accumulated for the eventual total of segments in the entire grid. Further optimization can be done by tracking the frequency of each segment length in each row instead of the length of each segment; this way a row with 100000 length 1 segments will not result in 100000 additions. In total, the maximum unique number of segment lengths possible in a row is about `sqrt(2n)` (1+2+3+4+5…), so this algorithm has a worst case runtime of $O(n^{1.5})$.

</details>

The entire solution I devised for E is correct. The only problem was that I had about 10 minutes left in the contest to implement this. Needless to say, I didn’t exactly complete it in time. [At least I upsolved it?](https://codeforces.com/contest/1841/submission/209502688)


## June 16th-30th

