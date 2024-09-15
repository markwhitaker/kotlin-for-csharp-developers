## 4.3. Enums
Enums are classes in Kotlin and their values are named in `SCREAMING_CASE`.

**C#**
```csharp
public enum TrafficLight
{
    Red,
    Yellow,
    Green
}
```

**Kotlin**
```kotlin
enum class TrafficLight {
    RED,
    YELLOW,
    GREEN
}
```

Since they are classes, they can have properties and methods.

**Kotlin**
```kotlin
enum class TrafficLight(private val sameColourAs: String) {
    RED("tomato"),
    YELLOW("banana"),
    GREEN("pea");

    fun describe() {
        println("I'm the same colour as a $sameColourAs")
    }
}

TrafficLight.YELLOW.describe() // "I'm the same colour as a banana"
```

[I told you](01-01-var.md) we'd see a semicolon eventually! Did you spot it?

And they can extend any type (not just integral types).

**C#**
```csharp
public enum TrafficLight : byte
{
    Red,
    Yellow,
    Green
}
```

**Kotlin**
```kotlin
enum class TrafficLight : Describable, Serializable {
    RED,
    YELLOW,
    GREEN;

    override fun describe() {/*...*/}
    override fun serialize() {/*...*/}
}

TrafficLight.RED.describe()
TrafficLight.GREEN.serialize()
```

[Next: Domain-specific languages](05-00-domain-specific-languages.md)
