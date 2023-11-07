
# Slices

Go provides slices to store a collection of data

```go
package main

import "fmt"

func main() {
  letters := []string{"a", "b", "c", "d"}
	
  fmt.Println("First in the slice",letters[0])
}
```

We can use a for loop to look at each element in the slice

```go
package main

import "fmt"

func main() {
  letters := []string{"a", "b", "c", "d"}
	
  fmt.Println("First in the slice",letters[0])
  fmt.Println("Number of elements in the letters slice",len(letters))

  for index :=0; index < len(letters); index++ {
      fmt.Println(index, "in the slice",letters[index])
  }
}
```

We can change or update elements in the slice

```go
package main

import (
  "fmt"
  "strings"
)

func main() {
  letters := []string{"a", "b", "c", "d"}
	
  fmt.Println("First in the slice",letters[0])
  fmt.Println("Number of elements in the letters slice",len(letters))

  for index :=0; index < len(letters); index++ {
      letters[index] = strings.ToUpper(letters[index])
      fmt.Println(index, "in the slice",letters[index])
  }
}
```

## Appending to a slice
Go will make a new slice from our existing slice and the new element  
`letters = append(letters, "e")`


## Practice

### Fruit
Create a new version of our `letters` example above using the following slice 
`fruit := []string{"apple", "Banana", "cherry", "orange", "watermelon", "Mango", "Papaya", "Blueberry", "plum", "Peach", "pear", "Pineapple", "Raspberry", "Strawberry", "lemon", "lime"}`

Use append to add three more fruit.

Create another loop that displays the values using `Title` instead of `ToUpper`
And another using `ToLower`

Create another loop to display the fruit on one line using `Print` instead of `Println`


### Temperature
Slices can contain floats. Using the following code to start lets create a slice of 20 temperatures and display the converted temperature for each.

```go
package main

import "fmt"

func main() {
	temperature := 88.0

	fmt.Printf("%.2f fahrenheit to celsius %0.2f\n", temperature, (temperature*9/5)+32)
}
```


<br />

<hr />

<br />  


[Next: 06_json](/06_json.md)

