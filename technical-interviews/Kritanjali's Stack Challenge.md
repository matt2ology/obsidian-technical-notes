---
aliases:
note-type: permanent
date-created: 2024-05-28
long-form-date-created: Tuesday, May 28, 2024
week-created: Week 22.2
time-created: 09:51 PM
---

# Kritanjali's Stack Challenge

Related : [Stack Data Structure](../_inbox/Stack%20Data%20Structure.md) - [Kritanjali's Queue Insert Challenge](Kritanjali's%20Queue%20Insert%20Challenge.md)

Topics : [Data Structures](../Data%20Structures/Data%20Structures.md)

## Prompt

```c
typedef struct Element
{
    struct Element *next;
    int data;
} Element;

/**
Given the Element structure above, implement the 2 function prototypes
below in C. Note that you will have to allocate memory for every new
Element struct you create.
*/

int push(Element *top, int data)
{
    // return 0 on success, -1 on failure;
    // go matt
}

int pop(Element *top)
{
    // do the thing zhu-li
}
```

## Implementation in C

```c
#include <stdio.h> // used for printf
#include <stdlib.h>
typedef struct Element
{
    struct Element *next;
    int data;
} Element;

int push(Element **top, int data)
{
    Element *new_element = (Element *)malloc(sizeof(Element));
    if (new_element == NULL)
    {
        return -1; // Memory allocation failed
    }
    new_element->data = data; // Set the data of the new element to the input data
    new_element->next = *top; // new_element's next points to current top
    *top = new_element;       // top now points to new_element
    return 0;                 // Success
}

int pop(Element **top)
{
    if (*top == NULL)
    {
        return -1; // Stack is empty so return -1
    }
    Element *temp = *top; // Store the current top in a temporary pointer
    int data = temp->data; // Store the data of the current top in a variable
    *top = (*top)->next; // Move the top to the next element in the stack
    free(temp); // Free the memory of the popped element to avoid memory leaks
    return data; // Return the popped data
}

// Stub
int main()
{
    Element *stack_top = NULL; // Initialize stack top pointer
    int num_elements = 3;      // Initialize number of elements in the stack

    // Push elements onto the stack
    for (int elementNum = 1; elementNum <= num_elements; elementNum++)
    {
        // multiple of 10 to distinguish from the index value of the element
        push(&stack_top, elementNum * 10);
        printf("Pushed element: %d\n", elementNum * 10);
    }

    // Pop elements from the stack and print them
    for (int elementNum = 1; elementNum <= num_elements; elementNum++)
    {
        printf("Popped element: %d\n", pop(&stack_top));
    }

    if (pop(&stack_top) == -1)
    {
        printf("Stack is empty\n");
    }
    else
    {
        printf("Popped element: %d\n", pop(&stack_top)); // Should return -1
    }
    return 0;
}
```

### Breakdown of `Element *new_element = (Element *)malloc(sizeof(Element));`

```c
Element *new_element = (Element *)malloc(sizeof(Element));
```

1. `malloc(sizeof(Element))`
   - `malloc` allocates a block of memory of the size of the element's structure in bytes.
   - According to malloc function documentation

     > On success, a pointer to the memory block allocated by the function. The type
     > of this pointer is always `void*`, which can be cast to the desired type of data
     > pointer in order to be dereferenceable. If the function failed to allocate the
     > requested block of memory, a *null pointer* is returned."

     - i.e. A `void *` (void pointer), a generic pointer, is returned that then can be pointed to any data type.
2.  **Type Casting**  using `(Element *)`
    - Converts the `void *` (the void pointer) into a pointer of type `Element *`
    - Without this we'd get an warning or an error because `malloc` returned a void 
      pointer

