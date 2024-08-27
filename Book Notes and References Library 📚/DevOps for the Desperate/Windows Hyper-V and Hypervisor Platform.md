---
aliases:
note-type: permanent
date-created: 2024-08-20
long-form-date-created: Tuesday, August 20, 2024
week-created: Week 34.2
time-created: 05:43 PM
---

# Windows Hyper-V and Hypervisor Platform

Related : [VirtualBox](../../3-permanent-notes-🧲/VirtualBox.md)

Windows Hyper-V and Hypervisor Platform are related but distinct technologies
in the Windows ecosystem.

**Windows Hyper-V:**

- Hyper-V is a virtualization technology developed by Microsoft. It's a type-1 hypervisor
  that allows you to create and manage virtual machines on a physical host machine.
  Hyper-V provides a virtual environment where you can run multiple operating systems
  simultaneously on a single physical machine.
- It's available as a feature in Windows Server editions and in certain editions
  of Windows 10 and Windows 11 (like Pro and Enterprise).

**Hypervisor Platform:**

- The Hypervisor Platform is a Windows feature that provides a set of interfaces
  for third-party virtualization solutions to leverage hardware-assisted
  virtualization. It's essentially a compatibility layer that allows other
  virtualization technologies, such as VMware Workstation or VirtualBox, to run
  on top of Windows using the same hardware virtualization support that Hyper-V
  uses.
- When the Hypervisor Platform is enabled, it helps other virtualization products
  to work more seamlessly with the underlying hardware and can be useful in
  scenarios where you need to run multiple virtualization platforms concurrently.

In summary, while both are related to virtualization, Hyper-V is a specific
hypervisor provided by Microsoft, whereas the Hypervisor Platform is a more
general feature that supports other virtualization solutions by providing access
to hardware virtualization capabilities.
