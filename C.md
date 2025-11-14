<h1 style="color:#00b4d8">C Programming</h1>

- [Introducción](#introducción)
- [Apuntadores](#apuntadores)
  - [typedef y enum](#typedef-y-enum)

# Introducción

- [x] Compilar: ```gcc hello.c -o hello```
- [x] Ejecutar: ```./hello```

```c
#include<stdio.h>

int main(void){
  int precios[3] = {100,200,300};
  char name[4] = "Luis";
  printf("%s\n",name);
  printf("%d\n",precios[0]);
}
```

# Apuntadores

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
