---
note-type: question
date-created: 2024-07-01
long-form-date-created: Monday, July 01, 2024
week-created: Week 27.1
time-created: 04:27 PM
author:
---

# What is Cargo.lock

Related :

- [Building and Running a Rust Cargo Project](Building%20and%20Running%20a%20Rust%20Cargo%20Project.md)
- [What is Cargo in Rust](What%20is%20Cargo%20in%20Rust.md)
- [What is Rust Cargo.toml](What%20is%20Rust%20Cargo.toml.md)

Source : [NOTE HUB for Klabnik, Steve; Nichols, Carol. The Rust Programming Language, 2nd Edition. No Starch Press. Kindle Edition.](NOTE%20HUB.md)

Topics : [Rust Programming Language](../../4-hub-notes-🚉/Rust.md)

`Cargo.lock` is created at the top level directory of the project file.

`Cargo.lock` keeps track of the exact versions of dependencies within
the project. This file is automatically managed by Rust's Cargo tool
(i.e. don't touch this file).
