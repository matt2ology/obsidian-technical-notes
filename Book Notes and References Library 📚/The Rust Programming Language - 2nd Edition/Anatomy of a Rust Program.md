---
aliases:
note-type: permanent
date-created: 2024-06-30
long-form-date-created: Sunday, June 30, 2024
week-created: Week 26.7
time-created: 09:56 PM
---

# Anatomy of a Rust Program

Related :

Source : [NOTE HUB for Klabnik, Steve; Nichols, Carol. The Rust Programming Language, 2nd Edition. No Starch Press. Kindle Edition.](NOTE%20HUB.md)

Topics : [Rust Programming Language](../4-hub-notes-🚉/Rust.md)

The `main` function is special, i.e. it is reserved, and is always the first code that
runs in every executable Rust program.

Rust is a C-like language where bodies of code, functions, uses the curly brace
syntax (`{}`). Stylistically follows the K&R style (named after
Brian Kernighan and Dennis Ritchie)

```rust
fn main(){
    println!("Hello, world!")
}
```

1. All bodies of code within the curly brace are indented with four spaces, not by tabs.
2. `println!` calls a Rust micro. Using an exclamation mark (`!`) signifies that it is a micro and not a standard library function.
3. Expressions are ended with semicolons (`;`).

To remedy the two chad programmers imposing one style each other's code
Rust has an automatic formatter tool called `rustfmt` that conforms code
to fit the "standard Rust format" defined by The Rust team.
