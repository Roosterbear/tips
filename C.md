# C

## Compiler

* The compiler checks the syntax of our code
* Then translates it to assembly language
## Preprocessor Directives

* The most used is: __FILE INCLUSION DIRECTIVE__

```c
#include<stdio.h>
#include<conio.h>
```

* __MACRO SUBSTITUTION DIRECTIVE__

```c
#define MAX 100
```
* We can use __MAX__ as _100_


## HELLO WORLD

* create a file example.c
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


### CONSTANTS

>const double PI = 3.1416;
>#define AGE = 47

## CONDITIONS

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

## ITERATIONS

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

## ARRAYS

```c
const int SIZE = 5;
int prices[SIZE];
```


```c
int prices = {1,2,3,4,5};
```











--

# C++

To compile in Linux, use: <br/>

>g++ myprogram.cpp

Will get _a.out_ as a compiled file, if we need a custom name: <br/>

>g++ myprogram.cpp -o myname

To compile in C++11 Standard:

>g++ -std=c++11 source.cpp -o myname


Or you can use the __code runner__ extension for VSCode <br/>


### CREATE A GAME

Install SFML: <br/>
>sudo apt-get install libsfml-dev
>sudo apt-get install cmake
>sudo apt-get install libgl1-mesa-dev

Download __Qt__



--


# C#

Install Visual Studio: <br/>

>community 2019
>Desktop
>.NET Framework 4
>Register to avoid nasty 

Install Mono: <br/>

>sudo apt-get install -y mono-complete mono-devel mono-develop


## ASP

>Visual C# - Windows - Web
>ASP.NET Application
>Framework 4.5.2
>MVC template
>Change Authentication - Without authentication
>Uncheck Host in the Cloud
>Install SQL Server Management Studio





## Restaurant APP

>Visual C# - Windows - Desktop
>Windows Forms Application (.NET Framework)






## XAMARIN

>Development for movile devices with .NET
