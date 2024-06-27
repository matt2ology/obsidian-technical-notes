---
author: leetcode.com
category-tag: articles
source-tag: reader
---
# Stacks and queues are data structures defined by their interfaces. They're a good example of how a simple idea can be used to implement efficient algorithms, and how data structures & algorithms show up in our everyday lives.

![rw-book-cover](https://leetcode.com/static/images/LeetCode_Sharing.png)

## Metadata
- Author: [[leetcode.com]]
- Full Title: Stacks and queues are data structures defined by their interfaces. They're a good example of how a simple idea can be used to implement efficient algorithms, and how data structures & algorithms show up in our everyday lives.
- Category: #articles
- URL: <https://leetcode.com/explore/interview/card/leetcodes-interview-crash-course-data-structures-and-algorithms/715/introduction/4654/>
## Summary

Stacks and queues are data structures with defined interfaces. They help implement efficient algorithms in everyday life. Understanding time and space complexity is essential in analyzing algorithms.

## Highlights
Algorithms are functions. It takes an input x and produces an output y.

> Algorithms take an input and produce an output. The output will be the answer to a question regarding the input. ([View Highlight](https://read.readwise.io/read/01j0mt9sjfr6skrd54z2mnvs4h))

---



> Algorithms take an input and produce an output. The output will be the answer to a question regarding the input ([View Highlight](https://read.readwise.io/read/01j0mtjv41hd2wtv4m4qfjbhrr))

---

Like a true function, an algorithm, should be one-to-one (1:1).

> Algorithms should be **deterministic**. Given the same **input**, the algorithm should **always** produce the same **output**. Basically, there shouldn't be any randomness. ([View Highlight](https://read.readwise.io/read/01j0mtr94mrdskgvzj4grd9aj3))

---



> Big O is a notation used to describe the computational complexity of an algorithm. ([View Highlight](https://read.readwise.io/read/01j0mv5kdjv2r9scyaf20yd89b))

---



> The time complexity of an algorithm is the amount of time the algorithm needs to run relative to the input size. ([View Highlight](https://read.readwise.io/read/01j0mvec3vnmr41y7yz9a23zhk))

---

Is cared about when running "close to metal" on hardware that has limited storage/memory.

> The space complexity of an algorithm is the amount of memory allocated by the algorithm when run relative to the input size. ([View Highlight](https://read.readwise.io/read/01j0mvefmdbxvqezaznds2r0qs))

---

Like algorithms, complexity is a function and is described by a mathematical formula.

> Complexity is described by a function (math formula). ([View Highlight](https://read.readwise.io/read/01j0qm7pvc51tksxdf8hcqk821))

---

Argument variables should encapsulate the concept/idea, capture the essence, of the corresponding inputs they represent as they affect the algorithm: `n`-numbers, `k`-average, `obj`-object, `num`/`i`/`j` - for some integer number, etc.

> The arguments are variables defined by the programmer, but they should represent values that change between different inputs, and these values should affect the algorithm. ([View Highlight](https://read.readwise.io/read/01j0qmnq0rxz38ybj3p5sk9cnk))

---

We care about input size, not an integer like 4 or 9,001, like an array/list of 4 or 9,001 elements/items.

> When dealing with integers, the larger the integer, the more time operations like addition, multiplication, or printing will take. While this **is** relevant in theory, we typically ignore this fact because the difference is practically very small, and treat all integers the same. If you are given an array of integers as an input, the only variable you would use is nnn to denote the length of the array. ([View Highlight](https://read.readwise.io/read/01j0qp9a6kvpgnhsahg66kmwxj))

---



> Being able to analyze an algorithm and calculate its time and space complexity is a crucial skill. Interviewers will **almost always** ask you for your algorithm's complexity to check that you actually understand your algorithm and didn't just memorize/copy the code. Being able to analyze an algorithm also enables you to determine what parts of it can be improved. ([View Highlight](https://read.readwise.io/read/01j0wryergqrerpbyvtsb3waac))

---

1. **Ignore constraints**
- We don't care that one algorithm versus another is 5x or 10x slower as the input size increases; for, the number of operations required increases $O\left(n\right)$ - **linearly**.
2. Consider the complexity as the variables **tend to infinity**
- Ignore all terms except the most powerful one
There are, normally, three cases in complexity analysis:
- Best case scenario
- Average case
- Worst case scenario

> There are a few rules when it comes to calculating complexity. ([View Highlight](https://read.readwise.io/read/01j0wt7wmp5bn4p4267fdztgs1))

---



> When talking about complexity, there are normally three cases:
>   • Best case scenario
>   • Average case
>   • Worst case scenario ([View Highlight](https://read.readwise.io/read/01j0wt74ecxw4x5fe8hj8tjry1))

---

