---
aliases:
note-type: permanent
date-created: 2024-05-27
long-form-date-created: Monday, May 27, 2024
week-created: Week 22.1
time-created: 06:09 PM
---

# 20200720 Technical Interview Template

Related :

| Topic                                                                      | Ideal (3 points)                                                                                                                                                                                                                                                                                                                                | Minimal (1 point)                                                                                                                                                                                                                                             | Weight (developer profile) | Weight (validation profile) |
| -------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------- | --------------------------- |
| Simple programming (absorb spec and code)<br><br>Fizzbuzz or "linked list" | Successful answer<br><br>1. Absorbed/understood requirements.<br>2. Successfully transferred into logic<br>3. No help required. (Specification questions are allowed)<br><br>Mentions built-in testability without prompting.                                                                                                                   | Can arrive at a guided solution.                                                                                                                                                                                                                              | 15%                        | 15%                         |
| Tactical Testability (as part of practical question)                       | Categorize points of failure and provide tests<br><br>1. Can speak to test coverage<br>2. How to apply in a testing strategy                                                                                                                                                                                                                    | Rational thought about testing:<br><br>1. Interesting test parameters and why (objective of test) (typical, exceptions, do you need to test every number)<br>2. How to construct a test                                                                       | 15%                        | 15%                         |
| Testing Strategies                                                         | Can describe test strategies under constrained resources (e.g. time, equipment)<br><br>Can describe how to increase test capacity and reproducibility.<br>(e.g. multiple instances of the same failures. Repository deltas, release notes.)<br>Aware of how to generate high quality sightings.                                                 | Can describe at least one way to testing more efficient in a complex org environment.                                                                                                                                                                         |                            | 15%                         |
| Bit manipulation programming                                               | Tests whether you've ever needed to use a bitwise operator.<br><br>Immediate knowledge                                                                                                                                                                                                                                                          | Coached into solution<br><br>(Or-case only)                                                                                                                                                                                                                   | 7.5%                       | 5%                          |
| Test driven development                                                    | Has developed in an environment where developer is responsible for tests as part of their "done" criteria                                                                                                                                                                                                                                       | Evidence they are willing to adopt testing as part of "done" criteria.                                                                                                                                                                                        | 7.5%                       | 15%                         |
| Real time/RTOS/IPC                                                         | Has debugged and resolved issues arising due to RTOS stacks.                                                                                                                                                                                                                                                                                    | Can describe IPC and RTOS concepts. Could include:<br><br>1. Mutex, semaphore, spin lock<br>2. Threads and processes<br>3. Priority inversion<br>4. Virtualization<br>5. ISRs and Interrupts                                                                  | 10%                        | 5%                          |
| HW interfaces                                                              | Proficient at using register interfaces and DMAs.<br><br>Proficient at memory management<br><br>1. Can describe pitfalls.<br>2. Does very well at linked list or memory related problems.<br>3. Perfectly describes stack, heap, bss, data, text \[note Aaron screens for basic knowledge of this concept, along with 'static' and 'volatile'\] | Awareness of how to interface with hardware. (e.g. memory mapped registers or port-based IO)<br><br>Aspects of memory management<br><br>1. Knows what a pointer is, and be aware of potential pitfalls.<br>2. Is aware of concept of 'malloc/free/new/delete' | 7.5%                       | 5%                          |
| HW protocols                                                               | Can describe HW protocol in depth or, has led implementation of attached protocol stack.                                                                                                                                                                                                                                                        | \<No score\>                                                                                                                                                                                                                                                  | 7.5%                       | 5%                          |
| SW quality                                                                 | Emphasis on importance.<br><br>Has used 3+ of the list:<br><br>1. Static test<br>2. Code coverage<br>3. Code review<br>4. Performance analysis                                                                                                                                                                                                  | Interested/willing to use, at a minimum:<br><br>1. Coding standard<br>2. Code reviews<br>3. Revision control<br>4. Ticketing systems<br>5. Continuous Integration                                                                                             | 8%                         | 10%                         |
| Specifications and Requirements analysis                                   | Has deconstructed a high-level spec into a lower-level spec for a successful project.<br><br>Requirements have been successfully absorbed by a test/validation team.<br><br>Designed and deployed an API.                                                                                                                                       | Can speak conceptually about why requirements are necessary                                                                                                                                                                                                   | 8%                         | 10%                         |
| Refactoring                                                                | Regularly refactors on the fly.<br><br>Has successfully planned and refactored large modules that delivered critical value to an org.                                                                                                                                                                                                           | Can conceptually describe when refactoring is useful and not useful.                                                                                                                                                                                          | 4%                         | 0%                          |
| Python or equivalent (Perl, TCL, other)                                    | Evidence of 2-5 year of experience with:<br><br>1. Workflow automation<br>2. Application dev<br>3. Test dev                                                                                                                                                                                                                                     | Has used python or other sparingly.                                                                                                                                                                                                                           | 4%                         | 0%                          |
| SCM repositories/branching/merging                                         | Has implemented or resolved complex repository issues                                                                                                                                                                                                                                                                                           | Has used Git or other                                                                                                                                                                                                                                         | 3%                         | 0%                          |
| Build methodologies (project files, make, gradle)                          | Has tackled/resolved complex build environment issues                                                                                                                                                                                                                                                                                           | Has built SW from a blank project.                                                                                                                                                                                                                            | 3%                         | 0%                          |