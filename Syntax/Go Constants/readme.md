# Go constants

If a variable should have a fixed value that cannot be changed, you can use the **const** keyword .

The **const** keyword declares the variable as "constant",which means that it is **unchangeable and read-only**

### Syntax

```go
    const CONSTNAME type = value
```

**Note:** The value of constant must be assigned when you declare it.

### Declaring a constant

Here is an example of declaring a constant in Go:

```go
package main
import ("fmt")


// out of scope
const PI = 3.14

func main(){
    fmt.Println("PI")
}

```

### Constant Rules

- constant names follow the same naming rules as variables

- constant names are usually written in uppercase letters (for easy identification and differentiation from variables)

- Constants can be declared both inside and outside of a function

### Constant Types

The are two types of constants :

- Typed constants
- Untyped constants

### Typed Constants

Typed constants are declared with a defined type

```go
package main
import ("fmt")

const A int = 1 ; // type const
const B = 2 ; // untyped const

```

### Constants : Unchangeable and Read-only

When a constant is declared, it is not possible to change the value later :

```go
package main
import ("fmt")

func main(){
    const A = 1;
    A = 2 ; // Cannot assign
}
```

### Multiple Constants Declaration

Multiple constants can be grouped together into a block for readability:

```go
package main
import ("fmt")

const (
  A int = 1
  B = 3.14
  C = "Hi!"
)

func main() {
  fmt.Println(A)
  fmt.Println(B)
  fmt.Println(C)
}
```
