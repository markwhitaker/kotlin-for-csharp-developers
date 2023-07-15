# Constructors (part 2)
Ready for an extra helping of 🤯?

You can mix and match constructor **properties** and regular constructor **parameters**.

**C#**
```csharp
public class Service
{
    private readonly IRepository _repository;

    public string Name { get; set; }

    public Service(IRepository repository, string name, int age)
    {
        _repository = repository;
        Name = name;
        // do something else with age - it isn't a property
    }
}
```

**Kotlin**
```kotlin
class Service(
    private val repository: Repository,  // Private, read-only property
    var name: String,                    // Public, read/write property
    age: Int                             // Just a parameter, not a property:
) {                                      //   usable within an init block
}
```

**And**... a class can have both **constructor properties** and **non-constructor properties**.

**C#**
```csharp
public class Service
{
    private readonly IRepository _repository;
    private readonly ILogger _logger;

    public Service(IRepository repository)
    {
        _repository = repository;
        _logger = new Logger();
    }
}
```

**Kotlin**
```kotlin
class Service(
    private val repository: Repository
) {
    private val logger = Logger()
}
```

[Next: Constructors (part 3)](03-04-constructors-part-3.md)
