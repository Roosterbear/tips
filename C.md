<h1 style="color:#00b4d8">C Programming</h1>

- [Introducción](#introducción)
  - [Hello World](#hello-world)
  - [Arrays](#arrays)
  - [Strings](#strings)
- [Apuntadores](#apuntadores)
  - [typedef y enum](#typedef-y-enum)
- [Estructuras](#estructuras)
- [Make](#make)
- [Malloc](#malloc)

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
struct cell_phone{
  int cell_no;
  const char *wallpaper;
  float minutes_of_charge;
};
struct cell_phone p = {551012233, "iphone.png",2.2}
```

- [x] Siempre usamos la palabra __struct__ para crear una estructura
- [x] Podemos simplificarlo con __typedef__ y un __alias__

```c
typedef struct cell_phone{
  int cell_no;
  const char *wallpaper;
  float minutes_of_charge;
}phone;
phone p = {551012233, "iphone.png",2.2}
```
- [x] __INCLUSO SI TENEMOS UN ALIAS, PODEMOS OMITIR EL NOMBRE__

```c
#include<stdio.h>

typedef struct{
  const char *name;
  const char *species;
  int age;
} turtle;

void happy_birthday(turtle *t){
  (*t).age = (*t).age + 1;
  printf("Happy Birthday %s!, You are %i years old!\n",(*t).name, (*t).age);
}

int main(){
  turtle myrtle = {"Myrtle", "Leatherback Sea Turtle", 99};
  happy_birthday(myrtle);
  printf("%s's age is now %i\n", myrtle.name, myrtle.age);
  return 0;
}
```
- [x] __*t__ Nos regresa la dirección de memoria de __turtle__
- [x] __*(t.age)__ NO es correcto porque no es una direccion de memoria
- [x] __t->age__ es una opción más __legible__ para notación de punteros

# Make

* Es una herramienta que puede ejecutar el compilador
* Revisa si hay una actualización
* Necesita conocer los detalles de dependencias de archivos

# Malloc

* Solicita espacio de memoria al sistema
* Regresa un apuntador a esa memoria





