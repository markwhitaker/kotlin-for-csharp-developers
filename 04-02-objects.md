# Objects
Kotlin doesn't have `static` (or anything equivalent)

However, it has built-in support for singleton objects with the `object` keyword

So the nearest equivalent to this...

#### C#
```
public static class Thing
{
    public static readonly string Name => "Bob"

    public static void DoStuff()
    {
        ...
	}
}

Thing.DoStuff();
Console.WriteLine(Thing.Name);
```

is this...

#### Kotlin
```
object Thing {
    val name = "Bob"

    fun doStuff() {
        ...
	}
}

Thing.doStuff()
println(Thing.name)
```

**Note:** `object` names are capitalised, like a class

Objects can extend classes and implement interfaces

#### Kotlin
```
object Thing : BaseClass(), Interface {
    override fun baseClassMethod() {
        ...
	}

	override fun InterfaceMethod {
        ...
	}
}
```

## Companion objects
The equivalent of a **static method** in a **non-static class** can be achieved with a `companion object`

#### C#
```
public class Singleton
{
    public static Singleton Instance => new Singleton();

    private Singleton()
    {
        ...
	}

    public InstanceMethod()
    {
        ...
	}
}

var instance = Singleton.Instance;

instance.InstanceMethod();
```

#### Kotlin
```
class Singleton private constructor() {
    fun instanceMethod() {
        ...
	}

    companion object {
        val instance = Singleton()    // can access the private constructor
	}
}

var instance = Singleton.instance     // property called directly on the class

instance.instanceMethod()
```

[Next: Enums](04-03-enums.md)
