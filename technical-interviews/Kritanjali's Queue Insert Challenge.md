---
aliases:
note-type: permanent
date-created: 2024-05-29
long-form-date-created: Wednesday, May 29, 2024
week-created: Week 22.3
time-created: 08:24 AM
---

# Kritanjali's Queue Insert Challenge

Related : [Kritanjali's Stack Challenge](../technical-interviews/Kritanjali's%20Stack%20Challenge.md) - [Queue Data Structure](Queue%20Data%20Structure)

Topic : [Data Structures](Data%20Structures)

> Kritanjali Balakrishnan - Wed 5/29/2024 6:29 AM
>
> > Very good. Now please implement a queue insert function, accounting for
> > full queue and empty queue conditions. Please just write up the individual
> > functions, they do not need to be executed (no need for header file
> > inclusions etc.). Write the functions on a whiteboard and take pics and send
> > to me.
> >
> > I want to see your functions this morning

Do it in Python if that's easier, i want to see you demonstrate knowledge of the data 
structure this time, along with speed and whiteboarding; and then, do it in C
(just the insert function) use array or pointers, your call.

## My Implementation

```c
void
```

![Python Whiteboarding Solution](../attachments/Pasted%20image%2020240529141841.png)

## Generated Python Solution

```python
class Queue:
    def __init__(self, max_size: int):
        self.items: list = []
        self.max_size: int = max_size

    def is_empty(self) -> bool:
        return len(self.items) == 0

    def is_full(self) -> bool:
        return len(self.items) >= self.max_size

    def enqueue(self, item) -> None:
        if self.is_full():
            raise OverflowError("enqueue to a full queue")
        self.items.append(item)

    def dequeue(self) -> int:
        if self.is_empty():
            raise IndexError("dequeue from empty queue")
        return self.items.pop(0)

    def peek(self) -> int:
        if self.is_empty():
            raise IndexError("peek from empty queue")
        return self.items[0]

    def size(self) -> int:
        return len(self.items)

    def __str__(self) -> str:
        return "Queue: " + str(self.items)

# Example usage:
print("Queue Example:")
q = Queue(max_size=3)
print("enqueue 1")
q.enqueue(1)
print("enqueue 2")
q.enqueue(2)
print("enqueue 3")
q.enqueue(3)
print(q) # Output: Print Queue: [1, 2, 3]
try:
    print("Enqueue:", q.enqueue(4))
except OverflowError as e:
    print(e)     # Output: enqueue to a full queue
print("Dequeue:", q.dequeue()) # Output: Dequeue: 1
print(q) # Output: Print Queue: [2, 3]
print("Peek Queue: (front element)", q.peek()) # Output: Peek Queue: (front element) 2
print("Size of Queue:", q.size()) # Output: Size of Queue: 2
```
## Generated C Solution

Creating a queue data structure from scratch in C involves defining the queue and its operations: enqueue, dequeue, and display. We'll use a linked list to implement the queue to allow for dynamic memory allocation.

Here's a step-by-step implementation:

### Step 1: Define the Queue Structure

First, we define the structure for the queue.

```c
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

#define MAX 100  // Define the maximum size of the queue

struct Queue {
    int items[MAX];
    int front;
    int rear;
};
```

### Step 2: Initialize the Queue

We create a function to initialize the queue.

```c
struct Queue* createQueue() {
    struct Queue* q = (struct Queue*)malloc(sizeof(struct Queue));
    q->front = -1;
    q->rear = -1;
    return q;
}
```

### Step 3: Check if the Queue is Full

We create a function to check if the queue is full.

```c
bool isFull(struct Queue* q) {
    if ((q->rear + 1) % MAX == q->front) {
        return true;
    }
    return false;
}
```

### Step 4: Check if the Queue is Empty

We create a function to check if the queue is empty.

```c
bool isEmpty(struct Queue* q) {
    if (q->front == -1) {
        return true;
    }
    return false;
}
```

