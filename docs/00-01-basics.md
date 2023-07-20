# 0.1. Basics
## Naming
Kotlin follows Java naming conventions:
* `PascalCase` for type names
* `camelCase` for variable, function and method names
* `SCREAMING_CASE` for constants and enum values

## Scope
Variables and functions can be declared at:
* **file scope** (globals)
* **local scope** (variables and local functions)
* **type scope** (fields, properties and methods in a class, object or interface)

## Visibility
Kotlin has the following visibility modifiers:
* `public`: same as C#
* `private`: same as C#... **plus** can be used at file scope to limit access to this file
* `protected`: same as C#
* `internal`: similar to C# - visible to the current "module" (a set of files that are compiled together e.g. Maven/Gradle project, IntelliJ project)

The default for everything is `public`.

**C#**
```csharp
class ImplicitlyInternal
{
    void ImplicitlyPrivate()
    {
    }
}
```

**Kotlin**
```kotlin
class ImplicitlyPublic {
    fun implicitlyPublic() {
    }
}
```

[Next: Variables](01-00-variables.md)
