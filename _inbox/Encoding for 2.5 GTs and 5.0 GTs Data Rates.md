---
aliases:
  - 4.2.1. Encoding for 2.5 GT/s and 5.0 GT/s Data Rates
note-type: permanent
week-created: Week 48.5
date-created: 2023-12-01
long-form-date-created: Friday, December 01, 2023
time-created: 08:59 AM
source:
---

# Encoding for 2.5 GTs and 5.0 GTs Data Rates

Related : [PCIe Revision 4](../4-hub-notes-🚉/PCIe%20Revision%204.md)

Topics : [PCI Express](../4-hub-notes-🚉/PCI%20Express.md)

## 4.2.1.1. Symbol Encoding

PCI Express uses an 8b/10b transmission code. The transmission code is the same as ones
defined in ANSI X3.230-1994, clause 11 (and also IEEE 802.3z, 36.2.4).

Using this scheme, 8-bit data characters are treated as 3 bits and 5 bits mapped onto a 4-bit
code group
