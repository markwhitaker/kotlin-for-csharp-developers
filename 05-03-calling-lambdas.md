# Calling lambdas
Lambda parameters are passed to functions using curly braces `{}`. Here's how we'd pass a lambda to each of the functions from the previous page:

Lambda with no parameters and no return value:
#### Kotlin
```kotlin
doLongRunningThing({
    println("Done.")
})
```

Lambda with a parameter and a return value:
#### Kotlin
```kotlin
outputAsHexString(100, { i ->
    i.toString(16)
})
```

## Trailing lambdas
Kotlin says that if a lambda is the last parameter to a function (a **trailing lambda**), its body can be placed outside the function's `()` brackets. Here's how that looks:

#### Kotlin
```kotlin
doLongRunningThing() {
    println("Done.")
}
```

#### Kotlin
```kotlin
outputAsHexString(100) { i ->
    i.toString(16)
}
```

 And if that leaves the brackets empty, they can be omitted completely. So our first example now looks like this:

#### Kotlin
```kotlin
doLongRunningThing {
    println("Done.")
}
```

That's starting to look like DSL syntax already. We're nearly there.

[Next: Function literals with receiver](05-04-function-literals-with-receiver.md)
