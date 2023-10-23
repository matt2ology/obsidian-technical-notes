---
aliases:
note-type: permanent
date-created: 2023-10-22
long-form-date-created: Sunday, October 22, 2023
week-created: Week 42.7
time-created: 07:04 PM
---

# Processes

Related : [Kernel four areas of system task management](Kernel%20four%20areas%20of%20system%20task%20management.md) - [Linux Kernel](../3-permanent-notes-🧲/Linux%20Kernel.md) - [Process vs. Program](../3-permanent-notes-🧲/Process%20vs.%20Program.md) [Process States](Process%20States.md)

Is an "active", is alive, is a program in execution!

A program becomes a process when the executable file is loaded into [memory](Memory.md) - ready to be
granted processor time.

![Execution of a program](Execution%20of%20a%20program.md)

## Key Notes

- A process is a program in execution under [OS](../4-hub-notes-🚉/Operating%20Systems.md) control
- The [OS](../4-hub-notes-🚉/Operating%20Systems.md) executes and manages processes in various modes:
  - [Supervisor mode](Privilege%20Level.md) - to mange [OS's](../4-hub-notes-🚉/Operating%20Systems.md) resource, [user process](User%20Space.md)
  - [Batch mode](Batch%20mode) - user jobs to be executed without user interaction
  - [Time-shared mode](Time-shared%20mode) - user interacts with running software
- Various process components:
  1. Program code (in antique IBM terms: text section).
  2. Hardware resources, including [registers](registers), [static memory](static%20memory), [stack](stack.md), [heap](heap.md)
  3. [Stack](stack.md) containing temporary and local data, varies in size during run, grows at call, shrinks at return, starts and ends at ~0 size
  4. Functions and function parameters, return address, local objects
  5. Data section containing global objects; possibly shared
  6. Files for data to be read (input) and generated (output)

The running programs that the kernel manages: collectively make up the system's upper
level called [user space](User%20Space.md).
