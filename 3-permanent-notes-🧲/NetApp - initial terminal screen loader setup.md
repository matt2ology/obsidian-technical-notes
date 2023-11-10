---
aliases:
note-type: permanent
date-created: "2023-11-10"
long-form-date-created: "Friday, November 10, 2023"
week-created: "Week 45.5"
time-created: "01:04 PM"
---

# NetApp - initial terminal screen loader setup

Created from : [NetApp A800](NetApp%20A800.md)

Related : [NetApp](../4-hub-notes-🚉/NetApp.md)

## Initial terminal screen loader setup

Setting up your screens

Have two terminals opened up with it's own node instance. The convention is that you have the a node instance named "LOADER-A" (i.e. node 1) and "LOADER-B" (i.e. node 2).

To set up two terminal instances (one left and one right) in your window

1. 11520 is your baud rate?
2. Left terminal Instance: `screen /dev/ttyUSB0 115200 -S LOADER-A`
3. Right terminal Instance: `screen /dev/ttyUSB1 11520 -S LOADER-B`
