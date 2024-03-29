# Go

## HELLO WORLD

* create a file example.go
* type: 

```go
package main

import "fmt"

func main(){
  fmt.Printf("Hello World Hacker!")
}
```
* You can just:
>go run example.go

* Or compile:
>go build example.go
>./example


## Principles

>A Go program must has .go extension and has to be compiled
>A Go program must starts with a package name
>A Go program must import every package that uses
>A Go program uses the main function to start
>You must capitalize variables from a package (like fmt.Println)
>The most common numeric types are: float64 and int.
>Declare a variable as: var name int = 1
>Use the short declaration: name := 1
>Format your code, specially if you want to share it: go fmt program.go
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

### Go Get Command / Go Modules

If we have: <br/>

```go
package main

import(
"fmt"
"net/http"
"github.com/stacktitan/ldapauth"
)
```
The last line import a package, but we can't access quite yet. <br/>

__Current option:__ <br/>
From your project root, exec: <br/>
>go mod init
It will create a _go.mod_ file. <br/>


__Classic option:__ <br/>
>go get github.com/stacktitan/ldapauth
This command will download the package in the GOPATH. <br/>
You can use it as:
>import "github.com/stacktitan/ldapauth"
To reload dependencies, run: <br/>
>go get -u


## ITERATIONS

```go
package main
import "fmt"

func main(){
  a := "Hola"
  for i,t := range a{
    fmt.Printf("%d: %s",i,string(t))
  }
}
```


## SLICES AND MAPS

__Slices__ are like arrays that you can dynamically resize and pass to function more efficiently. <br/>

__Maps__ are associative arrays, unordered lists of key/value pairs that allow you to efficiently and quickly look up values for unique key. <br/>






### dep

### mod

### Go fmt Command

Automatically formats your source code. <br/>
