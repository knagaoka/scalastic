# Chapter 2
> The signum of a number is 1 if the number is positive, -1 if it is negative, and 0 if it is zero. Write a function that computes this value.

```
def signum(i: Int): Int = {
  if (i > 0) 1
  else if (i < 0) -1
  else 0
}
```

> What is the value of an empty block expression `{}`? What is its type?

The value of an empty block expression is `()`, which is an empty instance of type `Unit`.

> Come up with one situation where the assignment `x = y = 1` is valid in Scala. (Hint: Pick a suitable type for `x`.)

Since assignments in Scala return type `Unit`, the type of `y = 1` will be `Unit`. Therefore, the type of `x` must be `Unit`.
```
var y = 0				// create an Int
var x: Unit = ()		// creates an instance of Unit
x = y = 1				// returns Unit
```

> Write a Scala equivalent for the Java loop `for (int i = 10; i >= 0; i--) System.out.println(i);`

`for (i <- 10 to 0 by -1) println(i)`

> Write a procedure `countdown(n: Int)` that prints the numbers from `n` to 0.

`def countdown(n: Int): Unit = for (i <- n to 0 by -1) println(i)`

> Write a `for` loop for computing the product of the Unicode codes of all letters in a string. For example, the product of the characters in `"Hello"` is 9415087488L.

```
val s = "Hello"
var p = 1
for (i <- 0 until s.length) {
  p *= s(i)
}
p	// p: Int = 825152896
```

> Solve the preceeding excercise without writing a loop. (Hint: Look at the `StringOps` Scaladoc.)

`"Hello".aggregate(1)({(prod, character) => prod * character.toInt}, {(current, next) => current * next})`

> Write a function `product(s : String)` that computes the product, as descibed in the preceeding exercises.

`def product(s: String) = s.aggregate(1)({(prod, character) => prod * character.toInt}, {(current, next) => current * next})
product("Hello")`

> Make the function of the preceeding exercise a recursive function.

```
def product(s: String): Int = {
  if (s == "") 1
  else s.head.toInt * product(s.tail)
}
```

> Write a function that computes x<sup>n</sup>, where n is an integer.

```
def powerx(base: Int, pow: Int): Int = {
  if (pow == 0) 1
  else base * powerx(base, pow - 1)
}
```