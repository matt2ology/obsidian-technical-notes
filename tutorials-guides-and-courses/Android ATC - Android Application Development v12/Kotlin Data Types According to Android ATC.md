---
note-type: literature
date-created: 2024-02-13
long-form-date-created: Tuesday, February 13, 2024
week-created: Week 07.2
time-created: 10:06 PM
author:
---

# Kotlin Data Types According to [Android ATC](Android%20Advanced%20Training%20Consultants.md)

Related :

- [The main( ) function in Kotlin According to Android ATC](<The%20main(%20)%20function%20in%20Kotlin%20According%20to%20Android%20ATC.md>)
- [Kotlin Variables According to Android ATC](Kotlin%20Variables%20According%20to%20Android%20ATC.md)

Source : [Android ATC - Android Application Development v12](Android%20ATC%20-%20Android%20Application%20Development%20v12.md)

Topics : [Kotlin](../../4-hub-notes-🚉/Kotlin%20Programming%20Language.md)

Has all the typical datatypes you'd expect to see

## String

Can be declared

- Implicitly: `val Name = "Fern"`
- Explicitly: `val Name:String = "Himmel"`

## Character

Implicitly Kotlin compiler considers single quotes ('s') as char: `val x = '$'`

Explicitly a character variable assignment is as follows: `val x =:Char = 's'`

## Booleans

```kotlin
val x:Boolean=true

fun main() {
    println(x)
}
```

## Numbers

| Data Type | Description                                         | Default Value |
| --------- | --------------------------------------------------- | ------------- |
| Byte      | The byte data type is an 8-bit signed integer.      |               |
|           | Its value is from 0 to 255                          | 0             |
| Short     | The short data type is a 16-bit signed integer.     |               |
|           | Its value ranges from -32768 to 32767               | 0             |
| Int       | The integer data type is a 32-bit signed integer.   |               |
|           | It has values from -2,147,483,648 to +2,147,483,647 | 0             |
| Long      | The long data type is a 64-bit singed integer       | 0L            |
| Float     | The float data type is a single-precision           |               |
|           | 32-bit floating point                               | 0.0f          |
| Double    | The double data type is a double-precision          |               |
|           | 64-bit floating point                               | 0.0d          |

When you want to format, and get the value of, a particular variable in a quoted string
one can do the following

```kotlin
var price:Double = 10.05 // Explicitly double
var tax = 0.05 // Implicitly Double

fun main(){
    printlin("price = $price and tax = $tax")
}
```

> Outputs
>
> > price = 10.05 and tax = 0.05

One can also declare a data type for a variable first, and later assign its value from a specific
code operation.

```kotlin
fun main(){
    var first_name:String?=null // Explicitly declared as String with Null value
    println(first_name)
}
```

> Outputs
>
> > null

```kotlin
fun main(){
    var first_name:String?=null // Explicitly declared as String with Null value
    first_name = "Heiter"
    println(first_name)
}
```

> Outputs
>
> > Heiter

### Differences between Double and Float variables

Most use Double data type for variables which are expected to have a fraction value, for
double ensures a higher precision (64 bit) while Floats are single-precision (32-bit).

If any fraction value to any variable without declaring it explicitly, as Float, the Kotlin
compiler will consider it implicitly as Double data type.

**TL;DR**: fractions are stored as Double data types implicitly

## Array

```kotlin
fun main(){
    var x = arrayOf(5, 7, 9)
    println(x[0]) // Print the element in index 0
    println(x[1]) // Print the element in index 1
    println(x[2]) // Print the element in index 2
}
```

> Outputs
>
> > 5
> > 7
> > 9

```kotlin
fun main(){
    var x:IntArray = intArrayOf(5, 7, 9)
    println(x[2])
    x[2] = x[0] + x[1]
    println(x[2])
}
```

> Outputs
>
> > 9
> > 12
>
> This means that the array `x` now includes the following values: `[5, 7, 12]`

## Data Type Conversions

There are conversion functions that can be applied to variables

- `toByte()`
- `toShort()`
- `toInt()`
- `toLong()`
- `toDouble()`
- `toChar()`
- `toString()`

There are times you'd need to convert a data type for a variable to another data type.

```kotlin
fun main(){
    val x:Int = 55
    val y:Float = x.toLong()
    println("x = $x")
    println("y = $y")
}
```

> Outputs
>
> > x = 55
> > y = 55.0

## Input of Information to Kotlin Program

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
> > Welcome to Android ATC
> > =========================================
> >
> > Enter Your Name :
> > `Eisen`
> > Enter Your Age :
> > `150`
> > Thank you, Your Name is : Eisen and Your Age is = 150
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
> >

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
| ---- | ---- | ---- |
| x + y | Plus | `x.plus(y)` |
| x - y | Minus | `x.minus(y)` |
| x * y | Times | `x.times(y)` |
| x / y | Div | `x.div(y)` |

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
