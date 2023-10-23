---
aliases:
note-type: permanent
date-created: "2023-10-23"
long-form-date-created: "Monday, October 23, 2023"
week-created: "Week 43.1"
time-created: "02:06 AM"
---

# Process States

Created from : [[Ward-How Linux Works, 3rd Edition]]

Related : [Processes](Processes.md)

Source : [CSUS CSC 193 Chapter 3 Slide 11](../readme-attachments/csus_csc139_herbert_g_mayer_chapter03_process.pdf)

Topics : [Operating System Principles](../4-hub-notes-🚉/Operating%20Systems.md)

While a process executes, over time it changes state

- new: Process is crated by loading from disk into memory
- running: Instructions are being executed on a CPU
- waiting: Process is waiting for some event to occur on its behalf; data input, or another
  event; may change priority while waiting
- ready: Process is waiting to be assigned to a processor (i.e. it is ready to run but not yet running, as it has not been granted a CPU)
- terminated: Process has completed execution; its whole memory space is being freed; all other resources will be re-acquired by [OS](../4-hub-notes-🚉/Operating%20Systems.md); PID will be purged

## Quote and Citation

the term state in reference to memory, processes, the kernel, and other parts of a computer system. Strictly speaking, a state is a particular arrangement of bits. For example, if you have four bits in your memory, 0110, 0001, and 1011 represent three different states. — location: [997](kindle://book?action=open&asin=B07X7S1JMB&location=997) ^ref-17804
