---
aliases:
note-type: permanent
date-created: 2023-10-22
long-form-date-created: Sunday, October 22, 2023
week-created: Week 42.7
time-created: 04:23 PM
---

# The Difference Between Kernel Mode and User Mode

Related : [Linux](../4-hub-notes-🚉/Linux.md) - [Linux Kernel](Linux%20Kernel.md) - [Privilege Level](Privilege%20Level.md)

Source : [Ward-How Linux Works, 3rd Edition](../kindle-highlights/Ward-How%20Linux%20Works,%203rd%20Edition.md)

Topics : [Operating Systems](../4-hub-notes-🚉/Operating%20Systems.md)

The modes, kernel mode and user mode, serve different purposes and have different levels
of privilege and access to system resources.

By separating the user, and the code created, from the core functions of the operating system reduces the "damage" that can be done to the rest of the system.

**Context Switching**: The process of transitioning between kernel mode
and user mode. When a system call or interrupt occurs, the CPU switches from
user mode to kernel mode to execute the relevant code in the kernel and then
switches back to user mode when the kernel mode operation is complete

|                                                    | Kernel Mode                                                                                       | User Mode                                                                                              |
| :------------------------------------------------- | :------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| **Privilege Level** (supervisor or privilege mode) | Highest privilege level in the OS.                                                                | Lower privilege level than Kernel Mode                                                                 |
|                                                    | Has unrestricted access to all system resources and hardware                                      | Is restricted and cannot directly access system resources or hardware                                  |
|                                                    |                                                                                                   | It must make system calls to request services from the kernel                                          |
| **Access to System Resources**                     | Can access and control hardware devices, manage memory, and execute privileged instructions       | Has limited access to system resources                                                                 |
|                                                    | The kernel manages the hardware and provides system services to user-mode applications            | Applications rely on system calls to request services from the kernel                                  |
| **Stability and Security**                         | Has the potential to directly impact system stability and security                                | Is designed to be more isolated and less prone to causing system-wide issues                           |
|                                                    | A bug or malicious code in the kernel can lead to system crashes or vulnerabilities               | Processes are typically sandboxed from each other and the kernel for enhanced security and stability   |
| **Application vs. Operating System**               | Is part of the operating system itself                                                            | Includes all user-space application and process that run on top of the operating system                |
|                                                    | Is responsible for managing system resources and providing services to the user-mode applications | Helps ensure system stability, security and resource protection by limiting what user-mode code can do |
|                                                    |                                                                                                   | Provide a controlled interface for user applications to interact with the operating system's kernel    |
