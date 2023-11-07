
# Hello World 

A new `repl` contains the following code:
```go
package main

import "fmt"

func main() {
  fmt.Println("Hello World")
}
```

`fmt` is part of the Go standard library.

The `fmt` package includes `Println`

<br>

## String Variables

```go
package main

import "fmt"

func main() {
  name := "Leah"
  fmt.Println("Hello", name)
}
```


<br>

## Numeric Variables

Arithmetic Operators: +, -, *, /, %

```go
package main

import "fmt"

func main() {
  x := 20
  y := 30
  fmt.Println("x =", x, "y =", y)
  fmt.Println("x + y =", x + y)
}
```

Integer calculations have no decimal 

If we want to use a decimal we can declare variables with decimals i.e. as float 


```go
package main

import "fmt"

func main() {
  x := 20.0
  y := 30.0
  fmt.Println("x =", x, "y =", y)
  fmt.Println("x + y =", x + y)
  fmt.Println("x / y =", x / y)
}
```

Output
```
x = 20 y = 30
x + y = 50
x / y = 0.6666666666666666
```

We have been creating variables inferring the type
`x := 10`

We can specify the type  
`var x float64 = 10`


We can check what type variables are using  
`fmt.Printf("%v %T", x, x)`


## Type safety
You cannot change the type of a variable one it has been declared.

```go
package main

import "fmt"

func main() {
  x := "Leah"
  y := 30.0
  fmt.Println("x =", x, "y =", y)
  fmt.Println("x + y =", x + y)
  fmt.Println("x / y =", x / y)
}
```

## Modulus operator
Only works with int

```go
package main

import "fmt"

func main() {
  x := 7
  y := 3
  fmt.Println("x % y =", x % y)
}
```

Output
```
x % y = 1
```

## Comments
You can add notes to your code using comments. 

You can use a comment to hide code and test things. 

```go
package main

import "fmt"

func main() {
  x := 7 // this variable is created as an integer
  // y := 3
  fmt.Println("x % y =", x % y)
}
```


<hr>

<br>

## Practice 

Experiment with changing types on the code we wrote


### Temperature conversions
Let's look at implementing a more complicated calculation, temperature conversion. 
The formula
(0°C × 9/5) + 32 = 32°F  
(38°C × 9/5) + 32 = 100.4°F  


Formatting decimal places  
`fmt.Printf("Value is %.2f", value)`

The output should look like  
```
88.00 celsius to fahrenheit 190.40
32.00 celsius to fahrenheit 89.60
0.00 celsius to fahrenheit 32.00
38.00 celsius to fahrenheit 100.40
```


<br />

<hr />

<br />  


[Next: 03_strings_and_user_input](/03_strings_and_user_input.md)

