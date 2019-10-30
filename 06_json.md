# JSON

This example uses a `json` data file.  
[What is JSON?](https://stackoverflow.com/questions/383692/what-is-json-and-why-would-i-use-it)

Create a new repl and call it `json`

Add a new file in your repl called `mock_data.json`
Copy the contents of the following into the file 
```json
{"users": 
  [{"id":1,"first_name":"Crichton","last_name":"Seckom","email":"cseckom0@utexas.edu","address":"68374 Dennis Way","city":"Legaspi","country":"Philippines","skill":"Hyperion Reports"},
  {"id":2,"first_name":"Bessie","last_name":"Fansy","email":"bfansy1@wp.com","address":"90622 Loeprich Crossing","city":"Santa Rosa de Copán","country":"Honduras","skill":"VDM"},
  {"id":3,"first_name":"Any","last_name":"Phette","email":"aphette2@pbs.org","address":"0632 Derek Terrace","city":"Vohibinany","country":"Madagascar","skill":"Wind Turbines"},
  {"id":4,"first_name":"Eula","last_name":"Khilkov","email":"ekhilkov3@timesonline.co.uk","address":"8526 Cambridge Road","city":"Clermont-Ferrand","country":"France","skill":"GDAL"},
  {"id":5,"first_name":"Derick","last_name":"Bennison","email":"dbennison4@360.cn","address":"3 North Junction","city":"Svalyava","country":"Ukraine","skill":"Aftersales"},
  {"id":6,"first_name":"Kimberley","last_name":"Tesh","email":"ktesh5@buzzfeed.com","address":"9 6th Terrace","city":"Talldaww","country":"Syria","skill":"Awesomeness"},
  {"id":7,"first_name":"Man","last_name":"Bigland","email":"mbigland6@mail.ru","address":"116 Weeping Birch Trail","city":"Wangzuo","country":"China","skill":"XML"},
  {"id":8,"first_name":"Justine","last_name":"Cordy","email":"jcordy7@netvibes.com","address":"3 Stuart Lane","city":"Magay","country":"Philippines","skill":"Glazing"},
  {"id":9,"first_name":"Thalia","last_name":"Jellett","email":"tjellett8@weibo.com","address":"9 Melby Drive","city":"Nelidovo","country":"Russia","skill":"Ultra Low Latency"},
  {"id":10,"first_name":"Arlen","last_name":"Garrish","email":"agarrish9@vimeo.com","address":"68860 Summit Court","city":"Uppsala","country":"Sweden","skill":"Organic Chemistry"}]
  }
  ```
In `main.go` add the following code

```go
package main

import (
	"encoding/json"
	"fmt"
	"io/ioutil"
	"os"
)

type Users struct {
	Users []User `json:"users"`
}

type User struct {
	Id        float64 `json:"id"`
	FirstName string  `json:"first_name"`
	LastName  string  `json:"last_name"`
	Email     string  `json:"email"`
}

func main() {
	// Open our jsonFile
	jsonFile, err := os.Open("mock_data.json")
	// if we os.Open returns an error then handle it
	if err != nil {
		fmt.Println(err)
	}
	fmt.Println("Successfully Opened mock_data.json")
	// defer the closing of our jsonFile so that we can parse it later on
	defer jsonFile.Close()

	// read our opened jsonFile as a byte array.
	byteValue, err := ioutil.ReadAll(jsonFile)
	if err != nil {
		panic(err)
	}
	// we initialize our Users array
	var users Users

	// we unmarshal our byteArray which contains our
	// jsonFile's content into 'users' which we defined above
	json.Unmarshal(byteValue, &users)
	fmt.Println("Unmarshaled users", len(users.Users))
  fmt.Println()

	for i := 0; i < len(users.Users); i++ {
    fmt.Println("User id#", users.Users[i].Id, "Name:", users.Users[i].FirstName, users.Users[i].LastName)
	}
}
```

Add the following to the User `struct`
- address
- city
- country
- skill

Add these values to the `Println` in the `for` loop.

Add an `if` to the `for` loop to only display users with names longer then 5.

Update your mock data  by copying the 1000 record data file [./data/mock_data.json](https://github.com/leahgarrett/go-intro-workshop/blob/master/data/MOCK_DATA.json)

Create a `for` loop that will display only Users from Australia.

Create a `for` loop to count and display the results of each of the following
- Users from China
- Users from United States
- Users with a skill containing the word "software"


## References
[Mockaroo - Data Source for Mock Data](https://www.mockaroo.com/schemas/download)  
[What is JSON?](https://stackoverflow.com/questions/383692/what-is-json-and-why-would-i-use-it)
