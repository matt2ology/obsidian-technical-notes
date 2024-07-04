---
aliases:
note-type: permanent
date-created: 2024-05-29
long-form-date-created: Wednesday, May 29, 2024
week-created: Week 22.3
time-created: 01:43 PM
---

# LeetCode - 20 - Valid Parentheses

Related : [NOTE HUB](../tutorials-guides-and-courses/LeetCode%20Interview%20Crash%20Course%20Data%20Structures%20and%20Algorithms/NOTE%20HUB.md)

Source : [LeetCode 20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)

Topics : [String Problems](String%20Problems) - [Stack Data Structure](../_inbox/Stack%20Data%20Structure.md)

## Solution in Python

```python
class Solution:
    def isValid(self, s: str) -> bool:
        # Stack to keep track of opening brackets
        stack = []

        # Dictionary to keep mappings of closing to opening brackets
        bracket_map = {')': '(', '}': '{', ']': '['}

        # Iterate over each character in the string
        for char in s:
            # If the character is a closing bracket
            if char in bracket_map:
                # Pop the top element from the stack if it's not empty, otherwise assign a dummy value
                top_element = stack.pop() if stack else '#'

                # Check if the popped element matches the corresponding opening bracket
                if bracket_map[char] != top_element:
                    return False
            else:
                # It's an opening bracket, push it onto the stack
                stack.append(char)

        # If the stack is empty, all opening brackets had a matching closing bracket
        return not stack
```
