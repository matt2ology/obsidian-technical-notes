---
kindle-sync:
  bookId: "58465"
  title: "How Linux Works, 3rd Edition: What Every Superuser Should Know"
  author: Brian Ward
  asin: B07X7S1JMB
  lastAnnotatedDate: "2023-10-23"
  bookImageUrl: "https://m.media-amazon.com/images/I/81K+2pqDU-L._SY160.jpg"
  highlightsCount: 10
---

# How Linux Works, 3rd Edition

Topics : [Linux](../4-hub-notes-🚉/Linux.md) - [Operating Systems](../4-hub-notes-🚉/Operating%20Systems.md)

## Metadata

- Author: [Brian Ward](https://www.amazon.comundefined)
- ASIN: B07X7S1JMB
- Reference: https://www.amazon.com/dp/B07X7S1JMB
- [Kindle link](kindle://book?action=open&asin=B07X7S1JMB)

## Highlights

The first edition included historical information that I removed later to improve focus. If you’re interested in Linux and how it relates to the history of Unix, pick up Peter H. Salus’s The Daemon, the Gnu, and the Penguin (Reed Media Services, 2008). — location: [926](kindle://book?action=open&asin=B07X7S1JMB&location=926) ^ref-33602

The recommended book covers how the software we used evolved over time.

### Chapter 1: The Big Picture

[The Three Levels of a Linux System](../3-permanent-notes-🧲/The%20Three%20Levels%20of%20a%20Linux%20System.md)

The most effective way to understand how an operating system works is through abstraction—a fancy way of saying that you can ignore most of the details that make up a piece that you’re trying to understand, and concentrate instead on its basic purpose and operation. — location: [939](kindle://book?action=open&asin=B07X7S1JMB&location=939) ^ref-57434

Can't see the forest for the trees... All too often one may get fixated on a particular component where in it of itself is a whole "process" and is distracted by this instead of understanding "just-enough" to continue the flow of understanding the system as a whole.

#### 1.1 Levels and Layers of Abstraction in a Linux System

[The Difference Between Kernel Mode and User Mode](../3-permanent-notes-🧲/The%20Difference%20Between%20Kernel%20Mode%20and%20User%20Mode.md)

The kernel is software residing in memory that tells the CPU where to look for its next task. Acting as a mediator, the kernel manages the hardware (especially main memory) and is the primary interface between the hardware and any running program. — location: [969](kindle://book?action=open&asin=B07X7S1JMB&location=969) ^ref-62147

The core of the operating system

---

Code running in kernel mode has unrestricted access to the processor and main memory. This is a powerful but dangerous privilege that allows the kernel to easily corrupt and crash the entire system. The memory area that only the kernel can access is called kernel space. — location: [978](kindle://book?action=open&asin=B07X7S1JMB&location=978) ^ref-62449

Because this is the "core" of the operating system the kernel has full access to all resources available.

---

User mode, in comparison, restricts access to a (usually quite small) subset of memory and safe CPU operations. User space refers to the parts of main memory that the user processes can access. — location: [980](kindle://book?action=open&asin=B07X7S1JMB&location=980) ^ref-12523

Adhering to the "principle of least privilege" a user has accesses to a subset of memory and is allowed to execute safe CPU operations. If a user needs to have full access they may go into "Super User" mode. This way "critical" operations of the system and other elements are not affected by errors of the user.

#### 1.2 Hardware: Understanding Main Memory

A CPU is just an operator on memory; it reads its instructions and data from the memory and writes data back out to the memory. — location: [996](kindle://book?action=open&asin=B07X7S1JMB&location=996) ^ref-64624

---

[Process States](../_inbox/Process%20States.md)

the term state in reference to memory, processes, the kernel, and other parts of a computer system. Strictly speaking, a state is a particular arrangement of bits. For example, if you have four bits in your memory, 0110, 0001, and 1011 represent three different states. — location: [997](kindle://book?action=open&asin=B07X7S1JMB&location=997) ^ref-17804

---

it’s common to refer to the state in abstract terms rather than to the actual bits, the term image refers to a particular physical arrangement of bits. — location: [1005](kindle://book?action=open&asin=B07X7S1JMB&location=1005) ^ref-47920

---

#### 1.3 The Kernel

Nearly everything that the kernel does revolves around main memory. One of the kernel’s tasks is to split memory into many subdivisions, and it must maintain certain state information about those subdivisions at all times. Each process gets its own share of memory, and the kernel must ensure that each process keeps to its share. — location: [1008](kindle://book?action=open&asin=B07X7S1JMB&location=1008) ^ref-33161

---

The kernel is in charge of managing tasks in four general system areas: Processes The kernel is responsible for determining which processes are allowed to use the CPU. Memory The kernel needs to keep track of all memory—what is currently allocated to a particular process, what might be shared between processes, and what is free. Device drivers The kernel acts as an interface between hardware (such as a disk) and processes. It’s usually the kernel’s job to operate the hardware. System calls and support Processes normally use system calls to communicate with the kernel. — location: [1010](kindle://book?action=open&asin=B07X7S1JMB&location=1010) ^ref-62231

- [Kernel four areas of system task management](../_inbox/Kernel%20four%20areas%20of%20system%20task%20management.md)

---
