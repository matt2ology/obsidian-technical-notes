---
note-type: literature
date-created: 2024-02-13
long-form-date-created: Tuesday, February 13, 2024
week-created: Week 07.2
time-created: 09:48 PM
author:
---

# Kotlin Variables According to [Android ATC](Android%20Advanced%20Training%20Consultants.md)

Related : [The main( ) function in Kotlin According to Android ATC](<The%20main(%20)%20function%20in%20Kotlin%20According%20to%20Android%20ATC.md>)

Source : [Android ATC - Android Application Development v12](Android%20ATC%20-%20Android%20Application%20Development%20v12.md)

Topics : [Kotlin](Kotlin%20Programming%20Language.md)

## Mutable variables

Can "mutate" during the run-time (i.e. the values can be re-assigned and changed)

To declare a mutable variable the keyword `var` is required before the variable name

```kotlin
var x = 1

fun main(){
    x = 4
    println(x)
}
```

> Output of code snippet above
>
> > 4

## Immutable variables

An immutable variables is a variable whose state, like constants, can't be changed after
Initialization and is declared via the keyword `val` before the variable name.

```kotlin
val y = 1

fun main(){
    y = 5 // Val cannot be reassigned because it's an immutable variable
    println(y)
}
```
