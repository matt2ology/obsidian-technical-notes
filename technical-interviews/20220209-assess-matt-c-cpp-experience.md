---
aliases:
note-type: permanent
date-created: 2022-02-09
long-form-date-created: Wednesday, February 9, 2022
week-created: Week 06.3
time-created: 04:55 PM
---

# Interview for Internal Tools Team

Related : [Technical Interview Note Hub](Technical%20Interview%20Note%20Hub.md)

Topics : [C Programming Language](C%20Programming%20Language)

## Interview questions asked

1. What is up-cast and what is downcast
   1. Which one is safer
      1. Answer: it's better to up-cast because it's more general
2. What is the difference between class, interface, abstract class, and object
3. What are the types of variables in C
4. How long is a byte
5. what is the size of an int
6. What is the max number variable int can hold
7. How would you do a one liner of sum of numbers
   1. Answer: $\frac{\left(number\cdot \:\left(number+1\right)\right)}{2}$
8. How would you print in C

## What is the output below?

```c
#include <stdio.h>
#include <stdlib.h>

int main(){
 int i = 30000;
 byte b = i;
 return 0;
}
```

```c
#include <stdio.h>
#include <stdlib.h>

int main(){
 byte b = 250;
 byte c = b+7;
 return 0;
}
```
