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

- $O\left(n\right)$: Linear
- $O\left(n^2\right)$
- $O\left(2^n\right)$
- $O\left(\log n\right)$
- $O\left(n\cdot m\right)$

In practice one would, for example, say:

- The time complexity of this algorithm is $O\left(n\right)$ (oh-of-n)
- The space complexity of my algorithm is $O\left(n^2\right)$ (oh-of-n-squared)

## Calculating complexity

There are, normally, three cases in complexity analysis:

- Best case scenario
- Average case
- Worst case scenario

In most algorithms, all three cases (i.e. best case scenario, average case, worst case scenario)
will all share the same complexity (big-O), but other will differ. Algorithms are judged based
on their worst case scenario.

Functions, or algorithm, calculate the number of operations (time) or the amount of
memory (space) relative to the input size.

Having the ability to abstract a(n) algorithm/function's complexity benefit's ones ability to
potentially optimize their own algorithm/function; in addition, interviewers will almost always
ask Big-O (time and space complexity) assess one's ability to determine what parts of a
algorithm/function can be improved.

### Rules

The rules when calculating complexity:

- **Ignore constants**: The point is to analyze the algorithm **_as the input changes_**.
  - We don't care that one algorithm versus another is 5x or 10x slower as the input size increases; for, the number of operations required increases $O\left(n\right)$ - **linearly**.
- Consider the complexity as the variables **tend to infinity**
  - Ignore all terms except the most powerful one; for example, $O\left(2^n+n^2-500n\right)\:=\:O\left(2^n\right)$: $O\left(2^n\right)$ is the most significant in the equation.
  - As `n` tends to infinity, $2^n$ becomes significantly large that the other terms are effectively zero in comparison

The best complexity possible is "constant time" or "constant space": $O\left(1\right)$ for
the algorithm/function ALWAYS uses the same amount of resources regardless of input size.
