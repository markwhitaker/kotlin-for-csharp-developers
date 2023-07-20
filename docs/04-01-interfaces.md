## 4.1. Interfaces
Kotlin interfaces are very similar to C#'s (although without the `I` naming convention).

**Kotlin**
```kotlin
interface MyInterface {
    val name: String
    fun printName()
}
```

Like C# 8.0, Kotlin methods can have default implementations.

```kotlin
interface MyInterface {
    val name: String
    fun printName() {
        println(name)
    }
}
```

Classes implement interface members with the `override` keyword.

```kotlin
class MyClass : MyInterface {
    override val name: String = "Bob"
    override fun printName() {
        // override the default from the interface
    }
}
```

[Next: Objects](04-02-objects.md)
