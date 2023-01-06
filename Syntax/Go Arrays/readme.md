# Go Arrays

Arrays are used to store multiple values of the same type in a single variable, instead of declaring separate variables for each value.

## Declare an Array

In Go, there are two ways to declare an array :

## 1. With the Var keyword

### Syntax

```go
var array_name = [length]datatype{values} // here length is defined

or

var array_name = [...]datatype{values} // here length is inferred
```

## 2. With the := sign

### Syntax

```go
array_name := [length]datatype{values} // here length is defined

or

array_name := [...]datatype{values} // here length is inferred
```

**Notes:** The length specifies the number of elements to store in the array. In Go, arrays have a fixed length. This length of array is either defined by a number or is inferred(means that the compiler decides the )

### Array Examples

This example declares two arrays (arr1 and arr2) with defined lengths:

```go
package main
import ("fmt")

func main() {
  var arr1 = [3]int{1,2,3}
  arr2 := [5]int{4,5,6,7,8}

  fmt.Println(arr1)
  fmt.Println(arr2)
}
```

Result :

    [1 2 3]
    [4 5 6 7 8]

Examples :

This example declares two arrays (arr1 and arr2) with inferred lengths:

```go
package main
import ("fmt")

func main() {
  var arr1 = [...]int{1,2,3}
  arr2 := [...]int{4,5,6,7,8}

  fmt.Println(arr1)
  fmt.Println(arr2)
}
```

    [1 2 3]
    [4 5 6 7 8]

## Access Elements of an Array

You can access a specific array element by referring to the index number.

In Go, array indexes start at 0. That means that [0] is the first element, [1] is the second element, etc.

## Example

This example shows how to access the first and third elements in the prices array:

```go
package main
import ("fmt")

func main() {
  prices := [3]int{10,20,30}

  fmt.Println(prices[0])
  fmt.Println(prices[2])
}
```

    Result:
    10
    30

## Change Elements of an Array

```go
package main
import ("fmt")

func main() {
  prices := [3]int{10,20,30}

  prices[2] = 50
  fmt.Println(prices)
}

```

    result : [10 20 50]

## Array Initialization

If an array or one of its elements has not been initialized , it is assigned the default value of its type.

**Tips:** The default value for int is 0, and the default value for string is "".

```go
package main
import ("fmt")

func main() {
  arr1 := [5]int{} //not initialized
  arr2 := [5]int{1,2} //partially initialized
  arr3 := [5]int{1,2,3,4,5} //fully initialized

  fmt.Println(arr1)
  fmt.Println(arr2)
  fmt.Println(arr3)
}
```

Result

    [0 0 0 0 0]
    [1 2 0 0 0]
    [1 2 3 4 5]

## Initialize Only Specific Elements

It is possible to initialize only specific elements in an array.

### Example

This example initializes only the second and third elements of the array:

```go
package main
import ("fmt")

func main() {
  arr1 := [5]int{1:10,2:40}
        //5 elements : type int . Index 1 = 10 , Index 2 = 49, default value 0

  fmt.Println(arr1)
}
```

    Result : [0 10 40 0 0]

## Find the length of an Array

The len() function is used the length of an array:

Example:

```go
package main
import ("fmt")

func main() {
  arr1 := [4]string{"Volvo", "BMW", "Ford", "Mazda"}
  arr2 := [...]int{1,2,3,4,5,6}

  fmt.Println(len(arr1))
  fmt.Println(len(arr2))
```
