# Go

## Hello world

```go
package main

import "fmt"

func main(){
  fmt.Printf("Hello World Hacker!")
}
```

## Principles

>A Go program must has .go extension and has to be compiled
>A Go program must starts with a package name
>A Go program must import every package that uses
>A Go program use the main function to start
>You must capitalize variables from a package (like fmt.Println)
>The most common numeric types are: float64 and int.
>Declare a variable as: var name int = 1
>Use the short declaration: name := 1
>Format your code, specially you want to share it: go fmt program.go
>Compile: go build program.go and then exec our program
>Compile without creating or saving the executable: go run program.go
>Runes are simple characters in single quotations and may contain almost any character
>Go does not allow useless variables
>We can not use parenthesis in loops and conditions
>In packages use lowercase ALWAYS, no dashes, underscores or Capitalize

## Strip file

```bash
go build -ldflags "-w -s" hello.go
```

## Cross-Compiling

Is one of the coolest aspects of Go, as no other language can do it as easy. <br/>
The build command allows you to cross-compile your program for multiple operating systems and architectures. <br/>

To cross-compile, you need to set a __constraint.__ This is just a means to pass information to the _build_ command about the operating system and architecture for which you'd like to compile your code. <br/>

These constraints include __GOOS__ (_for the operating system_) and __GOARCH__ (_for the architecture_). <br/>

You can introduce build constraints in three ways: <br/> 

* Via de command line
* Code comments 
* A file suffix naming convention


### Cross-compile by command line

```bash
$ GOOS="linux" GOARCH="amd64" go build hello.go
$ ls
hello hello.go
$ file hello
hello: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, not stripped
```
### Go Doc Documentation

The __go doc__ command lets you interrogate documentation about a _package, method or variable._ This documentation is embedded as comments through your code. 

```bash
go doc fmt.Println
```

### Go Get Command

If we have: <br/>

```go
package main

import(
"fmt"
"net/http"
"github.com/stacktitan/ldapauth"
)
```

The last line import a package, but we can't access quite yet.
