---
note-type: question
date-created: 2024-07-03
long-form-date-created: Wednesday, July 03, 2024
week-created: Week 27.3
time-created: 11:17 PM
author:
---

# What is Rust standard library prelude?

Related : [How to read user input in Rust](How%20to%20read%20user%20input%20in%20Rust.md)

Source : [NOTE HUB for Klabnik, Steve; Nichols, Carol. The Rust Programming Language, 2nd Edition. No Starch Press. Kindle Edition.](NOTE%20HUB.md)

Topics : [Rust Programming Language](../4-hub-notes-🚉/Rust.md)

By default, Rust has a set of items defined in the standard library that it brings 
into the scope of every program. This set is called the prelude, and you can see 
everything in it at https://doc.rust-lang.org/std/prelude/index.html.

If a type you  want to use isn’t in the prelude, you have to bring that type into 
scope explicitly  with a use statement. Using the std::io library provides you with a 
number of  useful features, including the ability to accept user input.

```rust
use std::io;
```

Klabnik, Steve; Nichols, Carol. The Rust Programming Language, 2nd Edition (p. 15). No Starch Press. Kindle Edition. 
