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
* __string__ for string methods like: _strupr()_

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

## STRUCTS

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

// Function Prototype --------
template <class TIPOD>
void mostrarAbs(TIPOD numero);
// ---------------------------

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
## REFERENCE PARAMETERS

> We send the memory address of a variable

```c++
#include<iostream>
using namespace std;

void new_value(int&, int&);

int main(){
  int num1, num2;

  cout<<"Digite 2 numeros: ";
  cin>>num1>>num2;

  new_value(num1,num2);

  cout<<"El primer NUEVO valor es: "<<num1<<endl;
  cout<<"El segundo NUEVO valor es: "<<num2<<endl;

}

void new_value(int& xnum, int&ynum){
  cout<<"El primer valor es: "<<xnum<<endl;
  cout<<"El segundo valor es: "<<ynum<<endl;

  // We can change the values:
  xnum = 123;
  ynum = 456;
}

```

## STRUCT PARAMETERS

```c++
#include<iostream>
using namespace std;

struct Persona{
	char nombre[30];
	int edad;
}p1;

// prototype
void pedirDatos();
void mostrarDatos(Persona);

int main(){
	pedirDatos();
	mostrarDatos(p1);
}

void pedirDatos(){
	cout<<"Digite su nombre: ";
	cin.getline(p1.nombre,30,'\n');
	cout<<"Digite su edad: ";
	cin>>p1.edad;
}

void mostrarDatos(Persona p){
	cout<<"Nombre: "<<p.nombre<<endl;
	cout<<"Edad: "<<p.edad<<endl;
}

```

## POINTERS

Is a variable where we store a memory address <br/>

```c++
#include<iostream>
using namespace std;

// PRIME NUMBERS
int main(){
  int numero, *dir_numero, cont = 0;

  cout<<"digite un numero: "; cin>>numero;
  dir_numero = &numero;

  // is a prime number?
  for(int i = 1;i<*dir_numero;i++){
    if(*dir_numero%i==0){
      cont++;
    }
  }

  if(cont>2){
    cout<<"El numero "<<*dir_numero<<" NO es primo"<<endl;
    cout<<"Posicion en memoria: "<<dir_numero<<endl;
  }else{
    cout<<"El numero "<<*dir_numero<<" SI es primo"<<endl;
    cout<<"Posicion en memoria: "<<dir_numero<<endl;
  }

}

```

## Arrays and Pointers

```c++
#include<iostream>
using namespace std;

int main(){
  int numeros[] = {1,2,3,4,5};
  int *dir_numeros;

  // We do not need to use: dir_numeros = &numeros[0]; Just:
  dir_numeros = numeros;

  for(int i = 0;i<5;i++){
    cout<<"\nElemento del vector: ["<<i<<"] es: "<<*dir_numeros<<endl;
    cout<<"Posicion de memoria: "<<numeros[i]<<" es: "<<dir_numeros++<<endl;
  }

}
```


## Dynamic Assignment of Arrays

```c++
#include<iostream>
#include<stdlib.h>

using namespace std;

void pedirNotas();
void mostrarNotas();

int numCalif, *calif;

int main(){
  pedirNotas();
  mostrarNotas();

  delete[] calif;
}

void pedirNotas(){
  cout<<"Digite ek numero de calificaciones: ";
  cin>>numCalif;

  calif = new int[numCalif];

  for(int i=0;i<numCalif;i++){
    cout<<"Ingrese una nota: "; cin>>calif[i];
  }
}

void mostrarNotas(){
  cout<<"\nMostrando notas del usuario\n";
  for(int i=0;i<numCalif;i++){
    cout<<calif[i]<<endl;
  }
}
```
