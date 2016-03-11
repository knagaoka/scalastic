# Chapter 1
> In the Scala REPL, `type 3.` followed by the Tab key. What methods can be applied?

All methods from the `Int` class can be applied. The Scala REPL recognizes `3` as type `Int`.

> In the Scala REPL, compute the square root of 3, and then square that value. By how much does the result differ from 3? (Hint: The `res` variables are your friend).

```
import scala.math._
sqrt(3)
pow(res1, 2)
```
The resulting value is `res2: Double = 2.9999999999999996`.

> Are `res` variables `val` or `var`?

The `res` variables are `val` since they are immutable and cannot be reassigned values. A simple test can prove this.

```
1 + 1			// res0: Int = 2
res0 = 11		// <console>:12: error: reassignment to val
```

> Scala lets you multiply a string with a number--try out `"crazy" * 3` in the REPL. What does this operation do? Where can you find it in Scaladoc?

This operation is calling the `scala.collection.immutable.StringLike` function `*` which returns the string concatenated n times. This can be found [here](http://www.scala-lang.org/api/2.11.5/index.html#scala.collection.immutable.StringLike).

> What does `10 max 2` mean? In which class is the `max` method defined?

The expression means return the higher number of this (left side) or that (right side). This method is defined in the `scala.runtime.RichInt` class.

> Using BigInt, compute 2<sup>1024</sup>.

```
import scala.math.BigInt
BigInt(2) pow 1024
```
Results in `179769313486231590772930519078902473361797697894230657273430081157732675805500963132708477322407536021120113879871393357658789768814416622492847430639474124377767893424865485276302219601246094119453082952085005768838150682342462881473913110540827237163350510684586298239947245938479716304835356329624224137216`

> What do you need to import so that you can get a random prime as `probablePrime(100, Random)`, without any qualifiers before `probablePrime` and `Random`?

```
import scala.util.Random
import scala.math.BigInt
```