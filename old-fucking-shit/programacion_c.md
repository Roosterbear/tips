# C ===================================================================
 
## Preprocessor Directives --------------------------------------------

* The most used is: __FILE INCLUSION DIRECTIVE__

```c
#include<stdio.h>
#include<conio.h>
```

* __MACRO SUBSTITUTION DIRECTIVE__

```c
#define MAX 100
```
Now we can use __MAX__ as _100_ <br/>


## HELLO WORLD @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

* create a file _example.c_
* Type: 

```c
#include<stdio.h>

int main(){
  printf("Hola mundo !!")  ;
}
```

To compile in Linux, use: <br/>
>gcc program.c -o program 
>./program


## Constants ----------------------------------------------------------

>const double PI = 3.1416;
>#define AGE = 47


## Booleans -----------------------------------------------------------

-- 
* _C_ __DOES NOT HAVE BOOLEAN DATA TYPE__
--


## Chars --------------------------------------------------------------

* __C__ treats characters as integers

* So, if we compare in a switch: 
>case 'a'

* We really are doing:
>case 97


## Conditions ---------------------------------------------------------

```c
if (AGE==true){
  printf("Age is true!");
}
```

```c
switch(LIVES){
  case 0:
    /* do something*/
    break;
  case 1:
    /* do something*/
    break;
  default:
    /* do something*/
    break;
}
```

## Iterations ---------------------------------------------------------

```c
for(int i = 0;i<10;i++){
  /* do something */
}
```

```c
while(i<10){
  /* do something */
}
```

```c
do{
  /* do something */
}while(i<10);
```

## Get data from user -------------------------------------------------


```c
puts("Enter value: ");
scanf("%c",&ch);
```

## Arrays -------------------------------------------------------------

```c
const int SIZE = 5;
int prices[SIZE];
```


```c
int prices = {1,2,3,4,5};
```

## POINTERS @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

* ALWAYS store __INTEGER__ entities
* Is the only variable whose data type we do not have to specify
* To define a _pointer_ we use '*' character

