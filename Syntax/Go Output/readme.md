# Go Output Functions

Go has three functions to output text :

- Print()
- Println()
- Printf()

The Print() function

The Print() function prints its arguments with their default format .

### Example

Print the values of i and j :

```go
package main
import ("fmt")

func main(){
    var i,j string = "hello","world"
    fmt.Print(i) // same line
    fmt.Print(j)
}
```

output :

    Hello world

**Tips:**

- \n creates new lines
- print() inserts a space between the arguments if neither are strings

## Go Formatting Verbs

Formatting Verbs for Printf()

Go offers several formatting verbs that can be used with the **Printf()** function .

General Formatting Verbs

| Verb | Description                            |
| ---- | -------------------------------------- |
| %v   | Prints the value in the default format |
| %#v  | Prints the value in Go-syntax format   |
| %T   | Prints the type of the value           |
| %%   | Prints the % sign                      |

Example :

```go
package main
import ("fmt")

func main() {
  var i = 15.5
  var txt = "Hello World!"

  fmt.Printf("%v\n", i)
  fmt.Printf("%#v\n", i)
  fmt.Printf("%v%%\n", i)
  fmt.Printf("%T\n", i)

  fmt.Printf("%v\n", txt)
  fmt.Printf("%#v\n", txt)
  fmt.Printf("%T\n", txt)
}

```

result:

    15.5
    15.5
    15.5%
    float64
    Hello World!
    "Hello World!"
    string

## Integer Formatting Verbs

| Verb | Description                              | Example                   |
| ---- | ---------------------------------------- | ------------------------- |
| %b   | Base 2                                   | var i = 15 ; print 1111   |
| %d   | Base 10                                  | var i = 15 ; print 15     |
| %+d  | Base 10 and always show sign             | var i = 15 ; print +15    |
| %o   | Base 8                                   | var i =15 ; print 17      |
| %O   | base 8, with leading 0o                  | var i =15 ; print 0o17    |
| %x   | base 16, lowercase                       | var i = 15 ; print f      |
| %X   | base 16, upper case                      | var i = 15 ; print F      |
| %#X  | base 16, with leading 0x                 | var i = 15 ; print 0xf    |
| %4d  | Pad with spaces (with 4,right justified) | var i = 15 ; print \_\_15 |
| %4d  | Pad with spaces (with 4,left justified)  | var i = 15 ; print 15     |
| %04d | Pad with zeroes (width 4)                | var i = 15 ; print 0015   |

## String Formatting Verbs

The following verbs can be used with the string data. Example : txt = "hello"

| Verb | Description                                                 | Example               |
| ---- | ----------------------------------------------------------- | --------------------- |
| %s   | Prints the value as plain string                            | output: hello         |
| %q   | Prints the value as a double-quoted string                  | output: "hello"       |
| %8s  | Prints the value as plain string (width 8, right justified) | output:\_\_"hello"    |
| %-8s | Prints the value as plain string (width 8, left justified)  | output: hello         |
| %x   | Prints the value as hex dump of byte values                 | output:48656c6c6f     |
| % x  | Prints the value as hex dump with spaces                    | output:48 65 6c 6c 6f |

## Float Format Verbs

| Verb  | Description                               |
| ----- | ----------------------------------------- |
| %e    | Scientific notation with 'e' as exponent  |
| %f    | Decimal point, no exponent                |
| %.2f  | Default width, precision 2                |
| %6.2f | Width 6, precision 2                      |
| %g    | Exponent as needed, only necessary digits |

## Boolean Formatting Verbs

The following verb can be used with the boolean data type:

| Verb | Description                                                              |
| ---- | ------------------------------------------------------------------------ |
| %t   | Value of the boolean operator in true or false format (same as using %v) |
