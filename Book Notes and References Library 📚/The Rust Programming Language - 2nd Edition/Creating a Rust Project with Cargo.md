---
note-type: literature
date-created: 2024-07-01
long-form-date-created: Monday, July 01, 2024
week-created: Week 27.1
time-created: 02:29 PM
author:
---

# Creating a Rust Project with Cargo

Related :

- [Building and Running a Rust Cargo Project](Building%20and%20Running%20a%20Rust%20Cargo%20Project.md)
- [What is Cargo in Rust](What%20is%20Cargo%20in%20Rust.md)
- [What is Rust Cargo.toml](What%20is%20Rust%20Cargo.toml.md)
- [What is Rust Project File Structure](What%20is%20Rust%20Project%20File%20Structure.md)

Source : [NOTE HUB for Klabnik, Steve; Nichols, Carol. The Rust Programming Language, 2nd Edition. No Starch Press. Kindle Edition.](NOTE%20HUB.md)

Topics : [Rust Programming Language](../../4-hub-notes-🚉/Rust.md)

After making sure that you have Rust installed

```sh
cargo --version
```

Create a project with Cargo by running the following in the terminal

```sh
cargo new <project_name>
cd <project_name>
```

This will create a new directory and project of the name we provided.
Cargo then creates two files and `src` directory with a main.rs file within it.

Cargo goes a step further it assumes that you'll be using some means of
version control, so the Cargo tool will initialize a new Git repository along
with a _.gitignore_ file; however, if an existing Git repository is already in
place Cargo won't create one when the `cargo new` command is used.

If you want to have a new Git repository within one already set you'd have to
provide the following command: `cargo new --vsc=git`; on the other hand,
if one wishes to use a different version control system or none at all they may
do the following `cargo new --help` to see the available options
