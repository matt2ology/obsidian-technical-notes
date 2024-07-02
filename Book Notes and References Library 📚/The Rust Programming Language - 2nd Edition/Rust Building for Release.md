---
note-type: literature
date-created: 2024-07-01
long-form-date-created: Monday, July 01, 2024
week-created: Week 27.1
time-created: 08:47 PM
author:
---

# Rust Building for Release

Related : [Rust Cargo](Rust%20Cargo.md) - [Rust cargo build](Rust%20cargo%20build.md)

Source : [NOTE HUB for Klabnik, Steve; Nichols, Carol. The Rust Programming Language, 2nd Edition. No Starch Press. Kindle Edition.](NOTE%20HUB.md)

Topics : [Rust Programming Language](../../4-hub-notes-🚉/Rust.md)

When the project is ready for release use `cargo build` command with flag
option `--release`. This will make a new directory `target/release` and
generate the build executable in that path.

Without the `--release` flag it will place the build executable in `target/debug`
in the project's directory.

**Note**: that when building a release version of the build the build will take longer;
for, Rust will make optimizations when compiling and creating the executable.
This is the version of executable to be given to users of your program.

If you are benchmarking use the executable located in `target/release`.

```sh
cargo build --release
```
