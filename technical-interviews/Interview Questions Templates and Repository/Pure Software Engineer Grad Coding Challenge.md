---
aliases:
note-type: permanent
date-created: 2024-07-24
long-form-date-created: Wednesday, July 24, 2024
week-created: Week 30.3
time-created: 01:49 PM
---

# Pure Software Engineer Grad Coding Challenge

Related :

You've been invited to take the software engineering challenge for Pure Storage's grad role! Here's what you can expect—

- Challenge time: 75 minutes
- Format: 8 total questions ranging from multiple choice, sentence completion, and coding
- Content, in no particular order: Concurrency, algorithms, data structures, general problem solving, math, and logic
- Important tips:
  - Once the challenge has begun, you will not be able to pause or stop the assessment until it is completed or the time has expired.
  - The coding questions are weighted heavier, so please manage your time appropriately
  - When in doubt, don't overthink or be too clever! You can receive partial credit for even the most basic solutions

Barring any major holidays, the team aims to update you on next steps within 1 week of your completed submission. Best of luck!!

Duration: 75 min
Start Login Date/Time: 1 Jul 2024 12:00 AM PDT (America - Los Angeles)
End Login Date/Time: 31 Jul 2024 12:00 AM PDT (America - Los Angeles)

## Q3

Complete the blanks in the following question with the appropriate answer

Luke has just bought 7 disk drives and grouped them together into a single logical drive so he could back up all funny cat pictures from the internet.
Luke's drive usage can be described as a sustained workload of 200,000 write operations per second with following distribution:

1.  512 bytes 20% of all operations
2.  1024 bytes - 30% of all operations
3.  4096 bytes - 40% of all operations
4.  16384 bytes 10%6 of all operations
    Each write operation appends sequentially to an individual drive, and the load is evenly distributed among all drives.
    There is no compression, garbage collection, or redundancy elimination involved.
    Assuming each drive has a capacity of exactly 513 GiB (1 GiB = 1024 MiB, 1 MiB = 1024 KiB, KiB = 1024 bytes), how soon will Luke's array be filled from completely empty to 86% (at that point, Luke should probably consider buying few more disks)?
    Please round the answer to minutes.

## Q4

struct Node
{
int value;
Node _ parent;
Node _ left_child;
Node \* right_child;
bool visited;
};

Node _ dfs(Node _ node, int target){
printf("% d", node->value);
node->visited = true;

if(node->value == target){
return node;
}

Node \* nodes[3] = {node->right_child, node->parent, node->left_child};

for(int i=0; i <3; ++i){
if(nodes[i]) && !nodes[i]->visited){
Node \* result = dfs(node[i], target);
if(result){
return result;
}
}
}
return NULL;
}

What will the program output be for the above tree when dfs() is called for node 11 and target is 12?

![](../../attachments/Pasted%20image%2020240724135210.png)

## Q5

Complete the blanks in the following question with the appropriate Suppose you want to store the following properties per each memory page

1. Page status - one of:
   a) in use (has some useful data)
   b) Dirty (stored data previously: ready to be reused)
   c) Free (never stored data)
2. Page index- an integer in range [0 .. 364847]
3. Access mode - one of:
   a) Read-only
   b) Write-only
   c) Execute-only
   d) Can read and write
   e) can read and execute
   f) Can read, write, and execute
4. Process ID - an integer in range [0 .. 37337] storing the process ID the page is allocated to

Assuming we need to keep the direct field access API as simple as possible (e.g. we can't have an additional compression layer), what is the minimal number of bytes we need to store a single record?

## Q6

`def check_log_history(events):`
