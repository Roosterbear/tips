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


## CONSTANTS

>const double PI = 3.1416;
>#define AGE = 47


## BOOLEANS

-- 
* _C_ __DOES NOT HAVE BOOLEAN DATA TYPE__
--


## CHARS

--
* _C_ __TREATS CHARACTERS AS INTEGERS__

* So, if we compare in a switch: 
>case 'a'

* We really are doing:
>case 97
--


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

## RECEIVE DATA FROM USER


```c
puts("Enter value: ");
scanf("%c",&ch);
```

## ARRAYS

```c
const int SIZE = 5;
int prices[SIZE];
```


```c
int prices = {1,2,3,4,5};
```

## POINTERS

* ALWAYS store __INTEGER__ entities
* Is the only variable whose data type we do not have to specify
* To define a _pointer_ we use '*' character










--

# C++

To compile in Linux, use: <br/>

>g++ myprogram.cpp

Will get _a.out_ as a compiled file, if we need a custom name: <br/>

>g++ myprogram.cpp -o myname

To compile in C++11 Standard:

>g++ -std=c++11 source.cpp -o myname


Or you can use the __code runner__ extension for VSCode <br/>


## LIBRARIES

* __cstdio__ is oriented to _C_ like _printf_
* __iostream__ is oriented to _C++_ like: _cout_, _cin_


```c++
#include<iostream>
using namespace std;

int main(){
  int arre[] = {1,2,3};
  for(int i=0;i<=2;i++){
    cout<<arre[i];
    cout<<"\n";
  }  
}
```





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
