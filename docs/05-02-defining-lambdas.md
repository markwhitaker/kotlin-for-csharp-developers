# Defining lambdas
Rember that [function parameters](02-00-Functions) are passed as `name: Type` in Kotlin, e.g.

#### Kotlin
```kotlin
fun multiplyBy2(value: Int) = value * 2
```

Kotlin also supports **lambdas**, which are passed to functions using the following syntax:

#### Kotlin
```kotlin
fun doLongRunningThing(onDone: () -> Unit) {
    figureOutMeaningOfLife()
    onDone()
}
```

So here the **name** of the lambda parameter is `onDone` and its **type** is `() -> Unit`:
* `()`: the lambda takes no arguments
* `Unit`: the lambda returns nothing (equivalent to `void` in C#)

Here's an example with a lambda that takes a parameter and returns something:

#### Kotlin
```kotlin
fun outputAsHexString(value: Int, convertToHexString: (Int) -> String) {
    val hexString = convertToHexString(value)
    println(hexString)
}
```

[Next: Calling lambdas](05-03-calling-lambdas.md)
