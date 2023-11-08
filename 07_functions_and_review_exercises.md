# functions

Functions we have used so far  
`main`

Functions in the `fmt` package


## When to use functions
- to break down large tasks
- for repeated code
- to add clarity (i.e. make the code explain itself)

```go
package main

import (
	"fmt"
)

func main() {
	x := 88.00
	y := (x * 9 / 5) + 32
	fmt.Printf("\n%.2f celsius to fahrenheit is %.2f", x, x)

	x = 328.00
	y = (x * 9 / 5) + 32
	fmt.Printf("\n%.2f celsius to fahrenheit is %.2f", x, x)

	x = 0.0
	y = (x * 9 / 5) + 32
	fmt.Printf("\n%.2f celsius to fahrenheit is %.2f", x, x)

	x = 42.0
	y = (x * 9 / 5) + 32
	fmt.Printf("\n%.2f celsius to fahrenheit is %.2f", x, x)
}
```

We have repeated code that may introduce errors through inconsistant typing.

Function to introduce:
```go
func calculateTemperature(celcius float64) float64 {
	return (celcius * 9 / 5) + 32
}
```

Easier to read and understand when using a function
```go
	y := (x * 9 / 5) + 32

	y = calculateTemperature(x)
```

Putting it together:ß
```go
package main

import (
	"fmt"
)

func calculateTemperature(celcius float64) float64 {
	return (celcius * 9 / 5) + 32
}

func main() {
	x := 88.00
	y := (x * 9 / 5) + 32
	fmt.Printf("\n%.2f celsius to fahrenheit is %.2f", x, y)

	fmt.Printf("\n\nNow using the function")
	y = calculateTemperature(x)
	fmt.Printf("\n%.2f celsius to fahrenheit is %.2f", x, y)

	x = 328.00
	y = (x * 9 / 5) + 32
	fmt.Printf("\n%.2f celsius to fahrenheit is %.2f", x, y)

	x = 0.0
	y = (x * 9 / 5) + 32
	fmt.Printf("\n%.2f celsius to fahrenheit is %.2f", x, y)

	x = 42.0
	y = (x * 9 / 5) + 32
	fmt.Printf("\n%.2f celsius to fahrenheit is %.2f", x, y)
}
```
<br />

## Practice

## Temperature
There is still repeated code. Change the code by putting  the `x` values in a slice and use a loop.

Make another version that coverts all the integer valus from 0 to 50 from celcius to fahrenheit. Do you need to use a slice for this?

Can you add another function? You can call functions from inside other functions.

## Triangles revisited
Update you code for the Trangles exercise. Create two functions, one for ascending triangles and one for descending triangles.

Are there any other patterns you can make?
Think about using spaces, try using `%`


## json revisited
Review the json app you created looking at where you can add functions. 

Extend the app to ask users for search terms.


[Next: 099_end_notes](/099_end_notes.md)