# Go Variables

Variables are containers for storing data values

Go Variables Types

In Go, there are different **types** of variables, for example:

- int - stores integers (whole numbers), such as 123 or 123

- float32 - stores floating point numbers, with decimals .Examples 1.33

- string - stores text, such as "Hello world". String values are surrounded by double quotes

- boolean - stores values with states : true or false

More about different variables types, will be explained in the Go data types chapter.

## Declaring (creating) variables

In Go, the are two ways to declare a variable :

Use the **var** keyword,followed by variable name and type :

### 1. With the var keyword

####

Syntax

```go
    var variablename type = value
```

**Note:** you always have to specify either **type** or **value** (or both)

### 2. With the := sign:

```go
    variable := value
```

**Note:** In the case, the case, the type of the variable is **inferred** from the value (means that the compiler decides the type of variable, based on value) .
**Note** : It is not possible to declare variable using := ,without assigning a value to it.

## Variable DEclaration With inital value

If the value of variable is known from the start,you can declare variable and assign a value to it on one line :

```go
package main
import ("fmt")

func main() {
    var student1 string = "john"; // type is tring
    var student2 = "Jane" ;  // type is inferred
    x := 2 ;  // type is is inferred
}
```

Variable Declaration without initial value

```go
package main
import ("fmt")

func main(){
    var a string
    var b int
    var c bool

    fmt.Println(a)
    fmt.Println(b)
    fmt.Println(c)
}
```

In this example there are 3 variables : a,b,c

There variables are declared but they have not been assigned initial values .

By running the code, we can see that they already have the default values is not initially known.

```go
//default values

- a is ""
- b is 0
- c is false

```

### Value Assignment After Declaration

It is possible to assign a value to a variable after it is declared .This is helpful for cases the value is not initially known.

```go
package main
import ("fmt")

func main(){
    var student1 string
    student1 = "John"
    fmt.Println(student1)
}
```

**Note:** It is not possible to declare a variable using := without assigning a value to it.

### Different Between var and :=

There are some differences between the **var** var **:=**

| var                                                              | :=                                                                                                  |
| ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Can be used inside and outside of functions                      | Can only be used inside functions                                                                   |
| Variable declaration and value assignment can be done separately | Variable declaration and value assignment cannot be done separately (must be done in the same line) |

## Go Multiple Variables Declaration

In Go,it is possible to declare multiple variables in the same line.

```go
package main
import ("fmt")

func main(){
    var a, b, c, d int = 1, 3, 5, 7 // same type
}

```

**Note:** If you use the type keyword, it is only possible to declare **one type** of variable line .

If the **type** keyword is not specified, you can declare different types of variables in the same line:

```go
package main
import ("fmt")

func main(){
    var a,b = 6,"Hello"
    // result : a =6 , b = "Hello"
}
```

### Go Variable Naming Rules

A variable can have a short name (like x and y) or more descriptive name (age,price,carname,etc)

Go variable naming rules :

- A variable name must start with a letter or an underscore character (\_)
- A variable name cannot start with a digit .
- A variable name can only contain alpha-numeric characters and underscores (a -z , A-Z , 0 - 9 and \_)
- Variable names are case-sensitive (age,Age and AGE are three different variables)
- A variable name cannot contain spaces
- The variable name cannot be any Go keywords

### Multi-Word variable names

Variable names with more than one word can be difficult to read .
There are several techniques you can use to them more readable :

- Camel Case . Example : listProducts ;
- Pascal Case . Example : ListProducts ;
- Snake Case . Example : list_products ;
