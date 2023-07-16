# Function literals with receiver (part 1)

We've seen [extension methods](02-02-extension-methods.md):

```kotlin
Type.extensionMethod() {
    doStuffWith(this)
}
```

And we've seen [lambdas](05-02-defining-lambdas.md):

```kotlin
fun doLongRunningTask(onDone: () -> Unit) {
    figureOutMeaningOfLife()
    onDone()
}
```

What happens if we put those two syntax elements together? The answer is we get a Kotlin feature called a **function literal with receiver**. (But if that's too much of a mouthful you can think of it as an "extension lambda".)

Here's an example:

```kotlin
fun html(provideContent: Html.() -> Unit): Html {
    val html = Html()
    html.provideContent()
    return html
}
```
There's a lot going on there so let's unpack it piece-by-piece.

* `html()` is a function declared at global scope.
* `html()` returns an object of type `Html`.
* `html()` takes a single argument, `provideContent`, which is a lambda.
* **But**... `provideContent` is slightly different to lambdas we've seen before. As well as the usual lambda syntax `() -> Unit` (no arguments, returns `Unit`), it's also scoped to the `Html` class, using the same syntax as an extension method: `Html.() -> Unit`
* This means that the `provideContent` lambda (just like an extension method) is scoped to the `Html` object it's called on. In other words, inside the lambda, `this` refers to an `Html` object.
* The body of the `html()` function is pretty standard Kotlin now: it creates a new `Html` object, invokes the `provideContent` lambda on it as if it's a method of the `Html` class, then returns the (now initialised) object.

The lambda is the **function literal**, and the `Html` class is the **receiver**, hence **function literal with receiver**.

Let's imagine our `Html` class is very basic indeed and looks like this:

```kotlin
class Html {
    private var content = ""

    fun div(innerText: String) = content += "<div>$innerText</div>\n"

    override fun toString() = content
}
```
And now let's put all that together and see how the `html` function is called:

```kotlin
val myHtml = html {
    // We're now inside the lambda body:
    // `this` refers to an Html object

    div("Hello world")   // Html class method call
    div("Goodbye world") // And another
}

println(myHtml)
// Output:
// <div>Hello world</div>
// <div>Goodbye world</div>
```

Look! We've built a very simple DSL! This is the exact equivalent of writing this:

```kotlin
val myHtml = Html()
myHtml.div("Hello world")
myHtml.div("Goodbye world")

println(myHtml)
```

[Next: Function literals with receiver (part 2)](05-05-function-literals-with-receiver-part-2.md)