### Step 5: Enqueue Operation

The enqueue operation adds a new element to the rear of the queue.

```c
void enqueue(struct Queue* q, int value) {
    if (isFull(q)) {
        printf("Queue is full\n");
        return;
    }
    if (q->front == -1) {
        q->front = 0;
    }
    q->rear = (q->rear + 1) % MAX;
    q->items[q->rear] = value;
    printf("Inserted %d\n", value);
}
```

### Step 6: Dequeue Operation

The dequeue operation removes an element from the front of the queue.

```c
int dequeue(struct Queue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return -1;
    }
    int item = q->items[q->front];
    if (q->front == q->rear) {
        q->front = -1;
        q->rear = -1;
    } else {
        q->front = (q->front + 1) % MAX;
    }
    return item;
}
```

### Step 7: Display Queue

We create a function to display the elements of the queue.

```c
void displayQueue(struct Queue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return;
    }
    int i = q->front;
    while (i != q->rear) {
        printf("%d -> ", q->items[i]);
        i = (i + 1) % MAX;
    }
    printf("%d\n", q->items[i]);
}
```

### Full Implementation

Here's the complete code putting all these pieces together:

```c
#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

#define MAX 100  // Define the maximum size of the queue

// Queue structure
struct Queue {
    int items[MAX];
    int front;
    int rear;
};

// Function to create a queue
struct Queue* createQueue() {
    struct Queue* q = (struct Queue*)malloc(sizeof(struct Queue));
    q->front = -1;
    q->rear = -1;
    return q;
}

// Function to check if the queue is full
bool isFull(struct Queue* q) {
    if ((q->rear + 1) % MAX == q->front) {
        return true;
    }
    return false;
}

// Function to check if the queue is empty
bool isEmpty(struct Queue* q) {
    if (q->front == -1) {
        return true;
    }
    return false;
}

// Function to add an element to the queue
void enqueue(struct Queue* q, int value) {
    if (isFull(q)) {
        printf("Queue is full\n");
        return;
    }
    if (q->front == -1) {
        q->front = 0;
    }
    q->rear = (q->rear + 1) % MAX;
    q->items[q->rear] = value;
    printf("Inserted %d\n", value);
}

// Function to remove an element from the queue
int dequeue(struct Queue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return -1;
    }
    int item = q->items[q->front];
    if (q->front == q->rear) {
        q->front = -1;
        q->rear = -1;
    } else {
        q->front = (q->front + 1) % MAX;
    }
    return item;
}

// Function to display the elements of the queue
void displayQueue(struct Queue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return;
    }
    int i = q->front;
    while (i != q->rear) {
        printf("%d -> ", q->items[i]);
        i = (i + 1) % MAX;
    }
    printf("%d\n", q->items[i]);
}

// Main function to test the queue implementation
int main() {
    struct Queue* q = createQueue();

    enqueue(q, 10);
    enqueue(q, 20);
    enqueue(q, 30);
    enqueue(q, 40);

    printf("Queue: ");
    displayQueue(q);

    printf("Dequeued: %d\n", dequeue(q));
    printf("Queue after dequeue: ");
    displayQueue(q);

    free(q);
    return 0;
}
```

### Explanation

1. 1. **Queue Structure**: Defines the queue with an array `items`, and two integers `front` and `rear` to keep track of the front and rear positions.
2. **createQueue**: Initializes the queue with `front` and `rear` set to `-1`.
3. **isFull**: Checks if the queue is full.
4. **isEmpty**: Checks if the queue is empty.
5. **enqueue**: Adds a value to the rear of the queue and handles circular wrapping.
6. **dequeue**: Removes a value from the front of the queue and handles circular wrapping.
7. **displayQueue**: Displays the elements of the queue from front to rear.

This implementation ensures that the queue operates efficiently within the bounds of the fixed-size array using circular indexing.
