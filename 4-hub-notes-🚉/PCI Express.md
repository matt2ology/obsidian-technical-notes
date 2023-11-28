---
aliases:
  - Peripheral Component Interconnect Express
note-type: hub
tags:
  - hub
---

# PCI Express

Related :

- [Hardware](Hardware.md)
- [PCIe 4.0](PCIe%20Revision%204.md)

Topics :

PCI Express is a high performance, general purpose I/O interconnect defined for a wide
variety of future computing and communication platforms.

## Key PCI attributes

### Usage model

"Usage model" refers to how the technology is intended to be employed or
utilized in a computing system. It encompasses the overall approach, methodology,
and scenarios in which PCI Express is designed to operate and interact with other
components within a computer or communication platform.

- **Data transfer paradigm**: allow point-to-point serial connection - replaces
  parallel bus architecture used in earlier PCI (Peripheral Component Interconnect)
- **Scalability**: allow for different lane configurations and data rates to
  meet the needs of various applications.
- **Connectivity**: various peripheral devices (e.g. graphics cards,
  storage devices, network interfaces) to the motherboard or other host devices
- **Software interfaces**: describes how software interacts with the PCI
  Express architecture (the spec)

### Load-store architecture

The term "load-store architecture" refers to a computer architecture design in
which data is explicitly moved between memory and processor registers through
load and store instructions.

In a load-store architecture, operations are performed only on data that has
been loaded from memory into registers, and the results of these operations are
stored back to memory.

1. Load Instruction
2. Store Instruction
3. Data Processing
