---
aliases:
note-type: permanent
date-created: 2024-07-01
long-form-date-created: Monday, July 01, 2024
week-created: Week 27.1
time-created: 08:18 PM
---

# Rust cargo check

Related : [Rust Cargo](Rust%20Cargo.md) - [Rust cargo run](Rust%20cargo%20run.md)

Topics : [Rust Programming Language](../../4-hub-notes-🚉/Rust.md)

Is a quick way to validate if one's Rust code is compile-able in its current state.
Rustaceans (those who program in Rust) will periodically run this command
as they write code to check that it can compile.

This is faster than using the `cargo run` command, for it skips creating an
executable.

```sh
cargo check
```
