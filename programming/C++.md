# C++ =================================================================
 
## Compile in Linux ---------------------------------------------------

>g++ myprogram.cpp

* Will get _a.out_ as a compiled file, if we need a custom name: 

>g++ myprogram.cpp -o myname

* To compile in C++11 Standard:

>g++ -std=c++11 source.cpp -o myname


## Libraries ----------------------------------------------------------

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

## SORTING @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

### Direct Sorting (Basic)

> Bubble - The lighter number is popping to the top like a soda bubble
> Insert - Check with the number of the left
> Selection - Seek the minimum number in each iteration

### Indirect (Advanced)

> Shell - Divide the elements between 2
> Quick sort - Divide and conquer, use a pivot
> Radix sort

## Structs

A Collection of one or more type of elements. <br/>

```c++
struct CD_Colection{
  char title[30];
  char artist[25];
  int numSongs;
  float price;
  char date[20];
};

// We can declare the struct variables before closing the struct
// Between "}" and ";"
int main(){
  struct CD_Colection cd1,cd2, cd3;
}

// we can fill the data with curly braces, Ej cd1 = {title="Hysteria"}
// We can access with our struct variable and its field, Ej. cd1.tittle

// We can get user data from (field, size, when to finish):
cin.getline(cd1.title,30,'\n');

```
> We can use Array Structs and nested structs: <br/>

```c++
// This struct will be part of employee
struct info_address{
  char address[30];
  char city[20];
}

// Here we use the info_address struct
struct employee{
  char name[20];
  struct info_address employee_address;
  double salary;
}employees[2];

// Save information
int main(){
  for(int i=0;i<2;i++){
    fflush(stdin); // Empty buffer
    cout<<"Digite su nombre: ";
    cin.getline(employee[i].name,20,'\n');
    cout<<"Digite su direccion: ";
    cin.getline(employee[i].employee_address.address,30,'\n');
    cout<<"Digite ciudad: ";
    cin.getline(employee[i].employee_address.city,20,'\n');
    cout<<"Digite salario: ";
    cin>>employee[i].salario;
    cout<<"\n";
  }

  // Print information
  for(int i=0;i<2;i++){
    cout<<"Nombre: "<<empleados[i].nombre<<endl;
    cout<<"Direccion: "<<empleados[i].employee_address.address<<endl;
    cout<<"Ciudad: "<<empleados[i].employee.city<<endl;
    cout<<"Salario: "<<empleados[i].salario<<endl;  
  }
}

```



## TEMPLATES @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

```c++
#include<iostream>

template <class TIPOD>
void mostrarAbs(TIPOD numero);

int main(){
  int num1 = -4;
  float num2 = 3.1416;
  double num3 = 123.456789;

  mostrarAbs(num1);
  mostrarAbs(num2);
  mostrarAbs(num3);


}

template <class TIPOD>
void mostrarAbs(TIPOD numero){
  if(numero < 0){
    numero = numero * -1;
  }

  cout<<"El valor absoluto es: "<<numero<<endl;
}

```

## POINTERS

Is a variable where we store a memory address <br/>


