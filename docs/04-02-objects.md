# Objects
Kotlin doesn't have `static` (or anything equivalent).

However, it has built-in support for singleton objects with the `object` keyword.

So the nearest equivalent to this...

**C#**
```csharp
public static class Thing
{
    public static readonly string Name => "Bob"

    public static void DoStuff()
    {
        //...
    }
}

Thing.DoStuff();
Console.WriteLine(Thing.Name);
```

is this...

**Kotlin**
```kotlin
object Thing {
    const val name = "Bob"

    fun doStuff() {
        //...
    }
}

Thing.doStuff()
println(Thing.name)
```

**Note:** Objects are named in `PascalCase`, like classes and interfaces.

Objects can extend classes and implement interfaces.

**Kotlin**
```kotlin
object Thing : BaseClass(), Interface {
    override fun baseClassMethod() {
        //...
    }

    override fun InterfaceMethod() {
        //...
    }
}
```

## Companion objects
The equivalent of a **static method** in a **non-static class** can be achieved with a `companion object`.

**C#**
```csharp
public class Singleton
{
    public static Singleton Instance => new Singleton();

    private Singleton()
    {
        //...
    }

    public InstanceMethod()
    {
        //...
    }
}

var instance = Singleton.Instance;

instance.InstanceMethod();
```

**Kotlin**
```kotlin
class Singleton private constructor() {
    fun instanceMethod() {
        //...
    }

    companion object {
        val instance = Singleton()    // can access the private constructor
    }
}

var instance = Singleton.instance     // property called directly on the class

instance.instanceMethod()
```

[Next: Enums](04-03-enums.md)
