
# Loops

Increment and Decrement Operators: ++, --


```go
package main

import (
	"fmt"
)

func main() {
  index := 0

  fmt.Println("Index:", index)

  index++
  fmt.Println("Index:", index)

  index++
  fmt.Println("Index:", index)

  index++
  fmt.Println("Index:", index)
}
```

We can use a loop to repeat a set number of times.
```go
package main

import (
	"fmt"
)

func main() {
  index := 0
  max := 10

  fmt.Println("Before loop:", index)

  for index < max {
    index++
    fmt.Println("Index:", index)
  }

}
```

We can use loop shorthand 
```go
package main

import (
	"fmt"
)

func main() {
  max := 10

  // fmt.Println("Before loop:", index)

  for index := 0; index < max; index++ {
    fmt.Println("Index:", index)
  }
}
```

Now `index` is only accessible inside the loop. Use the loop short hand when you need to reference the loop index inside the loop only.

How would we change this to count down?

<br>
<hr>
<br>  

## Practice  

### Temperature
Extend the following temperature example to loop 5 times asking for the temperature and displaying the converted temperature 5 times.

```go
package main

import "fmt"

func main() {
	temperature := 88.0

	fmt.Printf("%.2f fahrenheit to celsius %0.2f\n", temperature, (temperature*9/5)+32)
}
```

How could you change the loop to continually ask for the temperature?


### Triangles  

Use one loop inside the other to display
```
*
**
***
****
*****
******
*******
```

Use one loop inside the other to display
```
*******
******
*****
****
***
**
*
```

Ask the user for input about how wide the triangles will be.



### Random numbers
Run and test the following code.
```go
package main

import (
  "fmt"
  "math/rand"
  "time"  
)

func main() {
  min := 10
  max := 30
  rand.Seed(time.Now().UnixNano())
  number := rand.Intn(max - min) + min
  fmt.Println()

  guess := 0
  for guess != number {
    fmt.Println("Guess the random number?")
    fmt.Scan(&guess)
  }

	fmt.Println("You guessed", guess, "the random number was", number)
}
```

Try commented out the following line and run and test.  
`rand.Seed(time.Now().UnixNano())`

Change the `Guess the random number?` message to also display the maximum and minimum values. 
