---
kindle-sync:
  bookId: "58465"
  title: "How Linux Works, 3rd Edition: What Every Superuser Should Know"
  author: Brian Ward
  asin: B07X7S1JMB
  lastAnnotatedDate: "2023-10-22"
  bookImageUrl: "https://m.media-amazon.com/images/I/81K+2pqDU-L._SY160.jpg"
  highlightsCount: 5
---

# How Linux Works, 3rd Edition

## Metadata

- Author: [Brian Ward](https://www.amazon.comundefined)
- ASIN: B07X7S1JMB
- Reference: https://www.amazon.com/dp/B07X7S1JMB
- [Kindle link](kindle://book?action=open&asin=B07X7S1JMB)

## Highlights

The first edition included historical information that I removed later to improve focus. If you’re interested in Linux and how it relates to the history of Unix, pick up Peter H. Salus’s The Daemon, the Gnu, and the Penguin (Reed Media Services, 2008). — location: [926](kindle://book?action=open&asin=B07X7S1JMB&location=926) ^ref-33602

The recommended book covers how the software we used evolved over time.

---

The most effective way to understand how an operating system works is through abstraction—a fancy way of saying that you can ignore most of the details that make up a piece that you’re trying to understand, and concentrate instead on its basic purpose and operation. — location: [939](kindle://book?action=open&asin=B07X7S1JMB&location=939) ^ref-57434

Can't see the forest for the trees... All too often one may get fixated on a particular component where in it of itself is a whole "process" and is distracted by this instead of understanding "just-enough" to continue the flow of understanding the system as a whole.

---

The kernel is software residing in memory that tells the CPU where to look for its next task. Acting as a mediator, the kernel manages the hardware (especially main memory) and is the primary interface between the hardware and any running program. — location: [969](kindle://book?action=open&asin=B07X7S1JMB&location=969) ^ref-62147

The core of the operating system

---

Code running in kernel mode has unrestricted access to the processor and main memory. This is a powerful but dangerous privilege that allows the kernel to easily corrupt and crash the entire system. The memory area that only the kernel can access is called kernel space. — location: [978](kindle://book?action=open&asin=B07X7S1JMB&location=978) ^ref-62449

Because this is the "core" of the operating system the kernel has full access to all resources available.

---

User mode, in comparison, restricts access to a (usually quite small) subset of memory and safe CPU operations. User space refers to the parts of main memory that the user processes can access. — location: [980](kindle://book?action=open&asin=B07X7S1JMB&location=980) ^ref-12523

Adhering to the "principle of least privilege" a user has accesses to a subset of memory and is allowed to execute safe CPU operations. If a user needs to have full access they may go into "Super User" mode. This way "critical" operations of the system and other elements are not affected by errors of the user.

---
