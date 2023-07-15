# Classes: the basics
Declare...
* a class with `class`
* methods with `fun` 🥳
* properties with `var`/`val`

#### C#
```csharp
public class Thing
{
    private string _field;

    public string Property1 { get; set; }

    public string Property2 { get; }

    public string Property3
    {
        get => LoadProperty3();
	    set => SaveProperty3(value);
	}
}
```

#### Kotlin
```kotlin
class Thing {
    private var field: String = ""

    var property1: String = ""   // Use var for { get; set } behaviour

    val property2: String = ""   // Use val for { get; } behaviour

    var property3: String
        get() = loadProperty3()
        set(value) {
            saveProperty3(value)
		}
}
```

**Two things to note:**
* There's no distinction between fields and properties in Kotlin: all have implicit `get()`/`set()` methods
* Kotlin is strict about nulls, hence the `String` properties have to be initialised here. We'll see soon how to intialise them via the constructor...

[Next: Constructors (part 1)](03-02-constructors-part-1.md)