#### Example of Pointer Type Casting

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // Allocate memory for an integer
    void *void_ptr = malloc(sizeof(int));
    if (void_ptr == NULL) {
        printf("Memory allocation failed\n");
        return 1;
    }

    // Print the raw void pointer
    printf("Raw void pointer: %p\n", void_ptr); // This will print the address of the allocated memory

    // Cast the void pointer to an int pointer
    int *int_ptr = (int *)void_ptr;

    // Set the value of the integer
    *int_ptr = 42;

    // Print the int pointer and the value it points to
    printf("Casted int pointer: %p\n", int_ptr);
    printf("Value at int pointer: %d\n", *int_ptr);

    // Free the allocated memory
    free(void_ptr);

    return 0;
}
```

### Handling the Pointers

#### Passed by Reference

The `pop` function (`int pop(Element **top)`), the top pointer is passed by reference
(a  double pointer) and is modified within the function to point to the next element in the 
stack.

```c
int pop(Element **top)
{
    if (*top == NULL)
    {
        return -1; // Stack is empty so return -1
    }
    Element *temp = *top; // Store the current top in a temporary pointer
    int data = temp->data; // Store the data of the current top in a variable
    *top = (*top)->next; // Move the top to the next element in the stack
    free(temp); // Free the memory of the popped element to avoid memory leaks
    return data; // Return the popped data

// Stub
int main() {
    Element *stack_top = NULL; // Initialize stack top pointer

    // Push elements onto the stack
    printf("Pushed element: %d\n", push(&stack_top, 10));
    printf("Pushed element: %d\n", push(&stack_top, 20));
    printf("Pushed element: %d\n", push(&stack_top, 30));
    // Pop elements from the stack and print them
    printf("Popped element: %d\n", pop(&stack_top));
    printf("Popped element: %d\n", pop(&stack_top));
    printf("Popped element: %d\n", pop(&stack_top));

    // Try popping from an empty stack
    printf("Popped element: %d\n", pop(&stack_top)); // Should return -1
    return 0;
}
```

#### Return By Value

This `pop` function has a return type of `Element*`, indicating it returns the new top 
element of the stack after popping.

```c
Element* pop(Element *top, int *popped_data) {
    if (top == NULL) {
        return NULL; // Stack is empty
    }
    Element *temp = top;
    *popped_data = temp->data;
    top = top->next;
    free(temp);
    return top; // Return the new top element
}

int main() {
    Element *stack = NULL; // Initialize the stack to be empty

    // Push elements onto the stack and print them
    stack = push(stack, 10);
    printf("Pushed: 10\n");
    stack = push(stack, 20);
    printf("Pushed: 20\n");
    stack = push(stack, 30);
    printf("Pushed: 30\n");

    int popped_value;
    // &popped_value is the address of the variable
    printf("The address of popped_value is: %d\n", &popped_value);
    // popped_value is the value of the variable
    printf("The value of popped_value is: %d\n", popped_value);

    // Pop elements from the stack
    stack = pop(stack, &popped_value);
    // print Stack and then popped value
    printf("Popped: %d\n", popped_value);
    stack = pop(stack, &popped_value);
    printf("Popped: %d\n", popped_value);
    stack = pop(stack, &popped_value);
    printf("Popped: %d\n", popped_value);
    
    // Attempt to pop from empty stack
    stack = pop(stack, &popped_value);
    if (stack == NULL) {
        printf("Stack is empty\n");
    }

    return 0;
}
```

## Resources for C Implementation

- [The `malloc` function](https://cplusplus.com/reference/cstdlib/malloc/) - Reminder what the function does and how it behaves
- [C - Type Casting](https://www.tutorialspoint.com/cprogramming/c_type_casting.htm) - To help understand what `(Element *)` is doing
- [CSC130 - Data Structures and Algorithm Analysis - Section 1.3: Queues & Stacks in Practice Lecture Slide](https://github.com/matt2ology/csus-computer-science-csc/blob/main/csc130-data-structures-and-algorithm-analysis/lectures/3-queues%26StacksinPractice-CSC130-Fall2019.pdf) - A reminder on the Stack Data Structure
- [C – Pointer to Pointer (Double Pointer)](https://www.geeksforgeeks.org/c-pointer-to-pointer-double-pointer/) - **Handling the Top Pointer**

## Chat GPT Generated Python Solution

```python
class Stack:
    def __init__(self, max_size):
        self.items = []
        self.max_size = max_size

    def is_empty(self):
        return len(self.items) == 0

    def is_full(self):
        return len(self.items) >= self.max_size

    def push(self, item):
        if self.is_full():
            raise OverflowError("push to a full stack")
        self.items.append(item)

    def pop(self):
        if self.is_empty():
            raise IndexError("pop from empty stack")
        return self.items.pop()

    def peek(self):
        if self.is_empty():
            raise IndexError("peek from empty stack")
        return self.items[-1]

    def size(self):
        return len(self.items)

    def __str__(self):
        return "Stack: " + str(self.items)

# Example usage:
s = Stack(max_size=3)
s.push(1)
s.push(2)
s.push(3)
print(s)         # Output: Stack: [1, 2, 3]
try:
    s.push(4)    # Should raise an OverflowError
except OverflowError as e:
    print(e)     # Output: push to a full stack
print(s.pop())   # Output: 3
print(s)         # Output: Stack: [1, 2]
print(s.peek())  # Output: 2
print(s.size())  # Output: 2
```
