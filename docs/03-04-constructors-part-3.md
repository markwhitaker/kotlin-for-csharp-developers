## 3.4. Constructors (part 3)
Overloaded constructors are implemented with the `constructor` keyword.

**C#**
```csharp
public class Service
{
    private readonly IRepository _repository;

    public Service(IRepository repository)
    {
        _repository = repository;
    }

    public Service(IRepository repository, ILogger logger) : this(repository)
    {
        logger.Log("Hello");
    }
}
```

**Kotlin**
```kotlin
class Service(
    private val repository: Repository
) {
    constructor(repository: Repository, logger: Logger) : this(repository) {
        logger.log("Hello")
    }
}
```

**Note:** only the primary constructor can declare properties with `val`/`var`.

**Note:** overloaded constructors must call the primary constructor.

[Next: Inheritance](03-05-inheritance.md)
