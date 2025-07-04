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

# Apuntadores

- [x] Para referenciar una direccion de memoria usamos __&variable__
- [x] Las variables sería: __*variable__

```c
int x = 1;
int *direccion_de_x = &x;
*direccion_de_x = 2;
```

```c
#include<stdio.h>

int main(){
  int edad = 49;
  int *address = &edad;
  printf("%u\n",*address);
  printf("%p\n",*edad);
}
```

```c
#include<stdio.h>

void go_south_east(int* lat, int* lon){
  *lat = *lat - 1;
  *lon = *lon + 1;
}

int main(){
  int latitude = 32;
  int longitude = -64;

  go_south_east(&latitude, &longitude);
  printf("Avast, now at:[%i,%i]\n", latitude, longitude);
  return 0;
}
```

```c
#include<stdio.h>

void fortune_cookie(char msg[]){
  printf("La galleta dice: %s\n",msg);
  printf("La frase esta guardada en la parte %p de memoria\n",msg);
}

int main(){
  char frase[] = "Las Galletas te hacen engordar!";
  fortune_cookie(frase);
  return 0;
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












