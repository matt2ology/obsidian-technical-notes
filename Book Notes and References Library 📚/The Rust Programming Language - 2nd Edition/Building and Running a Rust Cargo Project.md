---
note-type: literature
date-created: 2024-07-01
long-form-date-created: Monday, July 01, 2024
week-created: Week 27.1
time-created: 04:11 PM
author:
---

# Building and Running a Rust Cargo Project

Related : [Creating a Rust Project with Cargo](Creating%20a%20Rust%20Project%20with%20Cargo.md) - [In Rust Compiling and Running Are Separate Steps](In%20Rust%20Compiling%20and%20Running%20Are%20Separate%20Steps.md) - [What is Cargo.lock](What%20is%20Cargo.lock.md) - [What is Rusts cargo check](What%20is%20Rusts%20cargo%20check.md) - [Rust Cargo](Rust%20Cargo.md)

Source : [NOTE HUB for Klabnik, Steve; Nichols, Carol. The Rust Programming Language, 2nd Edition. No Starch Press. Kindle Edition.](NOTE%20HUB.md)

Topics : [Rust Programming Language](../../4-hub-notes-🚉/Rust.md)

## Building the Project

Using Cargo to build the project folder, instead of a single source file using
`rustrc main.rs`, will create a target/debug folder.

```sh
cargo build
```

In Rust the default build is a debug build and so Cargo puts the
binary/executable into a directory named "debug".

When running `cargo build` for the first time Cargo will create a file named
`Cargo.lock` at the top level of the project folder directory.

## Running the Project

One can also **compile the code and then run** the respective platform
executable with the following command.

```sh
cargo run
```

This command only re-builds source code that has been modified

### Run the Executable (don't re-build source code)

Alternatively one can from the project directory you can run the
binary/executable by typing the following

On Linux

```sh
./target/debug/<project name>
```

On Windows

```pwsh
.\target\debug\<project name>.exe
```

## Sanity check

Cargo also has the following command. It will validate if the project is able
to produce an executable (i.e. it check if the source code can be compiled).
The command won't produce an executable as `cargo run` would have done.

```sh
cargo check
```

This is much faster than doing a while build process because it skips making an
executable.
