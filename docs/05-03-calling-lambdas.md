## 5.3. Calling lambdas
Lambda parameters are passed to functions using curly braces `{}`. Here's how we'd pass a lambda to each of the functions from the previous page:

Lambda with no parameters and no return value:

```kotlin
// Define a function with a lambda parameter
fun doLongRunningTask(onDone: () -> Unit) {
    figureOutMeaningOfLife()
    onDone()
}

// Now call it, passing a lambda body
doLongRunningTask({
    println("Done.")
})
```

Lambda with a parameter and a return value:

```kotlin
// Define a function with a lambda parameter
fun logAsString(int: Int, convertToString: (Int) -> String) {
    val string = convertToString(int)
    println(string)
}

// Now call it
logAsString(100, { i ->
    i.toString(radix = 16) // convert to hex string
})
```

### Trailing lambdas
If a lambda is the last parameter to a function (a **trailing lambda**), its body can be placed outside the function's `()` brackets. We can use this syntax when passing both of our earlier lambdas.

```kotlin
doLongRunningTask() {
    println("Done.")
}

logAsString(100) { i ->
    i.toString(radix = 16)
}
```

 And if that leaves the brackets empty (as with our `doLongRunningTask()` example), the brackets can be omitted completely.

 So our first example now looks like this:

```kotlin
doLongRunningTask {
    println("Done.")
}
```

That's starting to look closer to DSL syntax already. We're nearly there.

[Next: Function literals with receiver](05-04-function-literals-with-receiver-part-1.md)
