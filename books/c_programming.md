<h1 style="color:#00b4d8">C Programming Language Handbook</h1>

- [Introducción](#introducción)
  - [Hello World](#hello-world)
  - [Arrays](#arrays)
  - [Strings](#strings)
  - [Apuntadores](#apuntadores)
  - [typedef y enum](#typedef-y-enum)
- [Estructuras](#estructuras)

# Introducción

## Hello World

```c
#include<stdio.h>

int main(void){
  printf("Hello World")
}
```
- [x] Compilar: ```gcc hello.c -o hello```
- [x] Ejecutar: ```./hello```

## Arrays

```int precios[3] = {100,200,300};```


## Strings

```c
#include<stdio.h>

int main(void){
  char name[4] = "Luis";
  printf("%s",name);
}
```

## Apuntadores

- [x] Las variables de apuntadores comienzan con __asterisco__
- [x] Para referenciar una direccion de memoria, se usa __ampersand__
- [x] Para mandar a imprimir un entero sin signo se usa __%u__ 

```c
#include<stdio.h>

int main(void){
  int edad = 49;
  int *address = &edad;
  printf("%u",*address);
}
```

## typedef y enum

```c
typedef enum{
  lunes,
  martes,
  miercoles,
  jueves,
  viernes,
  sabado,
  domingo
}SEMANA;

int main(void){
  SEMANA dia = miercoles;
  if(dia == miercoles){
    printf("Hoy es miercoles\n");
  }else{
    printf("Hoy NO es miercoles\n");
  }
}
```

# Estructuras

```c
struct persona{
  char *nombre;
  int edad
}fernando, personas[10];


```




``` ```
``` ```
``` ```
``` ```












