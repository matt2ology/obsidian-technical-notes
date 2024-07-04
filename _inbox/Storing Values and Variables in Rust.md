---
aliases: 
note-type: permanent
date-created: 2024-07-03
long-form-date-created: Wednesday, July 03, 2024
week-created: Week 27.3
time-created: 11:23 PM
---

# Storing Values and Variables in Rust

Related : [What is a growable?](What%20is%20a%20growable) - [What is an associated function](../Book%20Notes%20and%20References%20Library%20📚/The%20Rust%20Programming%20Language%20-%202nd%20Edition/What%20is%20an%20associated%20function.md)

Topics : [Rust Programming Language](../4-hub-notes-🚉/Rust.md)

```rust
let apples = 5; // immutable (constant: can not manipulate)
let mut apples = 5; // mutable (is able to change in program)
```

Like other typical programming languages the equals sign (`=`) tells Rust that we
want to bind something to the variable on its left.  On the right of the equal sign
is the value that we want our variable to be bounded to.

```rust
let mut guess = String::new();
```

In the example: we want the variable `guess` to be bounded by the result of
the function `String::new` that returns a new instance of a `String`.

`String` is provided by the standard library that is a [growable](What%20is%20a%20growable), UTF-8 encoded
bit of text.

The double-colon (`::`) syntax indicates that `new` is an [associated function](../Book%20Notes%20and%20References%20Library%20📚/The%20Rust%20Programming%20Language%20-%202nd%20Edition/What%20is%20an%20associated%20function.md) of type
`String`.

The `new` function creates a new, empty string. `new` functions are common on 
many types because it's a common name for a function that makes a new value
of some kind.

All together, the `let mut guess = String::new();` creates a mutable
variable that is bound to a new, empty instance of a String.
