# 3.1. Classes: the basics
In Kotlin, you declare:
* a class with `class`
* methods with `fun`
* properties with `var` or `val`

**C#**
```csharp
public class Thing
{
    private string _readWriteField;

    public string ReadOnlyProperty { get; }

    public string ReadWriteProperty1 { get; set; }

    public string ReadWriteProperty2
    {
        get => LoadValue();
        set => SaveValue(value);
    }
}
```

**Kotlin**
```kotlin
class Thing {
    private var readWriteField: String = ""

    val readOnlyProperty: String = ""   // Use val for { get; } behaviour

    var readWriteProperty1: String = ""   // Use var for { get; set; } behaviour

    var readWriteProperty2: String
        get() = loadValue()
        set(value) {
            saveValue(value)
        }
}
```

**Two things to note:**

* There's no distinction between fields and properties in Kotlin: all have implicit `get()`/`set()` methods
* Kotlin is strict about nulls, hence the `String` properties have to be initialised here. We'll see soon how to intialise them via the constructor...

[Next: Constructors (part 1)](03-02-constructors-part-1.md)
