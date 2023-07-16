# DSL overview
The code snippet on the previous page...

```kotlin
html {
    body {
        div("hello world")
    }
}
```

...is an example of a **domain-specific language** or **DSL**, also referred to as **type-safe builder syntax**. It combines a few Kotlin features:

* Lambdas
* Trailing lambdas
* Function literals with receiver

Let's look at each in turn to build an understanding of that strange DSL syntax.

[Next: Defining lambdas](05-02-defining-lambdas.md)
