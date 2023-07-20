## 3.2. Constructors (part 1)
There is no `new` keyword in Kotlin: constructors are called directly.

**Kotlin**
```kotlin
var myObject = MyClass()
```

### Constructor declaration 🤯
Here's where things get funky.

A class's **primary constructor** is defined inline with the class declaration.

**C#**
```csharp
public class MyClass
{
    public MyClass(string s)
    {
        //...
    }
}
```

**Kotlin**
```kotlin
class MyClass constructor(s: String) {
}
```

The constructor here (like everything in Kotlin) is implicitly `public`, so if that's what we want we can omit the `constructor` keyword.

```kotlin
class MyClass(s: String) {
}
```

Or we can make it `private`/`protected`/`internal`.

```kotlin
class MyClass private constructor(s: String) {
}
```

If we need to access `s` we can do it in an `init` block.

```kotlin
class MyClass(s: String) {
    private val someProperty: String

    init {
        someProperty = s
    }
}
```

**But** a more common pattern is to initialise properties directly in the constructor by adding the `val` or `var` keyword.

```kotlin
class MyClass(val someProperty: String) {
}

var myObject = MyClass("hello world")
println(myObject.someProperty)   // "hello world"
```

This looks 😵‍💫 at first sight but it makes for nice small classes when you compare with C#.

**C#**
```csharp
public class Service
{
    private readonly IRepository _repository;
    private readonly ILogger _logger;

    public string Name { get; set; }

    public Service(IRepository repository, ILogger logger, string name)
    {
        _repository = repository;
        _logger = logger;
        Name = name;
    }
}
```

**Kotlin**
```kotlin
class Service(
    private val repository: Repository,
    private val logger: Logger,
    var name: String
) {
}
```

[Next: Constructors (part 2)](03-03-constructors-part-2.md)
