---
aliases:
note-type: permanent
date-created: 2024-02-11
long-form-date-created: Sunday, February 11, 2024
week-created: Week 06.7
time-created: 08:52 PM
---

# How Kotlin Programs work According to [Android Advanced Training Consultants](Android%20Advanced%20Training%20Consultants.md)

Related : [Kotlin Programming Language](Kotlin%20Programming%20Language.md)

The Kotlin Source Code is developed with an [Integrated Development Environment {IDE}](Integrated%20Development%20Environment), the Class files are then then run in the [Java Runtime Environment (JRE)](Java%20Runtime%20Environment).
The JRE has a "Class Loader" that is responsible for receiving the class file and executing in
via the "Execution Engine" of the JRE (i.e. the software to execute the Kotlin files: the [Java Development Kit (JDK)](Java%20Development%20Kit)).

The [JDK](Java%20Development%20Kit) software includes the part responsible for running Kotlin code and sends the result to the Operating System.

All together:

1. The Kotlin Source Code is developed in an [Integrated Development Environment](Integrated%20Development%20Environment.md)
2. The [JDK](Java%20Development%20Kit.md) includes the Kotlin compiler and the [JRE](Java%20Runtime%20Environment.md)
3. The [IDE](Integrated%20Development%20Environment.md) provides all the quality of life tooling and features to develop for the targeted language and/or platform; for example, it has a Java Debugger.
4. The Class file is then fed into the [JRE](Java%20Runtime%20Environment.md) that has set of libraries and other files
   1. In the [JRE](Java%20Runtime%20Environment.md) is the [Java Virtual Machine (JVM)](Java%20Virtual%20Machine) that leverages the Class Loader, feeds the output to [Byte Code](Byte%20Code) and is then fed into the Execution Engine
5. The result is then output to the corresponding Operating System (Windows, Linux, etc....)
