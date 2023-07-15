# apply()
`apply()` is a method available on all Kotlin objects. It takes a lambda whose context is `this` and returns `this`.

What does that mean? It means that multiple lines of code that operate on a single object can be reduced to a single line. For example:

#### Kotlin
```
fun buildWilf() {
	var wilf = Person()
	wilf.name = "Wilf"
	wilf.age = 5
	wilf.loadHobbies()
	return wilf
}
```

Can be rewritten as

#### Kotlin
```
fun buildWilf = Person().apply {
		// everything at this level is implicitly operating on this
	    name = "Wilf"
	    age = 5
	    loadHobbies()
	}
```

[Next: Summary](06-summary.md)
