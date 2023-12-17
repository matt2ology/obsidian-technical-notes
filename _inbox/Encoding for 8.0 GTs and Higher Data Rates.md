---
aliases:
note-type: permanent
date-created: 2023-12-01
long-form-date-created: Friday, December 01, 2023
week-created: Week 48.5
time-created: 09:48 AM
---

# Encoding for 8.0 GTs and Higher Data Rates

Related : [PCIe Revision 4](../4-hub-notes-🚉/PCIe%20Revision%204.md)

Topic : [PCI Express](../4-hub-notes-🚉/PCI%20Express.md)

When a PCI Express Link is operating at a data rate of 8.0 GT/s or higher, it uses the
encoding 5 rules described in this subsection: 128b/130b encoding.

For backwards compatibility, the Link initially trains to L0 at the 2.5 GT/s data rate using
8b/10b encoding as described in [Section 4.2.1. Encoding for 2.5 GT/s and 5.0 GT/s Data Rates](Encoding%20for%202.5%20GTs%20and%205.0%20GTs%20Data%20Rates.md),
then when the data rate is changed to 8.0 GT/s or higher, 128b/130b encoding is used.

128b/130b encoding is a Link-wide packetization mechanism and a per-Lane block code
with scrambling. The basic entity of data transmission is an 8-bit data character, referred to
as a Symbol, as shown in 10 Figure 4-11 and Figure 4-12.
