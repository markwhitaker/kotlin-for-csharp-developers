# Interfaces
Very similar to C# (although without the `I` naming convention)

#### Kotlin
```kotlin
interface MyInterface {
    val name: String
    fun printName()
}
```

...except methods can have default implementations

#### Kotlin
```kotlin
interface MyInterface {
    val name: String
    fun printName() {
        println(name)
    }
}
```

Classes implement interface members with `override`

#### Kotlin
```kotlin
class MyClass : MyInterface {
    override val name: String = "Bob"
    override fun printName() {
        // override the default from the interface
    }
}
```

[Next: Objects](04-02-objects.md)
