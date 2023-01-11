# Go slices

slices are similar to arrays, but are more powerful and flexible

Like arrays, slices are also used to store multiple values of the same type in single variable

However, unlike arrays, the length of a slice can grow and shrink as you see fit

In Go, there are several Ways to create a slice :

- Using the []datatype{values} format
- Create a slice from an array
- Using the make() function

## Create a slide with []datatype{values}

### Syntax

slice_name := []datatype{values}

A common way to declaring a slice is like this:

```go
    mySlice := [] int{}
```

The code above declares an empty slice of 0 length and 0 capacity.

To initialize the slice during declaration, use this:

```go
    mySLice := []int{1,2,3}
```

The code above declares a slice of integers of length 3 and also the capacity of 3 .

In GO, there are two functions that can be used to return the length and capacity of a slice :

- len() function - returns the length of the slice (the number of elements in the slice)
- cap() function - returns the the capacity of the slice (the number of elements the slice can grow or shrink to)

Example

this example shows how to create slices using the []datatype{values} format

```go
package main
import ("fmt")

func main() {
  myslice1 := []int{}
  fmt.Println(len(myslice1))
  fmt.Println(cap(myslice1))
  fmt.Println(myslice1)

  myslice2 := []string{"Go", "Slices", "Are", "Powerful"}
  fmt.Println(len(myslice2))
  fmt.Println(cap(myslice2))
  fmt.Println(myslice2)
}
/*
0
0
[]
4
4
[Go Slices Are Powerful]
*/
```

In the example above, we see that in the first slice (myslice1), the actual elements are not specified, so both the length and capacity of the slice will be zero. In the second slice (myslice2), the elements are specified, and both length and capacity is equal to the number of actual elements specified.

## Create a Slice From an Array

You can create a slice by slicing an array .

```go
var myArray = [length]dataType{values}
mySlice := myArray[start:end]
```

## Example

this example shows how to create a slice from an array

```go
package main
import ("fmt")

func main() {
  arr1 := [6]int{10, 11, 12, 13, 14,15}
  myslice := arr1[2:4]

  fmt.Printf("myslice = %v\n", myslice)
  fmt.Printf("length = %d\n", len(myslice))
  fmt.Printf("capacity = %d\n", cap(myslice))
}
// result :

/*
myslice = [12 13]
length = 2
capacity = 4
*/

```

In the example above myslice is a slice with length 2, It is made from arr1 which is an array with length6 .

The slice starts from the second element of the array which has value 12. The slice can grow to the and of the array . THis means that the capacity of the slice is 4.

## Create a Slice with the make() function

the Make() function can also be used to create a slice .

```go
Syntax

slice_name := make([]type,length,capacity)

```

**Note:** If the capacity parameter is not defined, it will be qual to length

## Go Modify

### Access elements of a slice

you can access a specific slice by referring to the index number

In Go, indexes start at 0. That means that [0] is the first element, [1] is the second element,etc.

```go
// package main
import ("fmt")

func main() {
  prices := []int{10,20,30}

  fmt.Println(prices[0])
  fmt.Println(prices[2])
}
```

## Change Elements of a slice

You can also change a specific slice element by referring to the index number .

```go
package main
import ("fmt")

func main() {
  prices := []int{10,20,30}
  prices[2] = 50
  fmt.Println(prices[0])
  fmt.Println(prices[2])
}
// 10 - 50
```

## Append Elements to a slice

You can append elements to the end of a slice using the append() function:

```go
slice_name = append(el1,el2)
```

## Append one slice to another slice

```go
slice3 = append(slice1,slice2)
```

```go
package main
import ("fmt")

func main() {
  myslice1 := []int{1,2,3}
  myslice2 := []int{4,5,6}
  myslice3 := append(myslice1, myslice2...)

  fmt.Printf("myslice3=%v\n", myslice3)
  fmt.Printf("length=%d\n", len(myslice3))
  fmt.Printf("capacity=%d\n", cap(myslice3))
}
// result :
/*
myslice3=[1 2 3 4 5 6]
length=6
capacity=6
*/
```

## Change the length of a slice

unlike arrays, it is possible to change the length of a slice.

### Example

```go
package main
import ("fmt")

func main() {
  arr1 := [6]int{9, 10, 11, 12, 13, 14} // An array
  myslice1 := arr1[1:5] // Slice array
  fmt.Printf("myslice1 = %v\n", myslice1)
  fmt.Printf("length = %d\n", len(myslice1))
  fmt.Printf("capacity = %d\n", cap(myslice1))

  myslice1 = arr1[1:3] // Change length by re-slicing the array
  fmt.Printf("myslice1 = %v\n", myslice1)
  fmt.Printf("length = %d\n", len(myslice1))
  fmt.Printf("capacity = %d\n", cap(myslice1))

  myslice1 = append(myslice1, 20, 21, 22, 23) // Change length by appending items
  fmt.Printf("myslice1 = %v\n", myslice1)
  fmt.Printf("length = %d\n", len(myslice1))
  fmt.Printf("capacity = %d\n", cap(myslice1))
}
/*
myslice1 = [10 11 12 13]
length = 4
capacity = 5
myslice1 = [10 11]
length = 2
capacity = 5
myslice1 = [10 11 20 21 22 23]
length = 6
capacity = 10
*/
```

### Memory Efficiency

When using slices, Go loads all the underlying elements into the memory
If the array is large and you add only a few elements,it is better to copy those elements using the copy function.
the copy() function creates a new underlying array with only the required elements for the slice . This will reduce the memory used for the program.

## Example

This example shows how to use the copy() function :

```go
package main
import ("fmt")

func main() {
  numbers := []int{1,2,3,4,5,6,7,8,9,10,11,12,13,14,15}
  // Original slice
  fmt.Printf("numbers = %v\n", numbers)
  fmt.Printf("length = %d\n", len(numbers))
  fmt.Printf("capacity = %d\n", cap(numbers))

  // Create copy with only needed numbers
  neededNumbers := numbers[:len(numbers)-10]
  numbersCopy := make([]int, len(neededNumbers))
  copy(numbersCopy, neededNumbers)

  fmt.Printf("numbersCopy = %v\n", numbersCopy)
  fmt.Printf("length = %d\n", len(numbersCopy))
  fmt.Printf("capacity = %d\n", cap(numbersCopy))
}

/*
// Original slice
numbers = [1 2 3 4 5 6 7 8 9 10 11 12 13 14 15]
length = 15
capacity = 15
// New slice
numbersCopy = [1 2 3 4 5]
length = 5
capacity = 5
*/
```
