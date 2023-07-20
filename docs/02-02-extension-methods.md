## 2.2. Extension methods

These are used much the same as in C# but are declared differently. In Kotlin:

* there's no need for an enclosing static class (extension methods can be declared at global scope)
* there's no `this` parameter: the type that the method extends is declared using `Type.` syntax

**C#**
```csharp
public static class StringExtensions
{
    public static string MaskPassword(this string password)
    {
        return new string('*', password.Length);
    }
}
```

**Kotlin**
```kotlin
fun String.maskPassword(): String {
    return "*".repeat(this.length)
}
```

Because there's no need for a `this` method parameter, we can also have **extension properties** in Kotlin

**Kotlin**
```kotlin
val String.masked: String
    get() = "*".repeat(length)   // Note, as in C# 'this' can be omitted
```

[Next: Classes](03-00-classes.md)
