## 1.3. const val
`const val` is equivalent to `const` in C#. In Kotlin, a `const val`:
* must be initialised where it's declared
* must be initialised with a compile-time constant value, whereas `val` is initialised at runtime
* is named in `SCREAMING_CASE` (like Java constants)

**C#**
```csharp
const int port = 80;
readonly string schema = "https";
readonly string host;  // Class field

// Later, in the constructor
host = "kotlinlang.org";
host = "microsoft.com";  // ERROR: can only assign once
```

**Kotlin**
```kotlin
const val PORT = 80   // As above, type can be inferred
val schema = "https"
val host: String   // Can be a class field or local (or even global)

// Later
host = "kotlinlang.org"
host = "microsoft.com"  // ERROR: can only assign once
```

[Next: Functions](02-00-functions.md)
