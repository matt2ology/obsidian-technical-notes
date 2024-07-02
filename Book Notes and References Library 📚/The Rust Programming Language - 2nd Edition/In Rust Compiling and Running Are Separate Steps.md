---
aliases:
note-type: permanent
date-created: 2024-07-01
long-form-date-created: Monday, July 01, 2024
week-created: Week 27.1
time-created: 12:43 PM
---

# In Rust Compiling and Running Are Separate Steps

Related :

Source : [NOTE HUB for Klabnik, Steve; Nichols, Carol. The Rust Programming Language, 2nd Edition. No Starch Press. Kindle Edition.](NOTE%20HUB.md)

Topics : [Rust Programming Language](../4-hub-notes-🚉/Rust.md)

Rust is an "ahead-of-time" compiled language. This allows one to create an
executable from source code and share the executable.

## Compiling the Program

Rust compiles code with the `rustc` command and is followed by the name of the
source file. This is similar to C/C++ `gcc` or `clang`.
This will produce a binary executable.

```sh
rustc main.rs
```

On Windows a debugging information file with the extension `.pdb` will also be
produced.

The command `rustc` is good for simple programs, but as one's source files
grows and the the complexity of all the files become more intricate Rust uses
`Cargo`.

## Running the Program

To execute, or run the program, it is as follows:

### On Linux

```sh
./main
```

### On Windows

```sh
.\main.exe
```
