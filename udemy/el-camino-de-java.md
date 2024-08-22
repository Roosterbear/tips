# EL CAMINO DE JAVA

## ARREGLOS @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

Podemos declarar arrays de las siguientes formas: <br/>

```java
double[] array;
int arr[] = {1,2,3};
int arr[] = new int[5];
```

* Ordenar un arreglo

```java
Array.sort(miArreglo);
```



## CONDICIONES @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

### If



## CICLOS @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@


### Ciclo FOR Mejorado

* Normal

```java
for(int n=0;n<arr.length;n++){
  sum += arr[n];
}
```

* Mejorado

```java
for(double d:arr){
  sum += d;
}
```

### While

```java
double sum = 0;
int n = 0;
while(n<arr.length){
  sum = sum+arr[n];
  n++;
}
return sum/arr.length;
```

### Do While

```java
int n = 0;
do{
  n++;
}while(n<10);
```

* Break
> Termina el ciclo 

* Continue
> Brinca al inicio del ciclo


## PROGRAMACION ORIENTADA A OBJETOS @@@@@@@@@@@@@

> Es un metodo de programacion que IMITA la manera en que
> hacemos las cosas.

Existen 3 propiedades principales: <br/>

[Encapsulamiento] <br/>
> Es la combinacionde un registro
> con funciones paramanipular sus datos
> con lo que forma un nuevo tipo de dato: EL OBJETO





### Clases

> Son moldes para crear objetos



### Sobrecarga de metodos

> Definir varias funciones con el mismo nombre
> siempre y cuando el tipo de datos sea DIFERENTE



## EXCEPCIONES

> Todas las excepciones son objetos de la clase Throwable