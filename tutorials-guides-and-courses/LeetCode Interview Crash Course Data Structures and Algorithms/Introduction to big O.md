---
aliases:
note-type: permanent
date-created: 2024-06-17
long-form-date-created: Monday, June 17, 2024
week-created: Week 25.1
time-created: 09:25 PM
---

# Introduction to Big-O

Related : [Algorithm Hub](../../Algorithms/Algorithm%20Hub.md)

Topic : [Big-O](Big-O)

Big O is a notation used to describe the computational complexity of an algorithm.

There are two parts to the computational complexity

- Time complexity (typically cared about most)
  - The amount of time an algorithm needs to run relative to the size input
  - Think: as the input size grows, how much longer does the algorithm take to complete?
- Space complexity
  - The amount of memory allocated by the algorithm when run relative to input size
  - Is cared about when running "close to metal" on hardware that has limited storage/memory.
  - Think: as the input size grows, how much more memory does the algorithm use?

## How complexity works

Like [algorithms](../../3-permanent-notes-🧲/What%20is%20an%20Algorithm.md),
complexity is a function and is described by a mathematical formula.

The inputs to complexity, its arguments, are variables defined by the programmer.
These variables represent values that change between different

Argument variables should encapsulate the concept/idea, capture the essence,
of the corresponding inputs they represent as they affect the algorithm:
`n`-numbers, `k`-average, `obj`-object, `num`/`i`/`j` - for some integer
number, etc.

In complexity we care about input size, not an integer like 4 or 9,001, but an
array of 4 or 9,001 elements/items.

Complexity, as written, is represented as a function with a capital "O" (oh)
and some, arbitrary, input size argument variable `n`:

- $O\left(n\right)$
- $O\left(n^2\right)$
- $O\left(2^n\right)$
- $O\left(\log n\right)$
- $O\left(n\cdot m\right)$

In practice one would, for example, say:

- The time complexity of this algorithm is $O\left(n\right)$ (oh-of-n)
- The space complexity of my algorithm is $O\left(n^2\right)$ (oh-of-n-squared)

