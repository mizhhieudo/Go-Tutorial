# Go comments

A comment is a text that is ignored upon exection.

Comments can be used to explain code , and to make it more readable.

Comments can also be used to prevent code execution When testing an alternative code .

Go support single-line or multi-line comments.

# Go single-line comments

single-line comments start with two forward slashes (//)

Any text between // and the of the line is ignored by the compiler (will not execute)

```go
// This is a comment
package main
import ("fmt")

func main() {
  // This is a comment
  fmt.Println("Hello World!")
}
```

The following example uses a single-line comment at the end of code line

```go
package main
import ("fmt")

func main() {
  fmt.Println("Hello World!") // This is a comment
}

```

## Go Multi-line comments

Multi-line comments start with /\* and end \*/

Any test between /\* and \*/ wil ignored by compiler:

```go

package main
import ("fmt")

func main() {
  /* The code below will print Hello World
  to the screen, and it is amazing */
  fmt.Println("Hello World!")
}
```
