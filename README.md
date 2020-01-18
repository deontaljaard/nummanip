nummanip
=

Testing GoLang modules

## Usage
Create a Go module, main.

```bash
cd PROGRAMMING_DIR
mkdir main
cd main
go mod init test
```

Create a go file, namely app.go, that looks like
```go
package main

import (
	"fmt"

	"github.com/deontaljaard/nummanip/calc"
)

func main() {
	result := calc.Add(1, 2
	fmt.Println("calc.Add(1, 2) => ", result)
}
```

Run app.go
```
go run app.go
```

Go should automatically download the module and update the main module's go.mod file with a require.

## References
* [Anatomy of Go Modules](https://medium.com/rungo/anatomy-of-modules-in-go-c8274d215c16)
* [Go Modules Official Documentation](https://github.com/golang/go/wiki/Modules)
