

# User Input

The `fmt` package provides `Scan` for user input 

```go
package main

import "fmt"

func main() {
	var age int
	fmt.Println("What is your age?")
	fmt.Scan(&age)

	fmt.Println("You are", age)

	var name string
	fmt.Println("What is your first name?")
	fmt.Scan(&name)

  fmt.Println("Hello", name)
}
```


# Conditional statements

Comparison Operators: ==, !=, <, >, <=, >=


```go
package main

import "fmt"

func main() {
  justRight := 88
	var temperature int
	fmt.Println("What temperature is the soup?")
	fmt.Scan(&temperature)

  if temperature == justRight {
    fmt.Println("The soup is just right")
  }
}
```

Lets add feedback on other temperatures.

```go
package main

import "fmt"

func main() {
  justRight := 88
	var temperature int
	fmt.Println("What temperature is the soup?")
	fmt.Scan(&temperature)

  if temperature == justRight {
    fmt.Println("The soup is just right")
  } else {
    fmt.Println("The soup is not right")
  }
}
```

Now lets be more specific

```go
package main

import "fmt"

func main() {
  justRight := 88
	var temperature int
	fmt.Println("What temperature is the soup?")
	fmt.Scan(&temperature)

  if temperature == justRight {
    fmt.Println("The soup is just right")
  } else if temperature > justRight {
    fmt.Println("The soup TOO hot")
  } else {
    fmt.Println("The soup is not right")
  }
}
```

<hr>

## Practice

### Extend age example
Add some if statements to the `age` questions above
- over 16 and able to drive in the USA
- over 18 and able to drive in Australia

Ask the user the following questions, and then store the responses in variables. Assemble the individual variable values into a single string.
- "What is your last name?"
- "What is your street number?"
- "What is the name of your street?"
- "What is the name of your suburb?"
- "What is the name of your city?"
- "What is your postcode?"


### Odd or Even
The following example will show is `7` is even or odd. Extend this example to ask user to input a number and
display whether it is even or odd.

```go
package main

import "fmt"

func main() {
    if 7%2 == 0 {
        fmt.Println("7 is even")
    } else {
        fmt.Println("7 is odd")
    }
}
```