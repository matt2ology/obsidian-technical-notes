---
aliases:
  - Installing the Rust Programming Language
  - Installing Rustlang
note-type: permanent
date-created: 2024-06-28
long-form-date-created: Friday, June 28, 2024
week-created: Week 26.5
time-created: 10:07 PM
---

# Installing Rust

Related : [Updating Rust](Updating%20Rust.md) - [Uninstalling Rust](Uninstalling%20Rust.md) - [Rust Has Local Documentation](Rust%20Has%20Local%20Documentation.md)

Source : [NOTE HUB for Klabnik, Steve; Nichols, Carol. The Rust Programming Language, 2nd Edition. No Starch Press. Kindle Edition.](NOTE%20HUB.md)

Topics : [Rust Programming Language](../4-hub-notes-🚉/Rust.md)

Validate installation by running:

```sh
rustc --version
```

## Installing Rust on Linux or MacOS

1. Download script and start installation of the `rustup`tool: `curl --proto '=https' --tlsv1.3 https://sh.rustup.rs -sSf | sh`
2. A _linker_ will let Rust join its compiled outputs into one file. A C compiler should be installed
   - If a C compiler is needed on MacOS: `xcode-select --install
   - Linux users generally install GCC or Clang respective to their distribution of Linux documentation; for example, Ubuntu uses the `build-essential` package

## Installing Rust on Windows

Instructions can be found here: https://www.rust-lang.org/tools/install

You may need to install the [Visual Studio C++ Build tools](https://visualstudio.microsoft.com/visual-cpp-build-tools/) when prompted to do so.

The build tools include the following

- “Desktop Development with C++”
- The Windows 10 or 11 SDK
- The English language pack component, along with any other language pack of your choosing
