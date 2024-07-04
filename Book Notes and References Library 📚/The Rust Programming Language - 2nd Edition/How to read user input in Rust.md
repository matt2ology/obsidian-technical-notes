---
note-type: question
date-created: 2024-07-03
long-form-date-created: Wednesday, July 03, 2024
week-created: Week 27.3
time-created: 11:10 PM
author:
---

# How to read user input in Rust

Related : [What is Rust standard library prelude](What%20is%20Rust%20standard%20library%20prelude.md)

Source : [NOTE HUB for Klabnik, Steve; Nichols, Carol. The Rust Programming Language, 2nd Edition. No Starch Press. Kindle Edition.](NOTE%20HUB.md)

Topics : [Rust Programming Language](../4-hub-notes-🚉/Rust.md)

To obtain user input and then print the result as output, we need to bring the
io input/output library into scope. The io library comes from the standard library,
known as std:

```rust
use std::io;
```

Klabnik, Steve; Nichols, Carol. The Rust Programming Language, 2nd Edition (p. 15). No Starch Press. Kindle Edition. 
