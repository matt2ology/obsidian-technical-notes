---
aliases:
note-type: permanent
date-created: 2024-07-01
long-form-date-created: Monday, July 01, 2024
week-created: Week 27.1
time-created: 08:42 PM
---

# Rust cargo build

Related : [Rust Cargo](Rust%20Cargo.md) - [Building and Running a Rust Cargo Project](Building%20and%20Running%20a%20Rust%20Cargo%20Project.md) - [In Rust Compiling and Running Are Separate Steps](In%20Rust%20Compiling%20and%20Running%20Are%20Separate%20Steps.md) - [Rust cargo run](Rust%20cargo%20run.md) - [Rust Building for Release](Rust%20Building%20for%20Release.md)

Topics : [Rust Programming Language](../../4-hub-notes-🚉/Rust.md)

By default Rust will create a debug build executable in the following path:
`projectName\target\debug\projectName.exe`

No optimizations are made when building and creating the executable.
This is best during development where frequency of and quick build times
are of priority.

```sh
cargo build
```
