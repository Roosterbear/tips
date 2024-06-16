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

> Bubble
> Selection
> Insert

### Indirect (Advanced)

> Shell
> Quick sort
> Radix sort





## TEMPLATES @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

```c++
#include<iostream>
template<typename T>

T Max(T x, T y){
  std::cout<<typeid(T).name()<<std::endl;
  return x>y?x:y;
}

int main(){
  auto num = Max(3.3f, 5.8f);
  std::cout<<num<<std::endl;
  return 0;
}
```
