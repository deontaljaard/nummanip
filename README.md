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
	newCalc "github.com/deontaljaard/nummanip/v2/calc"
)

func main() {
	result := calc.Add(1, 2, 3)
	fmt.Println("calc.Add(1, 2, 3) =>", result)

	// v2
	err, newResult := newCalc.Add()

	if err != nil {
		fmt.Println("Error: =>", err)
	} else {
		fmt.Println("calcNew.Add(1, 2, 3, 4) =>", newResult)
	}
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

## Troubleshooting
If you run into errors like 

```text
invalid version: module contains a go.mod file, so major version must be compatible: should be v0 or v1, not v
```

and you're certain if you've followed the docs, it's possible your module cache has been corrupted. Run the following to clean it.

```bash
go clean -modcache
```
