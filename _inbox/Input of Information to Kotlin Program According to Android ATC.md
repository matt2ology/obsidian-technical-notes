---
note-type: literature
date-created: 2024-02-14
long-form-date-created: Wednesday, February 14, 2024
week-created: Week 07.3
time-created: 04:19 PM
author:
---

# Input of Information to Kotlin Program According to [Android ATC](../tutorials-guides-and-courses/Android%20ATC%20-%20Android%20Application%20Development%20v12/Android%20Advanced%20Training%20Consultants.md)

Related : [Kotlin Variables According to Android ATC](../tutorials-guides-and-courses/Android%20ATC%20-%20Android%20Application%20Development%20v12/Kotlin%20Variables%20According%20to%20Android%20ATC.md)

Source : [Android ATC - Android Application Development v12](../tutorials-guides-and-courses/Android%20ATC%20-%20Android%20Application%20Development%20v12/Android%20ATC%20-%20Android%20Application%20Development%20v12.md)

Topics : [Kotlin](../4-hub-notes-🚉/Kotlin%20Programming%20Language.md)

`readLine()` function allows the Kotlin program user to enter string values or intercept
keyboard input from the console

```kotlin
fun main(){
    println("=========================================")
    println("Welcome to Android ATC")
    println("=========================================")
    println("Enter Your Name :")
    var x= readLine()

    println("Enter Your Age :")
    var y= readLine()

    println("Thank you, Your Name is : $x and Your Age is = $y")
    println("========================================================")
}
```

> Outputs
>
> > =========================================
> >
> > Welcome to Android ATC
> >
> > =========================================
> >
> > Enter Your Name :
> >
> > `Eisen`
> >
> > Enter Your Age :
> >
> > `150`
> >
> > Thank you, Your Name is : Eisen and Your Age is = 150
> >
> > =========================================

```kotlin
fun main() {
    println("=========================================")
    println("Welcome to Android ATC Calculator")
    println("=========================================")
    println("Enter the first number:")
    var x = Integer.valueOf(readLine())
    println("Enter the Second number:")
    var y = Integer.valueOf(readLine())

    var z=x+y
    var a=x*y
    var b=x/y

    println("The Sum Result = $z")
    println("The Multiplication Result = $a")
    println("The Division Result = $b")
    println("=========================================")
}
```

> Outputs
>
> > =========================================
> >
> > Welcome to Android ATC Calculator
> >
> > =========================================
> >
> > Enter the first number:
> > `8`
> >
> > Enter the Second number:
> >
> > `4`
> >
> > The Sum Result = 12
> > The Multiplication Result = 32
> > The Division Result = 2
> >
> > =========================================

```kotlin
fun main() {
    println("=========================================")
    println("Welcome to Android ATC Calculator")
    println("=========================================")
    println("Enter the first number:")
    var x = Integer.valueOf(readLine())
    println("Enter the Second number:")
    var y = Integer.valueOf(readLine())

    println("The Sum Result = ${x+y}")
    println("The Multiplication Result = ${x*y}")
    println("The Division Result = ${x/y}")
    println("========================================================")
}
```

The same effect can be done with native functions

| Expression | Function name | Translates to |
| ---------- | ------------- | ------------- |
| x + y      | Plus          | `x.plus(y)`   |
| x - y      | Minus         | `x.minus(y)`  |
| x \* y     | Times         | `x.times(y)`  |
| x / y      | Div           | `x.div(y)`    |

```kotlin
fun main() {
    println("=========================================")
    println("Welcome to Android ATC Calculator")
    println("=========================================")
    println("Enter the first number:")
    var x = Integer.valueOf(readLine())
    println("Enter the Second number:")
    var y = Integer.valueOf(readLine())

    var z=x.plus(y) // same x+y
    var a=x.times(y) // same x*y
    var b=x.div(y) //same x/y

    println("The Sum Result = $z")
    println("The Multiplication Result = $a")
    println("The Division Result = $b")
    println("========================================================")
}
```
