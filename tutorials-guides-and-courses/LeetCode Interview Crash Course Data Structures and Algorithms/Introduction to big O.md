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
