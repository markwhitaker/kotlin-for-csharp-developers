# Extension methods

These work exactly the same as in C# but the syntax is slightly different

#### C#
```csharp
public static class StringExtensions
{
    public static string MaskPassword(this string password)
    {
        return new string('*', password.Length);
    }
}
```

#### Kotlin
```kotlin
fun String.maskPassword(): String {
    return "*".repeat(this.length)
}
```

Unlike C#, Kotlin also has **extension properties**

#### Kotlin
```kotlin
val String.masked: String
    get() = "*".repeat(length)   // Note, as in C# 'this' can be omitted
```

[Next: Classes](03-00-classes.md)
