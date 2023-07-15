# Calling lambdas
Lambda parameters are passed to functions using curly braces `{}`. Here's how we'd pass a lambda to each of the functions from the previous page:

Lambda with no parameters and no return value:
**Kotlin**
```kotlin
fun doLongRunningThing(onDone: () -> Unit) {
    figureOutMeaningOfLife()
    onDone()
}

//...

doLongRunningThing({
    println("Done.")
})
```

Lambda with a parameter and a return value:
**Kotlin**
```kotlin
fun outputAsHexString(value: Int, convertToHexString: (Int) -> String) {
    val hexString = convertToHexString(value)
    println(hexString)
}


//...

outputAsHexString(100, { i ->
    i.toString(16)
})
```

## Trailing lambdas
If a lambda is the last parameter to a function (a **trailing lambda**), its body can be placed outside the function's `()` brackets. We can use this syntax when passing both of our earlier lambdas.

**Kotlin**
```kotlin
doLongRunningThing() {
    println("Done.")
}

outputAsHexString(100) { i ->
    i.toString(16)
}
```

 And if that leaves the brackets empty (as with our `doLongRunningThing()` example), the brackets can be omitted completely.

 So our first example now looks like this:

**Kotlin**
```kotlin
doLongRunningThing {
    println("Done.")
}
```

That's starting to look closer to DSL syntax already. We're nearly there.

[Next: Function literals with receiver](05-04-function-literals-with-receiver.md)
