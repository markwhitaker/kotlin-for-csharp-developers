# 5.5. Function literals with receiver (part 2)

Of course, we wouldn't normally put a `<div>` tag right inside `<html>`, so let's build that up further to allow a `<body>` element to be nested between `<html>` and `<div>`.

To do this we'll need to:
* add a new `Body` class
* move the `div` method to the `Body` class
* add a `body` method to `Html`, whose argument will be another function literal with receiver, this time with `Body` as the receiver

```kotlin
class Html {
    private var content = ""

    fun body(provideContent: Body.() -> Unit) {
        val body = Body()
        body.provideContent()
        content += "<body>\n${body}</body>"
    }

    override fun toString() = content
}

class Body {
    private var content = ""

    fun div(innerText: String) {
        content += "<div>$innerText</div>\n"
    }

    override fun toString() = content
}

fun html(provideContent: Html.() -> Unit): Html {
    val html = Html()
    html.provideContent()
    return html
}
```

Now we can build our HTML like this:

```kotlin
val myHtml = html {
    body {
        div("Hello world")
        div("Goodbye world")
    }
}

println(myHtml)
// Output:
// <body>
// <div>Hello world</div>
// <div>Goodbye world</div>
// </body>
```

The equivalent Kotlin without DSL syntax would look like this:

```kotlin
var myBody = Body()
myBody.div("Hello world")
myBody.div("Goodbye world")

val myHtml = Html()
myHtml.body(myBody)

println(myHtml)
```

[Next: Summary](06-00-summary.md)
