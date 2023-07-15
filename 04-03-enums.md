# Enums
Enums are classes in Kotlin

#### C#
```
public enum TrafficLight
{
    Red,
	Yellow,
	Green
}
```

#### Kotlin
```
enum class TrafficLight {
    RED,
    YELLOW,
    GREEN
}
```

This means they can have properties and methods

#### Kotlin
```
enum class TrafficLight(private val sameColourAs: String) {
    RED("tomato"),
    YELLOW("banana"),
    GREEN("pea");     // Rare use of a semicolon!

    fun describe() {
        println("I'm the same colour as a $sameColourAs")
	}
}

TrafficLight.YELLOW.describe() // "I'm the same colour as a banana"
```

And they can extend any type (not just integral types)

#### C#
```
public enum TrafficLight : byte
{
    Red,
	Yellow,
	Green
}
```

#### Kotlin
```
enum class TrafficLight : Describable, Serializable {
    RED,
    YELLOW,
    GREEN;

    override fun describe() {...}
    override fun serialize() {...}
}

TrafficLight.RED.describe()
TrafficLight.GREEN.serialize()
```

[Next: DSL functions](05-00-dsl-functions.md)
