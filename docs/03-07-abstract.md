# abstract
Kotlin's `abstract` is very similar to its C# counterpart, and open/closed rules are identical to those for `open` classes.

**C#**
```csharp
public abstract class AbstractThing
{
    public AbstractThing(string name)
    {
        //...
    }

    public void Run()
    {
        DoWork();
    }

    protected abstract void DoWork();
}

public sealed class Thing : AbstractThing
{
    public Thing(string name) : base(name)
    {
        //...
    }

    protected override void DoWork()
    {
        //...
    }
}
```

**Kotlin**
```kotlin
abstract class AbstractThing(val name: String) {
    fun run() {
        doWork()
    }

    protected abstract fun doWork()
}

class Thing(name: String) : AbstractThing(name) {
    override fun doWork() {
        //...
    }
}
```

[Next: Other types](04-00-other-types.md)
