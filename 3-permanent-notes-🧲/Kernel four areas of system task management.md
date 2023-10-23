---
aliases:
note-type: permanent
date-created: "2023-10-22"
long-form-date-created: "Sunday, October 22, 2023"
week-created: "Week 42.7"
time-created: "06:56 PM"
---

# Kernel four areas of system task management

Created from : [Ward-How Linux Works, 3rd Edition](../kindle-highlights/Ward-How%20Linux%20Works,%203rd%20Edition.md)

Related : [Linux Kernel](../3-permanent-notes-🧲/Linux%20Kernel.md)

1. [Processes](Processes.md)
2. [Memory](Memory.md)
3. [Device drivers](Device%20drivers)
4. [System calls and support](System%20calls%20and%20support)

## Quote and citation

The kernel is in charge of managing tasks in four general system areas:

- Processes The kernel is responsible for determining which processes are allowed to use the CPU.
- Memory The kernel needs to keep track of all memory—what is currently allocated to a particular process, what might be shared between processes, and what is free.
- Device drivers The kernel acts as an interface between hardware (such as a disk) and processes. It’s usually the kernel’s job to operate the hardware.
- System calls and support Processes normally use system calls to communicate with the kernel. — location: [1010](kindle://book?action=open&asin=B07X7S1JMB&location=1010) ^ref-62231
