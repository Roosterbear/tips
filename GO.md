<h1 style="color:#219ebc">Go</h1>

- [Introducción](#introducción)
  - [Hola Mundo](#hola-mundo)
  - [Tipos de Datos](#tipos-de-datos)
  - [Asignar Variables](#asignar-variables)
  - [Arreglos](#arreglos)
  - [Mapas](#mapas)
  - [Structs](#structs)
  - [Condicionales](#condicionales)
  - [Ciclos](#ciclos)
  - [Range](#range)
- [Funciones](#funciones)
- [Punteros](#punteros)
- [Interfaces](#interfaces)
- [Canales](#canales)

# Introducción

## Hola Mundo

```go
package main

import "fmt"

func main(){
    fmt.Println("Hola Mundo !!")
}
```

## Tipos de Datos

- [x] __bool__ true / false | false
- [x] __string__ cadenas | ""
- [x] __int__, int8, int16, int32, int64 | 0
- [x] __uint__, (_con signo_) uint8, uint16, uint32, uint64 | 0
- [x] __float32__, float64 (_reales_) | 0
- [x] __byte__ === __uint8__ (_caracter_) | 0
- [x] __rune__ === __int32__ (_caracter con más de un byte_) | 0
- [x] __complex64__, complex128 (_cuando es una parte real y otra imaginaria_) | 0+0i

## Asignar Variables

```go
var entero int = 1 // Lo especificamos
decimal := 1.1 // Lo infiere
```

## Arreglos

```go
arregloFijo := [3]int{1,2,3} // Ya no le podemos agregar elementos
slice := []int{1,2,3} // A este sí
slice = append(slice, 4)
```

## Mapas

```go
diccionario := map[string]int{
    "clave1":1,
    "clave2":2, // Se recomienda dejar la coma
}
```

## Structs

```go
type Persona struct{
    Nombre string
    Edad in
}

persona := Persona{Nombre:"Fernando"} // Si no ponemos edad, EXISTIRÁ con valor default 0
```

## Condicionales

```go
edad := 20

if edad < 18 { // No lleva paréntesis
    fmt.Print("Eres menor de edad")
    return
}

fmt.Println("Eres mayor de edad")
```

## Ciclos

```go
// Tradicional
for i := 0; i<5; i++{
    fmt.Printf("Iteración: %d\n", i)
}

// Tipo While
n := 3
for n<3{
    fmt.Printf("Iteración: %d\n", n)
    n++
}
```

## Range

```go
slice := []string{"uno", "dos", "tres"}

for _, value := range slice{ // Si no queremos usar un elemento que se debe implementar, usamos _
    fmt.Print("Valor: %d\n", value)
}
```

# Funciones

- [x] Tradicional

```go
func suma(a, b int) int{
    return a+b
}
```

- [x] Devolver + de 1 valor

```go
func dividir(a, b float64)(float64, float64){
    cociente := a/b
    resto := float64(int(a) % int(b))

    return cociente, resto
}

fun main(){
    cociente, resto := dividir(10, 3)
}
```


# Punteros

```
```

# Interfaces

```
```


# Canales 

```
```

















