# Chapter 3
> Write a code snippet that sets `a` to an array of `n` random integers between `0` (inclusive) and `n` (exclusive).

```
import scala.collection.mutable.ArrayBuffer
def randArray(n: Int): Array[Int] = {
  val ab = ArrayBuffer[Int]()
  for (i <- 0 until n) {
    ab += scala.util.Random.nextInt(n)
  }
  ab.toArray
}

val a = randArray(5)   // a: Array[Int] = Array(1, 4, 2, 4, 3)
```

> Write a loop that swaps adjacent elements of an array of integers. For example, `Array(1, 2, 3, 4, 5)` becomes `Array(2, 1, 4, 3, 5)`.

```
import scala.collection.mutable.ArrayBuffer
def swapAdjacent(arr: Array[Int]): Array[Int] = {
  var swaps = arr.length / 2
  var index = 0
  val ab = ArrayBuffer[Int]()
  while (swaps > 0) {
    ab += arr(index + 1)
    ab += arr(index)
    swaps -= 1
    index += 2
  }
  if (arr.length > index) ab += (arr(index))
  ab.toArray
}
```

> Repeat the preceding assignment, but produce a new array with the swapped values. Use `for/yield`.

```
// TODO Fix
def swapAdjacent(arr: Array[Int]) = {
  for (i <- 0 until arr.length) yield {
    if ((i % 2 == 0) && (i + 1 < arr.length)) arr(i + 1) else arr(i - 1)
  }
}
```

